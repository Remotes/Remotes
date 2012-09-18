# Remotes.io

## Control any web page remotely using Javascript

Remotes.io is a javascript library that can be used to control webpages remotely using gestures on a touch device. It currently supports the following gestures:

- Tap
- Hold
- Release
- Swipe



## Demo's

Here are some cool ways you can use Remotes.io

### Slideshow Presentation
A slideshow that uses Remotes.io to switch slides. [Check it out](https://dl.dropbox.com/u/9224326/www/presentation/index.html)

### Soundcloud Player
A Soundcloud player that uses Remotes.io to change tracks and control playback. [Check it out](https://dl.dropbox.com/u/9224326/www/soundcloud/index.html)

Want to add your site? [Say hello](mailto:hello@remotes.io)


## Documentation

A step by step guide on how to use remotes.io:

* Link to the latest Remotes build from your page

```
<script type="text/javascript" src="https://raw.github.com/Remotes/Remotes/master/dist/remotes.min.js"></script>

```

* [Here's a gist you can copy and paste to get started](https://gist.github.com/3741349).

* Control! Create a new Remotes object with the preview API key:

```var remotes = new Remotes("preview");```

Now, on every gesture that is performed on the remote touch device creates an event, and you'll receive a callback object with information on the gesture.

You can add event handler by using the 'on' method, and remove them using the 'off' method.

``` Remotes.on( "gesture-name", function(event){ // Handle your business }); ```

A single event can have mutliple handlers associated with it.
To remove an event handler, you must pass the event-name and the same callback function you wish to unbind, like so:

``` remotes.off( "gesture-name", function(event){ // Handle your business }); ```
	

Remotes.io currently supports the following touch events/gestures:

	remotes
	    .on("swipe-left", ...) 		// A touch and swipe in the leftward direction
		.on("swipe-right", ...)		// A touch and swipe in the rightward direction
		.on("swipe-up", ...) 		// A touch and swipe in the upward direction
		.on("swipe-down", ...) 		// A touch and swipe in the downward direction
		.on("tap", ...) 			// A quick tap/touch and release
		.on("hold", ...) 			// A touch lasting at least 500ms in one location
		.on("release", ...); 		// Fired when a 'Hold' event touch ends


### The Remotes.io event object:

The gesture events "tap" and "hold" provide:

- position.x: X co-ordinate of the gesture starting touch (px)
- position.y: Y co-ordinate of the gesture starting touch (px)
- sourceWidth: Width of the source broswer window (px)
- sourceHeight: Height of the source broswer window (px)

(the other events don't have a specific position attached to them)

### Requirements
Host: Google Chrome Browser (remotes.io currently requires the installation of a Google Chrome Extension)
Client: Touch device browser must be able to support websockets and touch events

Known touch device (mobile) browsers supporting websockets:
- iOS 4.2 and above
- Firefox for Android
- Chrome for Android
- Google Chrome 5 and above
- Firefox
- Safari 5
- IE 10 and above


### Client Touch Compatibility
|                                   | Tap | Hold | Swipe |
|:----------------------------------|:----|:-----|:------|
| **Windows**                                             
| Internet Explorer 8               | X   | X    | X     |
| Internet Explorer 9               | X   | X    | X     |
|                                                         
| **OSX**                                                 
| Firefox 11                        | X   | X    | X     |
| Opera 11                          | X   | X    | X     |
| Chrome 16                         | X   | X    | X     |
| Safari 5                          | X   | X    | X     |
|                                                         
| **iOS**                                                 
| iPad iOS 5                        | X   | X    | X     |
| iPhone iOS 5                      | X   | X    | X     |
|                                                         
| **Android 4**                                           
| Default browser                   | X   | X    | X     |
|                                                         
| **Android 3**                                           
| Default browser                   | X   | X    | X     |
|                                                         
| **Android 2**                                           
| Default browser                   | X   | X    | X     |
| Firefox 10                        | X   | X    | X     |
| Opera Mobile 12                   | X   | X    | X     |
| Opera Mini 6.5                    | X   |      |       |
| Opera Mini 7.0                    | X   |      |       |
|                                                         
| **Others**                                              
| Windows Phone 7.5                 | X   |      |       |
| Kindle Fire                       | X   | X    | X     |
| Nokia N900 - Firefox 1.1          | X   |      |       |


On a desktop browser the mouse can be used to simulate touch events with one finger.
On Android 2 (and 3?) doesn't support multi-touch events, so there's no transform callback on these Android versions.
Firefox 1.1 (Nokia N900) and Windows Phone 7.5 doesnt support touch events, and mouse events are badly supported.

Not all gestures are supported on every device. This matrix shows the support we have tested. This is ofcourse far from extensive.
If you've tested remotes.io on a different device, please let us know.

## Further notes
Created by [Philip Nuzhnyy](http://twitter.com/callmephilip).
Contributions by [Timothée Boucher](http://twitter.com/_timothee) and [Matt Campbell](http://twitter.com/just_matt)

Add your feature suggestions and bug reports on [GitHub](http://github.com/Remotes/Remotes/issues).
