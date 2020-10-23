### SPI（Service Provider Interface）

SPI全称Service Provider Interface，是Java提供的一套用来被第三方实现或者扩展的API，它可以用来启用框架扩展和替换组件。

![SPI](http://images.cdn.gramess.com/md/20200807/208133a138c9451d6824239a.jpg)



示例：

```java
package cn.nuaon.core.application;
 
import java.util.Iterator;
import java.util.ServiceLoader;
 
import cn.nuaon.core.service.CacheDataSource;
 
public class Application 
{
 
    public static void main (String[] args)
    {
        ServiceLoader<CacheDataSource> loader = ServiceLoader.load(CacheDataSource.class);
        Iterator<CacheDataSource> it = loader.iterator();
        while(it.hasNext())
        {
            CacheDataSource cacheDataSource = it.next();
            cacheDataSource.getDataSource();
        }
    }
}
```

```java
package cn.nuaon.core.service.impl;
 
import cn.nuaon.core.service.CacheDataSource;
 
public class MemoryCacheDataSource implements CacheDataSource 
{
    @Override
    public String getDataSource() 
    {
        System.out.println(this.getClass().getClassLoader());
        System.out.println("MemoryCacheDataSource");
        return this.getClass().getName();
    }
}
```

