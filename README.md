![sazs34’s github stats](https://github-readme-stats.vercel.app/api?username=sazs34&show_icons=true&theme=merko)

# MyActions
自己用来签到的东东,不支持售后

目前[@lxk0301](https://github.com/lxk0301) 的代码都支持无限账号了，各位可以直接使用那边的了呢

更新时间:2020-9-14 16:41:49

> 支持手动执行，具体在Actions中选中要执行的Workflows后再在右侧可以看到Run workflow


目前已支持[@NobyDa](https://github.com/NobyDa) 以及[@lxk0301](https://github.com/lxk0301) 中京东签到的内容,优点是支持无限数量的京东cookie

## 使用教程

1. 直接fork走
2. 再在`Settings`-`Secrets`里面添加`JD_COOKIE`
3. 多条cookie用`&`隔开，支持无数条cookie

上面三步搞定后就不用管了

刚fork完可能在Actions中看不到对应的workflow

目前**已配置好自动执行时间**，到了指定时间会执行并且看到workflow

### Secrets全集合

| Name                    |  归属  | 属性   | 说明                                                         |
| ----------------------- | :----: | ------ | ------------------------------------------------------------ |
| `JD_COOKIE`             |  京东  | 必须   |                                                              |
| `PUSH_KEY`              |  推送  | 非必须 | cookie失效推送[server酱的微信通知](http://sc.ftqq.com/3.version) |
| `BARK_PUSH`             |  推送  | 非必须 | cookie失效推送BARK这个APP,此token是https://api.day.app/后面的内容 |
| `FruitShareCodes`       | 分享码 | 非必须 | 京东农场                                                     |
| `PETSHARECODES`         | 分享码 | 非必须 | 京东萌宠                                                     |
| `PLANT_BEAN_SHARECODES` | 分享码 | 非必须 | 种豆得豆                                                     |
| `JDMarketCoinToBeans`   |  兑换  | 非必须 | 京小超蓝币兑换京豆，默认0，请填入纯数字,并且在0~20之间       |
| `JDJoyFeedCount`        |  喂食  | 非必须 | 宠汪汪喂食数量，默认10，请填写[10,20,40,80]其中任意一个      |
| `UNSUBSCRIBE`           |  取关  | 非必须 | 京东取关店铺和商品，格式为`取关商品数`,`取关店铺数`,`遇到此商品不再进行取关`,`遇到此店铺不再进行取关`      |

关于分享码的说明:

```javascript
// 同一个京东账号的好友互助码用@符号隔开,不同京东账号之间按Cookie隔开方法,即用&符号隔开,下面给一个示例
// 如: 京东账号1的shareCode1@京东账号1的shareCode2&京东账号2的shareCode1@京东账号2的shareCode2
0a74407df5df4fa99672a037eec61f7e@dbb21614667246fabcfd9685b6f448f3@6fbd26cc27ac44d6a7fed34092453f77@61ff5c624949454aa88561f2cd721bf6&6fbd26cc27ac44d6a7fed34092453f77@61ff5c624949454aa88561f2cd721bf6
```

取关店铺参数的说明

```javascript
// 例如我要取关10个商品，20个店铺，商品遇到商品关键字apple停止取关，店铺遇到apple不再取关
// 则填入的内容是10,20,apple,apple

//再例如我什么都不管，商品和店铺我都取关50个
// 则填入的内容为50,50,,

// 即 哪怕不填关键字，也要用英文逗号隔开
```

### Cookie获取和配置

> 具体如何取cookie如何配置,可参考 https://github.com/lxk0301/scripts/issues/8#issuecomment-675837338

```

针对京东cookie我们只需要
pt_key=****;
和
pt_pin=***;
的部分

我有两个京东账号,则我JD_COOKIE里面要填写的内容为
pt_key=****;pt_pin=***;&pt_key=****;pt_pin=***;
```

### fork后如何同步代码

[手动同步 http://www.ibloger.net/article/3361.html](http://www.ibloger.net/article/3361.html)

[自动同步 http://note.youdao.com/noteshare?id=6cd72de428957d593c129749194b4352](http://note.youdao.com/noteshare?id=6cd72de428957d593c129749194b4352)

