# request
network request module

集成步骤：
1. 在项目的根目录下的build.gradle中添加配置：
allprojects {
    repositories {
        google()
        jcenter()
        //添加如下代码配置
        maven { url "https://raw.githubusercontent.com/hbczzswqqq/request/master" }
    }
}

2. 在module的dependencies中添加如下配置
implementation 'com.boringkiller:request:1.0.0.201909201406d'//正式版本号只有三位如1.0.0；测试版本号添加了插件日期时间以及d作为debug版本标志
然后同步代码即可使用该插件进行网络请求了；

在开发调试阶段，部分请求接口可能为来得及添加到版本中，开发人员可以使用通用接口进行本地调试；
//不带参数的GET请求方法
public static void getRequest(String url, Observer<Object> subscriber, ObservableTransformer transformer) {
      ......
}
//带参数的GET请求方法
public static void getRequest(String url, HashMap<Object, Object> map, Observer<Object> subscriber, ObservableTransformer transformer) {
    ......
}
//POST请求方法
public static void postRequest(String url, Object body, Observer<Object> subscriber, ObservableTransformer transformer) {
    ......
}
//PUT请求方法
public static void putRequest(String url, Object body, Observer<Object> subscriber, ObservableTransformer transformer) {
    ......
}
//DELETE请求方法
public static void deleteRequest(String url, Observer<Object> subscriber, ObservableTransformer transformer) {
    ......
}
上面的方法中均带有请求地址，请求参数和返回结果均为Object类型，所以在传参时可以根据需要传入Map或者Body等，接收参数后转换为自己的实体类即可 。
  
