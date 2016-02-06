JS-Learning
==================


### Table of Contents
[Browserify](#browserify)

[Module-Pattern](#module-pattern)

[Database-Design](#database-design)

## Angular
[Share data between controllers](#share-data-between-controllers)  
* [AngularJS : Initialize service with asynchronous data](http://stackoverflow.com/questions/16286605/angularjs-initialize-service-with-asynchronous-data)
* [ui-router resume preventedEvent] (http://stackoverflow.com/a/26737967/4042489)


## Browserify
* [Cross platform JavaScript with Browserify – Sharing Code Between Node.js and the Browser](https://blog.codecentric.de/en/2014/02/cross-platform-javascript/)
* [Getting Started with Browserify](http://www.sitepoint.com/getting-started-browserify/?utm_source=javascriptweekly&utm_medium=email)


## Module-Pattern
* [JavaScript Module Pattern: In-Depth](http://www.adequatelygood.com/JavaScript-Module-Pattern-In-Depth.html)
* [JavaScript design pattern: difference between module pattern and revealing module pattern?](http://stackoverflow.com/questions/22906662/javascript-design-pattern-difference-between-module-pattern-and-revealing-modul)


## Database-Design
* [Modeling Product Variants](http://stackoverflow.com/questions/24923469/modeling-product-variants)


## Share data between controllers
* Here is a one-page example of two controllers sharing service data:
```
<!doctype html>
<html ng-app="project">
<head>
    <title>Angular: Service example</title>
    <script src="http://code.angularjs.org/angular-1.0.1.js"></script>
    <script>
var projectModule = angular.module('project',[]);

projectModule.factory('theService', function() {  
    return {
        thing : {
            x : 100
        }
    };
});

function FirstCtrl($scope, theService) {
    $scope.thing = theService.thing;
    $scope.name = "First Controller";
}

function SecondCtrl($scope, theService) {   
    $scope.someThing = theService.thing; 
    $scope.name = "Second Controller!";
}
    </script>
</head>
<body>  
    <div ng-controller="FirstCtrl">
        <h2>{{name}}</h2>
        <input ng-model="thing.x"/>         
    </div>

    <div ng-controller="SecondCtrl">
        <h2>{{name}}</h2>
        <input ng-model="someThing.x"/>             
    </div>
</body>
</html>
```
Also here: https://gist.github.com/3595424
