# ngTinyEditor
The ngTinyEditor is base on angular and tinyEditor(ngWYSIWYG), and more beautiful than before.

在最近的项目中需要一款简洁又好用的富文本编辑器，本来想用百度UM的，但是其功能太多，引用之后导致整个项目极其庞大，遂弃之。
然后偶然发现了tinyEditor这个富文本编辑器，代码量很小，满足了我们项目的基本全部需求，然后又看到有开发者直接编写好了angurla 版本的tinyEditor ，命名为ngWYSIWYG 。我不知道这个WYSIWYG 和tinyEditor 什么关系。所以直接以ngTinyEditor命名。<br>
汉化、改编自[WYSIWYG](https://github.com/psergus/ngWYSIWYG)<br>
`如侵删。`<br>
`0.` 最主要的是修改全部样式和布局，更加合理，抛弃原来的float布局，更改边框的布局，原编辑器的一个group组是通过一个div来实现的，修改交互，增加阴影特效等等，使其更加的现代化，更加的美观，这个也是我分享的主要原因。其中用到了开源的图标库fortawesome， 当然这个也是提升美观度的很大因素。<br>
`1.` 我在原有功能的基础上增加了一个功能模块，全屏功能。功能意义是当你嵌入到页面中，当需要潜心编写内容的时候一点击全屏就把整个富文本编辑器全屏。正如我们正在使用的lofter的编辑器一样。<br>
`2.` 修改了若干bug，不成熟的，比如插入图片的时候，什么都不写或者空白的链接，她也会解析成图片，还有字体颜色和文字背静颜色和特殊字符的选框会同时存在等，全部被我修改了，更符合人性化的交互啦。<br>
`3.` 调整了切换到查看源码模式顶部的控制条隐藏的奇怪交互。<br>
`4.` 改变了$sce 来绑定ng-bind-html。<br>
`5.` 增加了富文本的 model --> view 的｀xss｀过滤，这个大概增加了90行代码左右。其中主要改用了[Jsdxss](https://github.com/phith0n/Jsdxss)的思路和源码。
2015-09-23更。<br>
<br>
[![demo]](http://htmlpreview.github.io/?https://github.com/anchengjian/ngTinyEditor/blob/master/index.html)  
[demo]:https://raw.githubusercontent.com/anchengjian/ngTinyEditor/master/preview.png
<br>
## 依赖
  [AngularJs](https://angularjs.org/) `AngularJs` >= `1.2X` <br>
  [fortawesome](http://fortawesome.github.io/Font-Awesome/icons/)
 <br>
## demo
  [demo](http://htmlpreview.github.io/?https://github.com/anchengjian/ngTinyEditor/blob/master/index.html)
 <br>
## 使用说明
<br>
### link css
```html
  <link rel="stylesheet" href="css/editor.css">
  <link rel="stylesheet" href="css/font-awesome.min.css">
```
<br>
### load assets
```html
  <script src="js/angular.min.js"></script>
  <script src="js/ngTinyEditor.js"></script>
```
<br>
### use it wherever you want
```html
  <tinyedit content="content"></tinyedit>
```
<br>
### js
```js
  angular.module('myApp', ['ngTinyEditor']).
    controller('demoController', ['$scope', function($scope) {
      $scope.content = '<p>Hello World!</p>';
      $scope.$watch('content', function(newValue) {
        console.info(newValue);
      });
  }]);
```
<br>
### 其中为了新手需要说明：
  在module 部分需要依赖 `'ngTinyEditor'`
<br>
### 好了，再来一个全部的基础模版
```html
<!DOCTYPE html>
<html>
<head>
    <meta http-equiv="X-UA-Compatible" content="IE=edge"/>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
    <title>ngTinyEditor Demo</title>
    <link rel="stylesheet" href="css/editor.css">
    <link rel="stylesheet" href="css/font-awesome.min.css">
    <style>
        .container{margin: 100px;}
    </style>
</head>
<body ng-app="myApp">

    <div class="container" ng-controller="demoController">
        <tinyedit content="content"></tinyedit>
    </div>

    <script src="js/angular.min.js"></script>
    <script src="js/ngTinyEditor.js"></script>
    <script>
	angular.module('myApp', ['ngTinyEditor']).
	controller('demoController', ['$scope', function($scope) {
	    $scope.content = '<p>Hello World!</p>';
	    $scope.$watch('content', function(newValue) {
		  console.info(newValue);
	    });
	}]);
    </script>
</body>
</html>
```


