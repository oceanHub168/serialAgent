# serialAgent
c++  封装的串口通信aar,适用android 

# 使用

- 在项目的build.gradle 下面添加仓库地址
```
allprojects {
    repositories {
        google()
        jcenter()
        maven { url "https://github.com/oceanhub168pub/maven_repo/raw/master" }  // 这一句
    }
}
```

- 在项目中引用
> api 'com.hub168.yh:serialAgent-android:1.0.0@aar'

- 方法

  1.实现SerialBufferable接口,接受收到的数据
  
  2.创建实例对象
   SerialAgent serialAgent=new SerialAgent.Builder().setiBaudRate(115200)
                                                .setSerializable(serializableCallBack)
                                                .builder();
                                                
方法 | 参数 | 注解
------------ | ------------- | -------------
setiBaudRate | int | 设置波特率
setsPort | String | 设置读取的文件
setDataBits | int | 设置数据位
setStopBits | int | 设置停止位
setSerializable | SerialBufferable | 设置接收数据接口

打开<br/>
public void open()

发送数据<br/>
public void send(byte[] bOutArray) 

接收数据
public void onReceiverData(byte[] buffer, int buffsize);

关闭<br/>
public void close()
