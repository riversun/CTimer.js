# Overview
'CTimer.js' is a Simple Timer Class for Javascript

Concurrent execution can be done easily because it is a class rather than a timer function(setInterval,setTimeout).

It is licensed under [MIT license](https://opensource.org/licenses/MIT).

# Quick start
## Example 1
Simple timer example.interval:100ms


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

# Example 2
Example on HTML.
<a href="https://riversun.github.io/ctimer/example1.html" target="_blank">Click here to open this example</a>
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>CTimer.js demo</title>
    <script src="CTimer.js"></script>

</head>
<body onload="start()">

Timer1:
<span id="timer1_container"></span>
<br/>
Timer2:
<span id="timer2_container"></span>

<script>

    function start() {

        var container1 = document.getElementById("timer1_container");
        var value1 = 0;
        var timer1 = new CTimer()
                .setIntervalMillis(500)
                .setCallback(function (timerObj) {
                    value1++;
                    container1.innerHTML = "<b>" + value1 + "</b>";
                    if (value1 == 10) {
                        timerObj.stopTimer();
                    }
                });


        var container2 = document.getElementById("timer2_container");
        var value2 = 0;
        var timer2 = new CTimer().setIntervalMillis(250)
                .setCallback(function (timerObj) {
                    value2++;
                    container2.innerHTML = "<b>" + value2 + "</b>";
                    if (value2 == 20) {
                        timerObj.stopTimer();
                    }
                });

        timer1.startTimer();
        timer2.startTimer();
    }

</script>
</body>
</html>
```
