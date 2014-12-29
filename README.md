angular-selectize
==================
This is an Angular.js directive for Brian Reavis's [selectize jQuery plugin](http://brianreavis.github.io/selectize.js/).

* Selectize is ~7kb (gzipped)
* Snappy performance even with 10k+ options (refer to demo)
* Smart Ranking / Multi-Property Searching & Sorting
* Angular models & bindings
* Skinnable
* Keyboard Compatible

###[Try the Demos on Plunker](http://plnkr.co/edit/X2YYPX?p=preview)



## Dependencies

- [AngularJS](http://angularjs.org/)
- [JQuery](http://jquery.com/)
- [Selectize](http://brianreavis.github.io/selectize.js/)

## Install
Install with [Bower](http://bower.io)

`$ bower install angular-selectize2`

Load the script files in your application:
```html
<link rel="stylesheet" href="bower_components/selectize/dist/css/selectize.default.css ">
<script type="text/javascript" src="bower_components/jquery/jquery.js"></script>
<script type="text/javascript" src="bower_components/selectize/dist/js/standalone/selectize.min.js"></script>
<script type="text/javascript" src="bower_components/angular/angular.js"></script>
<script type="text/javascript" src="bower_components/angular-selectize2/dist/selectize.js"></script>
```


Add the selectize module as a dependency to your application module:

```javascript
var myAppModule = angular.module('MyApp', ['selectize']);
```

##Please Note!
Add the directive to `<div>` elements. It will not work with `<select>` because of conflicts with ngOptions.

## Usage
Setup your controller variables:

```javascript
$scope.myModel = 1;

$scope.myOptions = [
  {id: 1, title: 'Spectrometer'},
  {id: 2, title: 'Star Chart'},
  {id: 3, title: 'Laser Pointer'}
];

$scope.config = {
  create: true,
  valueField: 'id',
  labelField: 'title',
  delimiter: '|',
  placeholder: 'Pick something'
  // maxItems: 1
}
```

Add the selectize element to your view template:

```html
<div selectize="config" options='myOptions' ng-model="myModel"></div>
```


##Documentation
- [Selectize config options](https://github.com/brianreavis/selectize.js/blob/master/docs/usage.md)
- [Selectize API](https://github.com/brianreavis/selectize.js/blob/master/docs/api.md)

##Config
####Inline

```html
<div selectize="{create:true, maxItems:10}" options='myOptions' ng-model="myModel"></div>
```


####Global
To define global defaults, you can configure the `selectize` injectable:

```javascript
MyApp.value('selectizeConfig', {
  delimiter: '|'
});
```
