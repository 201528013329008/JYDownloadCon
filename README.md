# JYDownloadCon
HTTP request中加入“Range”头实现断点续传
```objc
       // 创建请求
        NSMutableURLRequest *request = [NSMutableURLRequest requestWithURL:[NSURL URLWithString: self.downLoadUrl]];

        // 设置请求头
        // Range : bytes=xxx-xxx，从已经下载的长度开始到文件总长度的最后都要下载
        NSString *range = [NSString stringWithFormat:@"bytes=%zd-",  DownloadLength];
        [request setValue:range forHTTPHeaderField:@"Range"];
```
