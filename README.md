AdMobPlugin
===========

This is a prototype of a cross-platform Adv Cordova plugin. Android,
iOS and WindowsPhone7 are currently supported

## AdMob Plugin JavaScript API

As with most Cordova APIs, functionality is not available until the
`deviceready` event has fired on the document. The `admob.js` file
should be included _after_ the `cordova.js` file.

### Methods

#### start
    window.plugins.AdMob.start(successCallback, errorCallback)
	
Start adv

	successCallback - adv was success started
	errorCallback - error callback function
	
Example:
	
	window.plugins.AdMob.start(function(msg){
        console.log("Adv was started");
    }, function(msg){
        console.log("Adv start failed");//User use AdBlock or problem with internet connection
    }); 
    
    
#### stop
    window.plugins.AdMob.stop(successCallback, errorCallback)
	
Stop adv

	successCallback - adv was success stopeed
	errorCallback - error callback function
	
Example:
	
	window.plugins.AdMob.stop(function(msg){
        console.log("Adv was stoped");
    }, function(msg){
        console.log("Adv stop error");
    }); 


### Config.xml configuration

Example:

	<gap:plugin name="AdMob" version="1.0.0" >
		<parameter name="AD_MOB_ANDROID_AD_UNIT_ID" value="ANDROID_PUBLISHER_ID_HERE" platform="android"/>
		<parameter name="AD_MOB_IOS_AD_UNIT_ID" value="IOS_PUBLISHER_ID_HERE" platform="ios"/>
		<parameter name="AD_MOB_WP_AD_UNIT_ID" value="WP7_PUBLISHER_ID_HERE" platform="winphone"/>
		<parameter name="AD_MOB_ON_TOP" value="true" />
		<parameter name="AD_MOB_FORSE_START" value="true" />
		<parameter name="AD_MOB_DEBUG" value="true" />
	</gap:plugin>
	
#### AD_MOB_ANDROID_AD_UNIT_ID
	
Android Publisher ID from http://www.admob.com/

#### AD_MOB_IOS_AD_UNIT_ID
	
iOS Publisher ID from http://www.admob.com/

#### AD_MOB_WP_AD_UNIT_ID
	
Windows Phone 7 Publisher ID from http://www.admob.com/

#### AD_MOB_ON_TOP

If value is `true` adv was shown on top, if `false` - on bottom

#### AD_MOB_FORSE_START

If value is `true` adv was shown after start application, if `false` - _after_ call `window.plugins.AdMob.start` function

#### AD_MOB_DEBUG

If value is `true` adv was shown in debug mode, if `false` - in production mode
