# adaptive-scroll [![Build Status](https://travis-ci.org/angular-adaptive/adaptive-scroll.png?branch=master)](https://travis-ci.org/angular-adaptive/adaptive-scroll)

This module allows you to scroll an AngularJS app using gyroscope.

**Note: You need a device with a gyroscope and a browser with requestAnimationFrame support for smooth scrolling**

**We recommend [Gyrocopter extension for Chrome](https://github.com/janantala/Gyrocopter).**

### Demo

Check out http://angular-adaptive.github.io/adaptive-scroll/demo/

# Requirements

- AngularJS v 1.0+
- device with a gyroscope or a [simulator](https://github.com/janantala/Gyrocopter)
- browser with requestAnimationFrame support for smooth scrolling 
    - iOS Safari 6+, 
    - Chrome for Android 25+, 
    - Opera Mobile 14+
    - Firefox for Android 19+

# Usage

We use [bower](http://twitter.github.com/bower/) for dependency management. Add

    dependencies: {
        "angular-adaptive-scroll": "latest"
    }

To your `bower.json` file. Then run

    bower install

This will copy the scroll files into your `components` folder, along with its dependencies. Load the script files in your application:

    <script type="text/javascript" src="components/angular/angular.js"></script>
    <script type="text/javascript" src="components/angular-adaptive-scroll/src/adaptive-scroll.js"></script>

**Add the adaptive.scroll module** as a dependency to your application module:

    var myAppModule = angular.module('MyApp', ['adaptive.scroll']);

and **include $gyroscope service** as a dependency to your controller:

    angular.module('MyApp').controller('MainCtrl', function ['$scope', '$gyroscope', ($scope, $gyroscope) {

    }]);

**Append a directive adaptivescroll** to the scrollable element.

    <body adaptivescroll>
      ...
    </body>
    
    or
    
    <textarea adaptivescroll></textarea>

To start scrolling **run method watchPosition()** and pass trashold argument (in degrees):

    $gyroscope.watchPosition(10);

To stop scrolling run method ignorePosition():

    $gyroscope.ignorePosition();

# Testing

We use karma and jshint to ensure the quality of the code. The easiest way to run these checks is to use grunt:

    npm install -g grunt-cli
    npm install
    bower install
    grunt

The karma task will try to open Chrome as a browser in which to run the tests. Make sure this is available or change the configuration in `test/test.config.js` 

# License

The MIT License

Copyright (c) 2013 Jan Antala, https://github.com/janantala
