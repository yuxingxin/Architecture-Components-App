# Architecture-Components-App
2017 Xi'an GDG DevFest codelab app starter 

codelab地址：[Build an App with Architecture Components Codelab](https://codelabs.developers.google.com/codelabs/build-app-with-arch-components/index.html)

[完整工程地址](https://github.com/yuxingxin/Architecture-Component-App-Finished)

#### 各个包和类的描述

##### `data.network` package

从网络获取数据的相关类

* 网络获取与解析函数已经帮你写好了，你的工作是在正确的时间获取数据并展示结果

* 你无须修改 `NetworkUtils`, `OpenWeatherJsonParser` and `WeatherResponse` 相关类

* `WeatherNetworkDataSource` 管理与网络相关的所有事情，它是一个单例，包含有：

  * `scheduleRecurringFetchWeatherSync()`：使用 `FirebaseJobDispatcher`.来完成一个周期的 `JobService` 

    ，这个job最终会在后台同步天气信息数据。

  * `startFetchWeatherService()`：获取即时天气数据的一个IntentService服务

  * `fetchWeather()`：获取天气数据的方法，该类使用 JSON parsing和network classes来发起请求，它不处理任何与获取天气数据相关的事情

##### `data.database` package

所有和本地缓存数据相关的类（现在基本是空的）

* WeatherEntry - 表示一天天气的Java对象

##### `ui` package

所有和展示相关的的activity和adapters

##### ui.detail package

* `DetailActivity` - 展示某一天天气数据的Activity

##### ui.list package

* `MainActivty` - 展示`WeatherEntry`天气列表的Activity
* `ForecastAdapter` - 展示`WeatherEntry`天气列表的`RecyclerView.Adapter`

### `utilities` package

* 你无须修改 `SunshineDateUtils` 或者 `SunshineWeatherUtils`
* `SunshineDateUtils` - 跨时区格式化时间的工具方法
* `SunshineWeatherUtils` - 展示天气相关的工具方法，例如选取图片资源等。

#### AppExectuors class

提供全局的线程池，简而言之，该类可以很容易的在子线程中执行你的代码

#### 迁移

[Android Studio 3 和 Gradle for Plugins 3.0 迁移](https://zhuanlan.zhihu.com/p/30722989)





