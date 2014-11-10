AndroidContext
==============

Appcelerator Titanium code to fire paused/resumed events in Android.

## How to use

Put the Context.js in your `app/lib` folder and register every activity with Android Context:

```
<Alloy>
	<Window onOpen="onOpen" onClose="onClose" />
</Alloy>
```

```
var Context = require('Context');

function onOpen(evt) {
	Context.on('activityName1', this.activity);
}

function onClose(evt) {
	Context.off('activityName1');
}
```

Android Context will keep track of which Activity is currently active and will fire the `paused` and `resumed` events appropriately, when the app goes into the background / comes into foreground. Does currently not support `pause` and `resume`.
