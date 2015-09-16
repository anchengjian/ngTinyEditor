# ngTinyEditor
The ngTinyEditor is base on angular and tinyEditor(ngWYSIWYG), and more beautiful than before.

在最近的项目中需要一款简洁又好用的富文本编辑器，本来想用百度UM的，但是其功能太多，引用之后导致整个项目极其庞大，遂弃之。
然后偶然发现了tinyEditor这个富文本编辑器，代码量很小，满足了我们项目的基本全部需求，然后又看到有开发者直接编写好了angurla 版本的tinyEditor ，命名为ngWYSIWYG 。我不知道这个WYSIWYG 和tinyEditor 什么关系。所以直接以ngTinyEditor命名。<br>
如侵删。<br>
其中修改了部分很多，最多的是把其布局和样式等几乎全部重写，使其更加的美观，这个也是我分享上来的主要目的。其中用到了开源的图标库fortawesome， 当然这个也是提升美观度的很大因素。<br>


## 依赖
  [AngularJs](https://angularjs.org/) `AngularJs` >= 1.2X <br>
  [fortawesome](http://fortawesome.github.io/Font-Awesome/icons/)
  
## demo
  [demo](http://htmlpreview.github.io/?https://github.com/anchengjian/ngTinyEditor/blob/master/index.html)
  
## 使用说明
### link css
```html
  <link rel="stylesheet" href="css/editor.css">
  <link rel="stylesheet" href="css/font-awesome.min.css">
```
### load assets
```html
  <script src="js/angular.min.js"></script>
  <script src="js/ngTinyEditor.js"></script>
```
### use it wherever you want
```html
  <tinyedit content="content"></tinyedit>
```
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
### 其中为了新手需要说明：
  在module 部分需要依赖 `'ngTinyEditor'`

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


