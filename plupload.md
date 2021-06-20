## plupload



```javascript
var uploader = new plupload.Uploader({
    browse_button: 'danger', //触发文件选择对话框的按钮，为那个元素id
    url: "/upload/doupload", //服务器端的上传页面地址
    filters: {
        // 设置允许上传的类型
        max_file_size: '100mb', //设置允许上传的最大文件的大小
        mime_types: [
            // 用来限定上传文件的类型,一个类型一个对象，放入当前数组
            {title: 'Image files', extensions: 'jpg,png,tif,bmp'}
        ]
    }
});

// 在实例对象上调用init()方法进行初始化
uploader.init();

//当文件添加到上传队列后触发监听函数参数
uploader.bind("FilesAdded", function (uploader, files) {
    // uploader为当前的plupload实例对象，files为一个数组，里面的元素为本次添加到上传队列里的文件对象
    // console.log("FilesAdded",files);
    // 队列添加文件后，直接调用文件上传，也可以单独拿出
    uploader.start();
});

// 当队列中的某一个文件正要开始上传前触发监听函数参数
uploader.bind("BeforeUpload",function (uploader, file) {
    // uploader为当前的plupload实例对象，file为触发此事件的文件对象
    console.log("BeforeUpload", file);
});

//会在文件上传过程中不断触发，可以用此事件来显示上传进度监听函数参数
uploader.bind("UploadProgress", function (uploader, file) {
    // uploader为当前的plupload实例对象，file为触发此事件的文件对象
    console.log("UploadProgress", file.name, file.percent);
});

//当队列中的某一个文件上传完成后触发监听函数参数
uploader.bind("FileUploaded",function (uploader, file, info) {
    // uploader为当前的plupload实例对象，file为触发此事件的文件对象，responseObject为服务器返回的信息对象，它有以下3个属性：
    // response：服务器返回的文本
    // responseHeaders：服务器返回的头信息
    // status：服务器返回的http状态码，比如200
    console.log("FileUploaded", uploader, info.response);
    console.log(JSON.parse(info.response));
});
```

