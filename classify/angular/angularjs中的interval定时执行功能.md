#angularjs中的interval定时执行功能

> 本篇文章主要介绍了"angularjs中的interval定时执行功能 "，主要涉及到angularjs中的interval定时执行功能 方面的内容，对于angularjs中的interval定时执行功能 感兴趣的同学可以参考一下。
>
> 一个例子，用来显示当前实时时间，1秒钟刷新一次：

``` html
<!DOCTYPE html>
<html ng-app="myApp">
<head>
<meta charset="UTF-8">
<title>interval</title>
<script type="text/javascript" src="js/angular/angular.min.js"></script>
</head>
<body ng-controller="ctrl">
<div>当前时间为：{{time}}</div>
<script>
var app = angular.module('myApp',[]);
app.controller("ctrl",function($scope,$interval){
    $interval(function(){
        var time = new Date();
        var t = time.getFullYear()+"年"+(time.getMonth()+1)+"月"+time.getDate() + "日 星期"+"日一二三四五六".charAt(time.getDay())+ " "+time.getHours() +":"+time.getMinutes()+":"+time.getSeconds();
        $scope.time=t;
    },1000);
});
</script>
</body>
</html>
```

