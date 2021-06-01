### Nginx + Lua



```bash
server
{
    listen       80;
    server_name  localhost; 

    access_log  /var/log/nginx/access.log;
    charset utf-8;

    lua_code_cache on;

    location /dologin
    {
        default_type text/html;
        lua_code_cache on;
        rewrite_by_lua_file /opt/lua/1.lua;
    }

    location @mbuto
    {
        content_by_lua_block
        {
            ngx.say("<p>mbuto</p>")
        }
    }

    location @mbudo
    {
        content_by_lua_block
        {
            ngx.say("<p>mbudo</p>")
        }
    }
}
```



```lua
local request_method = ngx.var.request_method
local args = nil
local param= nil

if "GET" == request_method then
    args = ngx.req.get_uri_args()
elseif "POST" == request_method then
    ngx.req.read_body()
    args = ngx.req.get_post_args()
end

param = args["a"]
if "1" == param then
    ngx.exec("@mbuto")
elseif "2" == param then
    ngx.exec("@mbudo")
end
```

