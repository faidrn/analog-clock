# Analog Clock

![](https://github.com/faidrn/analog-clock/blob/main/assets/images/ScreenShot.png)

![](https://github.com/faidrn/analog-clock/blob/main/assets/images/ScreenShotMobile.png)

Analog clock with HTML, CSS and JavaScript.

## HTML

This is the HTML structure:

```html
<div class="container external-shadow">
    <div class="clock internal-shadow">
        <div class="hour"></div>
        <div class="minutes"></div>
        <div class="seconds"></div>
    </div>
</div>
```

### Container

This div containt the clock structure, moreover, it's used to get the external shadow

### Clock

This div is the **clock**, because into this div is the hands axis of the clock (hour, minute and second), also is used for drawing the clock shape.


## JavaScript

The next code is using to get the clock working:

Setting 6 degrees of rotation for the minutes and seconds and to get elements HTML (clock hands), after  setting the clock, getting the hours, minutes and seconds using the object Date and then applying the transform style at the clock hands; finally, using the setIntervals method every second to rotate every clock hand.


```javascript
const deg = 6;
const hour = document.querySelector(".hour");
const min = document.querySelector(".minutes");
const sec = document.querySelector(".seconds");

const setClock = () => {
    let day = new Date();
    let hh = day.getHours   () * 30;
    let mm = day.getMinutes() * deg;
    let ss = day.getSeconds() * deg;

    hour.style.transform = `rotateZ(${hh + mm / 12}deg)`;
    min.style.transform = `rotateZ(${mm}deg)`;
    sec.style.transform = `rotateZ(${ss}deg)`;
};

setClock();
setInterval(setClock, 1000);
```



