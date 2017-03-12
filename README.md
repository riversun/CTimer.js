# Overview
'CTimer.js' is a Simple Timer Class for Javascript

Concurrent execution can be done easily because it is a class rather than a timer function(setInterval,setTimeout).

It is licensed under [MIT license](https://opensource.org/licenses/MIT).

# Quick start
## Search sequence of bytes from a big file quickly.

```js
var timer = new CTimer();
var value = 0;

timer.setCallback(function (timerObj) {
    value++;
    console.log(value);
    if (value == 100) {
        timerObj.stopTimer();
    }
});
timer.setIntervalMillis(100);
timer.startTimer();
```
