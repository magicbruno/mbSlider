#mbSlider 1.0.0
####A flexibile slider system to create animated presentations.
Based on bxSlider by by: Steven Wanderski - [http://stevenwanderski.com](http://stevenwanderski.com)

###Why should I use this slider?
* Define timing for every slide 
* Define in (entering) and out (exiting) animations for every HTML element in the slide
* Fully responsive - will adapt to any device
* Horizontal, vertical, and fade modes
* Slides can contain any HTML content
* Callback API and public methods
* Browser support: Modern Browser with fall back for ie8 and ie9.
* Tons of configuration options

For complete documentation visit:

###License
Released under the MIT license - http://opensource.org/licenses/MIT

Let's get on with it!

##Installation

You must include the jQuery library. The simpliest way is to include it from a CDN (see the example below). Visit [https://code.jquery.com/](https://code.jquery.com/) for a complete list of available versions. 

Next, download the package from this site and link the mbSlider CSS file (for the theme) and the mbSlider Javascript file.

```
<!-- jQuery library -->
<script   src="https://code.jquery.com/jquery-3.1.1.min.js"
  integrity="sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8="
  crossorigin="anonymous"></script>
  
<!-- mbSlider Javascript file -->
<script src="/mbslider/jquery.mbslider.min.js"></script>

<!-- mbSlider CSS file -->
<link href="/mbslider/jquery.mbslider.css" rel="stylesheet" />
```

##Use
Create a `<ul class="mbslider">` element, with a `<li>` for each slide. Slides can contain any HTML content!

```html
<ul class="mbslider">
  <li><img src="/images/pic1.jpg" /></li>
  <li><img src="/images/pic2.jpg" /></li>
  <li><img src="/images/pic3.jpg" /></li>
  <li><img src="/images/pic4.jpg" /></li>
</ul>
```
Call .mbSlider() on `<ul class="mbslider">`. Note that the call must be made inside of a $(document).ready() call, or the plugin will not work!

```javascript
$(document).ready(function(){
  $('.mbslider').mbSlider();
});
```
##Animations
You can animate any single HTML element inside a slide simply assigning to it some classes.

###General class
To every animated element you must assign the class `animated`.This class set general behaviors.
###Animation classes
Then you must:
* Assign a class for enter animation. Enter animation classes names have the "In" suffix or infix (like `fadeIn, flipInX, rotateIn, slideInUp`, etc.).
* Assign a class for exit animation. Exit animation classes have the "Out" suffix or infix (`fadeOut, flipInX, rotateIn, slideInUp`, etc.)
* Finally, if you need, you may modify animations speed and delay.

**Available enter animation classes**: `fadeIn, fadeInUp, fadeInUpBig, fadeInDown, fadeInDownBig, fadeInLeft, fadeInLeftBig, fadeInRight, fadeInRightBig, bounceIn, bounceInUp, bounceInDown, bounceInLeft, bounceInRight, rotateIn, rotateInBig, rotateInUpLeft, rotateInUpRight, rotateInDownLeft, rotateInDownRight, slideIn, slideInUp, slideInDown, slideInLeft, slideInRight, flipInX, flipOutX, lightSpeedIn, rollIn, zoomIn, zoomInDown, zoomInLeft, zoomInRight, zoomInUp`

**Available exit animation classes**: `fadeOut, fadeOutUp, fadeOutUpBig, fadeOutDown, fadeOutDownBig, fadeOutLeft, fadeOutLeftBig, fadeOutRight, fadeOutRightBig, bounceOut, bounceOutUp, bounceOutDown, bounceOutLeft, bounceOutRight, rotateOut, rotateOutUpLeft, rotateOutUpRight, rotateOutDownLeft, rotateOutDownRight, slideOut, slideOutUp, slideOutDown, slideOutLeft, slideOutRight, flipOutX, flipOutX, lightSpeedOut, hingeOut, rollOut, zoomOut, zoomOutDown, zoomOutLeft, zoomOutRight, zoomOutUp`

###Modifier classes
* **Delay**: You can use delayInXXXX and delayOutXXXX classes (where XXXX is 500, 1000, 1500, 2000, 2500, 3000, 3500, 4000, 4500, 5000) to delay in and/or out animation and create temporized animation sequences.
* **Speed**: Animations has a base speed of 1 second. You can modify animation speed using `slowIn, slowOut, fastIn, fastOut, xslowIn, xslowOut` classes.

###Single slides timing
You can customize single slides timing using `data-` attributes.

**data-pause**
The amount of time (in ms) between each auto transition. Override option `pause` setting.
```
<ul class="mbslider">
  <li data-pause="7000">
    .......
  </li>
</ul>
```


**data-pauseBeforeOut**

Pause before slide change in milliseconds. It allows out animation completion before the next slide enter. It works both in auto mode and in manual mode. Override option `pauseBeforeOut` setting.
```
<ul class="mbslider">
  <li data-pauseBeforeOut="2000">
    .......
  </li>
</ul>
```

**data-pauseAfterIn**

Pause added to slide pause in milliseconds. For every slide you may define a pause for in animation completion an a pause for slide reading. It works both in auto mode and in manual mode. Override option `pauseAfterIn` setting.
```
<ul class="mbslider">
  <li data-pauseAfterIn="2000">
    .......
  </li>
</ul>
```

###Slide show Example
Here's the code of the slide show you will find on the documentatio home page. 

HTML
```
<ul class="mbslider fade">
  <li id='slide_1' class="out">
    <h1><img alt="" class="img-responsive center-block animated delayOut1000 rotateInBig zoomOut" src="{{assets}}/img/LogoMbSlider_l.png" /></h1>
    <h3 class="text-center animated delayIn1000 bounceInRight fadeOutDown">Create animated presentations in minutes!</h3> </li>
  <li id='slide_2' class="out" data-pauseAfterIn="4000" data-pauseBeforeOut="5000" data-pause="5000">
    <div class="container">
      <div class="row">
        <div class="col-sm-3">
          <img alt="" class="img-responsive center-block animated rollIn rollOut delayOut3500" src="{{assets}}/img/conte-scontornato_L.png" />
        </div>
        <div class="col-sm-9">
          <ul>
            <li class="h2 animated delayIn1000 delayOut2000 bounceInRight hingeOut">
              <big>Define timing for every slide</big>
            </li>
            <li class="h2 animated delayIn1500 delayOut1000 bounceInRight fadeOutDown"><big>Define in and out animations for every HTML element in the slide</big></li>
            <li class="h2 animated delayIn2000 bounceInRight fadeOutDown"><big>Fully responsive - will adapt to any device</big></li>
          </ul>
        </div>
      </div>
    </div>
  </li>
  <li id='slide_3' class="out" data-pauseAfterIn="4000" data-pauseBeforeOut="5000" data-pause="5000">
    <div class="container">
      <div class="row">
        <div class="col-sm-9">
          <ul>
            <li class="h2 animated delayIn1000 delayOut2000 bounceInLeft hingeOut"><big>Slides can contain any HTML content</big></li>
            <li class="h2 animated delayIn1500 delayOut1000 bounceInLeft fadeOutDown"><big>Callback API and public methods</big></li>
            <li class="h2 animated delayIn2000 bounceInLeft fadeOutDown"><big>Support Modern Browser with fall back for ie8 and ie9.</big></li>
          </ul>
        </div>

        <div class="col-sm-3">
          <img alt="" class="img-responsive center-block animated rollInRight rollOutLeft delayOut3500 flippedY" src="{{assets}}/img/conte-scontornato-rotated.png" />
        </div>
      </div>
    </div>
  </li>
</ul>
```
JavaScript

```
<script>
  $(function() {
    var slider = $('.mbslider');
    slider.mbSlider({
      customAnimation: "slide",
      auto: true,
      pause: 8000,
      pauseBeforeOut: 2000,
      startSlide: 0,
      pager: false,
      controls: false,
      onSliderLoad: function(currentIndex) {
        setTimeout(function() {
          // Important! Class fade hide slider content
          // I use it to hide slider during initialization 
          // and i remove it only whem the slider is ready.
          slider.removeClass('fade');  
        }, 2000);
      }
  })
</script>
```

##Configuration options

###General

**mode**
Type of transition between slides
```
default: 'horizontal'
options: 'horizontal', 'vertical', 'fade'
```

**speed**
Slide transition duration (in ms)
```
default: 500
options: integer
```

**slideMargin**
Margin between each slide
```
default: 0
options: integer
```

**startSlide**
Starting slide index (zero-based)
```
default: 0
options: integer
```

**randomStart**
Start slider on a random slide
```
default: false
options: boolean (true / false)
```

**slideSelector**
Element to use as slides (ex. <code>'div.slide'</code>).<br />Note: by default, mbSlider will use all immediate children of the slider element
```
default: ''
options: jQuery selector
```

**infiniteLoop**
If <code>true</code>, clicking "Next" while on the last slide will transition to the first slide and vice-versa
```
default: true
options: boolean (true / false)
```

**hideControlOnEnd**
If <code>true</code>, "Prev" and "Next" controls will receive a class <code>disabled</code> when slide is the first or the last<br/>Note: Only used when <code>infiniteLoop: false</code>
```
default: false
options: boolean (true / false)
```

**easing**
The type of "easing" to use during transitions. If using CSS transitions, include a value for the <code>transition-timing-function</code> property. If not using CSS transitions, you may include <code>plugins/jquery.easing.1.3.js</code> for many options.<br />See <a href="http://gsgd.co.uk/sandbox/jquery/easing/" target="_blank">http://gsgd.co.uk/sandbox/jquery/easing/</a> for more info.
```
default: null
options: if using CSS: 'linear', 'ease', 'ease-in', 'ease-out', 'ease-in-out', 'cubic-bezier(n,n,n,n)'. If not using CSS: 'swing', 'linear' (see the above file for more options)
```

**captions**
Include image captions. Captions are derived from the image's <code>title</code> attribute
```
default: false
options: boolean (true / false)
```

**captionsCustomClass**
Add custom class to captions. 
```
default: ""
options: string
```

**ticker**
Use slider in ticker mode (similar to a news ticker)
```
default: false
options: boolean (true / false)
```

**tickerHover**
Ticker will pause when mouse hovers over slider. Note: this functionality does NOT work if using CSS transitions!
```
default: false
options: boolean (true / false)
```

**adaptiveHeight**
Dynamically adjust slider height based on each slide's height
```
default: false
options: boolean (true / false)
```

**adaptiveHeightSpeed**
Slide height transition duration (in ms). Note: only used if <code>adaptiveHeight: true</code>
```
default: 500
options: integer
```

**video**
If any slides contain video, set this to <code>true</code>. Also, include <code>plugins/jquery.fitvids.js</code><br />See <a href="http://fitvidsjs.com/" target="_blank">http://fitvidsjs.com/</a> for more info
```
default: false
options: boolean (true / false)
```

**responsive**
Enable or disable auto resize of the slider. Useful if you need to use fixed width sliders.
```
default: true
options: boolean (true /false)
```

**useCSS**
If true, CSS transitions will be used for horizontal and vertical slide animations (this uses native hardware acceleration). If false, jQuery animate() will be used.
```
default: true
options: boolean (true / false)
```

**preloadImages**
If 'all', preloads all images before starting the slider. If 'visible', preloads only images in the initially visible slides before starting the slider (tip: use 'visible' if all slides are identical dimensions)
```
default: 'visible'
options: 'all', 'visible'
```

**touchEnabled**
If <code>true</code>, slider will allow touch swipe transitions
```
default: true
options: boolean (true / false)
```

**swipeThreshold**
Amount of pixels a touch swipe needs to exceed in order to execute a slide transition. Note: only used if <code>touchEnabled: true</code>
```
default: 50
options: integer
```

**oneToOneTouch**
If <code>true</code>, non-fade slides follow the finger as it swipes
```
default: true
options: boolean (true / false)
```

**preventDefaultSwipeX**
If <code>true</code>, touch screen will not move along the x-axis as the finger swipes
```
default: true
options: boolean (true / false)
```

**preventDefaultSwipeY**
If <code>true</code>, touch screen will not move along the y-axis as the finger swipes
```
default: false
options: boolean (true / false)
```

**wrapperClass**
Class to wrap the slider in. Change to prevent from using default mbSlider styles.
```
default: 'bx-wrapper'
options: string
```

###Pager

**pager**
If <code>true</code>, a pager will be added
```
default: true
options: boolean (true / false)
```

**pagerType**
If <code>'full'</code>, a pager link will be generated for each slide. If <code>'short'</code>, a x / y pager will be used (ex. 1 / 5)
```
default: 'full'
options: 'full', 'short'
```

**pagerShortSeparator**
If <code>pagerType: 'short'</code>, pager will use this value as the separating character
```
default: ' / '
options: string
```

**pagerSelector**
Element used to populate the populate the pager. By default, the pager is appended to the bx-viewport
```
default: ''
options: jQuery selector
```

**pagerCustom**
Parent element to be used as the pager. Parent element must contain a <code>&lt;a data-slide-index="x"&gt;</code> element for each slide. See example <a href="/examples/thumbnail-method-1">here</a>. Not for use with dynamic carousels.
```
default: null
options: jQuery selector
```

**buildPager**
If supplied, function is called on every slide element, and the returned value is used as the pager item markup.<br />See <a href="http://mbslider.com/examples">examples</a> for detailed implementation
```
default: null
options: function(slideIndex)
```

###Controls

**controls**
If <code>true</code>, "Next" / "Prev" controls will be added
```
default: true
options: boolean (true / false)
```

**nextText**
Text to be used for the "Next" control
```
default: 'Next'
options: string
```

**prevText**
Text to be used for the "Prev" control
```
default: 'Prev'
options: string
```

**nextSelector**
Element used to populate the "Next" control
```
default: null
options: jQuery selector
```

**prevSelector**
Element used to populate the "Prev" control
```
default: null
options: jQuery selector
```

**autoControls**
If <code>true</code>, "Start" / "Stop" controls will be added
```
default: false
options: boolean (true / false)
```

**startText**
Text to be used for the "Start" control
```
default: 'Start'
options: string
```

**stopText**
Text to be used for the "Stop" control
```
default: 'Stop'
options: string
```

**autoControlsCombine**
When slideshow is playing only "Stop" control is displayed and vice-versa
```
default: false
options: boolean (true / false)
```

**autoControlsSelector**
Element used to populate the auto controls
```
default: null
options: jQuery selector
```

**keyboardEnabled**
Enable keyboard navigation for visible sliders
```
default: false
options: boolean (true / false)
```
###Animations

**customAnimation**

Is set to 'static' or 'slide' entering and exiting slides transitions must be handled by managing single slide elements animations. On *static* customAnimation, slides ar not removed from slider viewpoint. Delaying out transition you may perform next transition over old slide (se examples). On *slide* customAnimation slides are remove from viewpoint. Every in transition is from blank screen and every out transition is to blank screen.  If customAnimation is set to false transitions between slider are managed by mbSlider and `pauseBeforeOut` and `pauseAfterIn` values are ignored.  
```
default: false
options: boolean | string (true | 'static' | 'sòide')
```

**pauseBeforeOut**

Pause before slide change in milliseconds. It allows out animation completion before the next slide enter. It works both in auto mode and in manual mode. 
```
default: 1000
options: integer
```

**pauseAfterIn**

Pause added to slide pause in milliseconds. For every slide you may define a pause for in animation completion an a pause for slide reading. It works both in auto mode and in manual mode. 
```
default: 0
options: integer
```
###Auto

**auto**
Slides will automatically transition
```
default: false
options: boolean (true / false)
```
**stopAutoOnClick**
Auto will stop on interaction with controls
```
default: false
options: boolean (true / false)
```

**pause**
The amount of time (in ms) between each auto transition
```
default: 4000
options: integer
```

**autoStart**
Auto show starts playing on load. If <code>false</code>, slideshow will start when the "Start" control is clicked
```
default: true
options: boolean (true / false)
```

**autoDirection**
The direction of auto show slide transitions
```
default: 'next'
options: 'next', 'prev'
```

**autoHover**
Auto show will pause when mouse hovers over slider
```
default: false
options: boolean (true / false)
```

**autoDelay**
Time (in ms) auto show should wait before starting
```
default: 0
options: integer
```

###Carousel

**minSlides**
The minimum number of slides to be shown. Slides will be sized down if carousel becomes smaller than the original size.
```
default: 1
options: integer
```

**maxSlides**
The maximum number of slides to be shown. Slides will be sized up if carousel becomes larger than the original size.
```
default: 1
options: integer
```

**moveSlides**
The number of slides to move on transition. This value must be <code>>= minSlides</code>, and <code><= maxSlides</code>. If zero (default), the number of fully-visible slides will be used.
```
default: 0
options: integer
```

**slideWidth**
The width of each slide. This setting is required for all horizontal carousels!
```
default: 0
options: integer
```

**shrinkItems**
The Carousel will only show whole items and shrink the images to fit the viewport based on maxSlides/MinSlides.
```
default: false
options: boolean (true / false)
```

###Keyboard

**keyboardEnabled**
Allows for keyboard control of visible slider. Keypress ignored if slider not visible.
```
default: false
options: boolean (true / false)
```

###Accessibility
**ariaLive**
Adds Aria Live attribute to slider.
```
default: true
options: boolean (true / false)
```
    
**ariaHidden**
Adds Aria Hidden attribute to any nonvisible slides.
```
default: true
options: boolean (true / false)
```

###Callbacks

**onSliderLoad**
Executes immediately after the slider is fully loaded
```
default: function(){}
options: function(currentIndex){ // your code here }
arguments:
  currentIndex: element index of the current slide
```

**onSliderResize**
Executes immediately after the slider is resized
```
default: function(){}
options: function(currentIndex){ // your code here }
arguments:
  currentIndex: element index of the current slide
```

**onSlideBefore**
Executes immediately before each slide transition.
```
default: function(){}
options: function($slideElement, oldIndex, newIndex){ // your code here }
arguments:
  $slideElement: jQuery element of the destination element
  oldIndex: element index of the previous slide (before the transition)
  newIndex: element index of the destination slide (after the transition)
```

**onSlideAfter**
Executes immediately after each slide transition. Function argument is the current slide element (when transition completes).
```
default: function(){}
options: function($slideElement, oldIndex, newIndex){ // your code here }
arguments:
  $slideElement: jQuery element of the destination element
  oldIndex: element index of the previous slide (before the transition)
  newIndex: element index of the destination slide (after the transition)
```

**onSlideNext**
Executes immediately before each "Next" slide transition. Function argument is the target (next) slide element.
```
default: function(){}
options: function($slideElement, oldIndex, newIndex){ // your code here }
arguments:
  $slideElement: jQuery element of the destination element
  oldIndex: element index of the previous slide (before the transition)
  newIndex: element index of the destination slide (after the transition)
```

**onSlidePrev**
Executes immediately before each "Prev" slide transition. Function argument is the target (prev) slide element.
```
default: function(){}
options: function($slideElement, oldIndex, newIndex){ // your code here }
arguments:
  $slideElement: jQuery element of the destination element
  oldIndex: element index of the previous slide (before the transition)
  newIndex: element index of the destination slide (after the transition)
```

###Public methods

**goToSlide**
Performs a slide transition to the supplied slide index (zero-based)
```
example:
slider = $('.mbslider').mbSlider();
slider.goToSlide(3);
```

**goToNextSlide**
Performs a "Next" slide transition
```
example:
slider = $('.mbslider').mbSlider();
slider.goToNextSlide();
```

**goToPrevSlide**
Performs a "Prev" slide transition
```
example:
slider = $('.mbslider').mbSlider();
slider.goToPrevSlide();
```

**startAuto**
Starts the auto show. Provide an argument <code>false</code> to prevent the auto controls from being updated.
```
example:
slider = $('.mbslider').mbSlider();
slider.startAuto();
```

**stopAuto**
Stops the auto show. Provide an argument <code>false</code> to prevent the auto controls from being updated.
```
example:
slider = $('.mbslider').mbSlider();
slider.stopAuto();
```

**getCurrentSlide**
Returns the current active slide
```
example:
slider = $('.mbslider').mbSlider();
var current = slider.getCurrentSlide();
```

**getSlideCount**
Returns the total number of slides in the slider
```
example:
slider = $('.mbslider').mbSlider();
var slideQty = slider.getSlideCount();
```

**redrawSlider**
Redraw the slider. Useful when needing to redraw a hidden slider after it is unhidden.
```
example:
slider = $('.mbslider').mbSlider();
slider.redrawSlider();
```

**reloadSlider**
Reload the slider. Useful when adding slides on the fly. Accepts an optional settings object. <a href="/examples/reload-slider-settings">See here for an example.</a>
```
example:
slider = $('.mbslider').mbSlider();
slider.reloadSlider();
```

**destroySlider**
Destroy the slider. This reverts all slider elements back to their original state (before calling the slider).
```
example:
slider = $('.mbslider').mbSlider();
slider.destroySlider();
```

### Install Grunt and Bower

**Unfamiliar with npm? Don't have node installed?** [Download and install node.js](http://nodejs.org/download/) before proceeding.

From the command line:

1. Install `grunt-cli` and `bower` globally with `npm install -g grunt-cli bower`.
2. Run `npm install`. npm will look at `package.json` and automatically install the necessary dependencies. 
3. Run `bower install`, which installs front-end packages defined in `bower.json`.

When completed, you'll be able to run the various Grunt commands provided from the command line.

### Available Grunt commands

* `grunt` — Clean, Compile LESS to CSS, compile SCSS to CSS with compass,  concatenate and validate JS, build documentation.
* `grunt dist` — Clean, Compile LESS to CSS, compile SCSS to CSS with compass, concatenate and validate JS for plugin only.
* `grunt docs` — Clean, build documentation only.
* `grunt watch` — loads LiveReload, connects, and watches all assets.
* `grunt zip` — Creates a zip of `/dist` and places it in `/download`.
* `grunt jscs-check` - Check js style with jscs

