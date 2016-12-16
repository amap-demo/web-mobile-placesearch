# JSAPI-simple-placesearch-mobile
基于高德jsapi实现的手机端地点搜索

##效果预览

<img src='https://raw.githubusercontent.com/amap-demo/JSAPI-simple-placesearch-mobile/master/snapshots/1.jpg' width='200'/>
<img src='https://raw.githubusercontent.com/amap-demo/JSAPI-simple-placesearch-mobile/master/snapshots/2.jpg' width='200'/>
<img src='https://raw.githubusercontent.com/amap-demo/JSAPI-simple-placesearch-mobile/master/snapshots/3.jpg' width='200'/>
<img src='https://raw.githubusercontent.com/amap-demo/JSAPI-simple-placesearch-mobile/master/snapshots/4.jpg' width='200'/>

##实现思路

1. 基于 [AMap.Autocomplete](http://lbs.amap.com/api/javascript-api/reference/search/#m_AMap.Autocomplete)，实现一个支持关键字自动提示的搜索框

2. 基于 [AMap.PlaceSearch](http://lbs.amap.com/api/javascript-api/reference/search/#m_AMap.PlaceSearch)， 实现关键字搜索并显示结果列表

3. 监听`AMap.Autocomplete`，`AMap.PlaceSearch`抛出的事件，实现搜索框与结果面板之间的联动

4. 细节优化，包括结果面板的显示/隐藏，搜索结果的清楚，搜索中显示loading状态等

##关键点

- 如何获取用户选中的关键字？

  	监听`AMap.Autocomplete`的`select`事件，从事件参数中获取对应的城市信息和关键字名称传递给`AMap.PlaceSearch`

- 如何获取用户选中的地点结果，比如通过点击结果列表？
	
	监听`AMap.PlaceSearch`的`selectChanged`事件，从事件参数中可获取选中的地点信息

- 如何清除搜索结果

	调用`AMap.PlaceSearch`的`clear`函数

##相关参考

- AMap.Autocomplete： [接口说明](http://lbs.amap.com/api/javascript-api/reference/search/#m_AMap.Autocomplete)，[示例](http://lbs.amap.com/api/javascript-api/example/poi-search/input-prompt/)

- AMap.PlaceSearch： [接口说明](http://lbs.amap.com/api/javascript-api/reference/search/#m_AMap.PlaceSearch)，[示例](http://lbs.amap.com/api/javascript-api/example/poi-search/keywords-search/)