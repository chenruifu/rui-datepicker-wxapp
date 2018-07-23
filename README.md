## 微信小程序公农历日期选择器组件(rui-datepicker-wxapp)

- 支持公历农历切换，带时辰和不带时辰...
- 时间区间：1940-2-8至明年12-31（可修改代码调整）

### 效果

![gif](https://cdn.chenrf.com/abc.gif)

### 小程序二维码

![前端读者](http://cdn.chenrf.com/2018723213248.png)

### 使用方法
```html
<!-- wxml加载组件，指定组件ID，设置回调函数 -->
<rui-datepicker id="ruiDatepicker" bind:confirm="dateConfirm"></rui-datepicker>
```

```js
// json载入组件
{
    "usingComponents": {
        "rui-datepicker": "/components/rui-datepicker"
    }
}
```

```js
// 获取日期组件对象实例，并初始化配置
this.selectComponent("#ruiDatepicker").init({
    date: '2017-12-31',
    hour: '-1',
    lunar: false
});
```

具体参数配置及其默认参数：

```
confirm: true,          //是否需要确认
date: '1991-12-31',     //默认日期(新历)
hour: '-1',             //默认时辰,未知
showHour: true,         //是否有时辰选项
lunar: true,            //默认展示农历
```

统一确认回调函数上面绑定的 `bind:confirm`:

```js
dateConfirm(event) {
    console.log(event.detail)
}
```
`event.detail`对应的数据：

```
year: 1991          //公历年 
month: 12           //公历月 
day: 31             //公历日
hour: -1            //时辰，-1未知时辰
isLeap: false       //农历是否是闰年
lYear: 1991         //农历年
lMonth: 11          //农历月
lDay: 26            //农历日
lastTab: "solar"    //最后选择的是农历（lunar）还是公历（solar）

lunarStr: "农历:1991年十一月廿六 时辰未知"
solarStr: "公历:1991年12月31日 时辰未知"
thisStr: "公历:1991年12月31日 时辰未知"
```










