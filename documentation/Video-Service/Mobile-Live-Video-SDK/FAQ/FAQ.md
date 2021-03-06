# 常见问题

**Q：常见的推流方式？**

A：常见的推流方式有以下四种：
* 移动端 Android/iOS，使用京东云移动直播SDK采集摄像头视频或第三方软件，并推送视频流至RTMP推流地址。
* 台式机或笔记本，使用摄像头或桌面录屏：使用第三方软件采集摄像头视频或桌面图像，将视频或桌面内容推流至RTMP推流地址。第三方推流软件包括：OBS（推荐）、XSplit、FMLE 等。
* 视频采集设备：高清摄像机类设备如果具备 HDMI 或者 SDI 输出接口，可以接入编码器，以 RTMP 推流的方式向直播服务推送直播内容，您需要将直播推流地址配置到编码器的 RTMP 发布地址。  
网络摄像头类设备，如果支持 RTMP 推流，则可将直播推流地址配置到摄像头的 RTMP 发布地址。
* 视频文件转视频流：读取某个视频文件，并以 RTMP 流方式输出作为视频源来向直播服务的 RTMP 推流地址进行视频发布。可以使用 ffmpeg 命令来实现（Windows、Linux 及 Mac 均适用）。



**Q：目前支持的推流协议有哪些？**

A：推流SDK产品目前仅支持RTMP协议。


**Q：支持哪些播放协议？**

A：移动直播SDK支持RTMP、HLS、HDL多种协议播放。


