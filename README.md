# mMedia (Millennial Media) Plugin Pro #

Present mMedia Ads in Mobile App/Games natively from JavaScript. 

Highlights:
- [x] Easy-to-use APIs. Display Ad with single line of Js code.
- [x] Support Banner, Interstitial Ad, and Video Ad.
- [x] One plugin supports both Android and iOS platform.
- [x] Auto fit on orientation change.
- [x] Actively maintained, prompt support.

Compatible with:

* Cordova CLI, v3.5+
* Intel XDK and Crosswalk, r1095+
* IBM Worklight, v6.2+

## How to use? ##

If use with Cordova CLI:
```
cordova plugin add com.rjfun.cordova.mmedia
```

If use with Intel XDK:
Project -> CORDOVA 3.X HYBRID MOBILE APP SETTINGS -> PLUGINS AND PERMISSIONS -> Third-Party Plugins ->
Add a Third-Party Plugin -> Get Plugin from the Web, input:
```
Name: mMediaPluginPro
Plugin ID: com.rjfun.cordova.mmedia
[x] Plugin is located in the Apache Cordova Plugins Registry
```

## Quick Start Example Code ##

Step 1: Prepare your mMedia Apid for your app, create it in [mMedia website](http://www.mmedia.com/)

```javascript
		var ad_units = {
			ios : {
				banner : "177365",
				interstitial : "177364"
			},
			android : {
				banner : "177367",
				interstitial : "177369"
			}
		};

// select the right Ad Id according to platform
var adId = ( /(android)/i.test(navigator.userAgent) ) ? ad_units.android : ad_units.ios;
```

Step 2: Create a banner with single line of javascript

```javascript
// it will display smart banner at top center, using the default options
if(mMedia) mMedia.createBanner({adId:adid.banner, autoShow:true});
```

Or, show the banner Ad in some other way:

```javascript
// or, show a default banner at bottom
	if(mMedia) mMedia.createBanner({
		adId : adid.banner,
		autoShow : true,
		overlap : true,
		position : mMedia.AD_POSITION.BOTTOM_CENTER
	});
```

Step 3: Prepare an interstitial or video Ad, and show it when needed

```javascript
// preppare and load ad resource in background, e.g. at begining of game level
if(mMedia) mMedia.prepareInterstitial( {adId:adid.interstitial, autoShow:false} );

// show the interstitial later, e.g. at end of game level
if(mMedia) mMedia.showInterstitial();
```

## Javascript API Overview ##

Methods:
```javascript
// set default value for other methods
setOptions(options, success, fail);
// for banner
createBanner(adId/options, success, fail);
removeBanner();
showBanner(position);
showBannerAtXY(x, y);
hideBanner();
// for interstitial
prepareInterstitial(adId/options, success, fail);
showInterstitial();
```

## Detailed Documentation ##

The APIs, Events and Options are detailed documented.

Read the detailed API Reference Documentation [English](https://github.com/floatinghotpot/cordova-mmedia-pro/wiki).

## FAQ ##

If encounter problem when using the plugin, please read the [FAQ](https://github.com/floatinghotpot/cordova-mmedia-pro/wiki/FAQ) first.

## Full Example Code ##

This mMedia Plugin Pro offers the most flexibility and many options.

Check the [test/index.html] (https://github.com/floatinghotpot/cordova-mmedia-pro/blob/master/test/index.html).

## Screenshots ##

iPhone Banner | iPhone Interstitial
-------|---------------
![ScreenShot](docs/iphone_banner.jpg) | ![ScreenShot](docs/iphone_interstitial.jpg)
 iPad Banner | iPad Video Ad
![ScreenShot](docs/ipad_banner.jpg) | ![ScreenShot](docs/ipad_video.jpg)
 Android Banner | Android Video Ad
![ScreenShot](docs/android_banner.jpg) | ![ScreenShot](docs/android_video.jpg)

## Credits ##

This mMedia Plugin Pro is published in a win-win partnership model:
- It's FREE. 
- It's closed source.
- 2% Ad traffic will be shared, as return for the support and maintenance effort.
- You will get commercial-level support with high priority, prompt and professional.

If you hope to make the Ad 100% under your control and keep 100% Ad revenue, you can also consider spending $20 to [get a license key](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=XJYYFV9XFF9U4) to remove the 2% Ad traffic sharing.
It's much cheaper than [the $50 iOS only AdMob plugin for unity](https://prime31.com/plugins). 

Then set the license key in options (either API setOptions, or createBanner, or prepareInterstitial):
```javascript
    license: 'username@gmail.com/xxxxxxxxxxxxxxx',
```

With impressive video Ads, mMedia Plugin Pro is one of the best choice for HTML5/Cordova/PhoneGap/XDK/Construct2 app/games.

## See Also ##

Cordova/PhoneGap plugins for top Mobile Ad services:

* [AdMob Plugin Pro](https://github.com/floatinghotpot/cordova-admob-pro), enhanced Google AdMob plugin, easy API and more features.
* [mMedia Plugin Pro](https://github.com/floatinghotpot/cordova-mmedia-pro), enhanced mMedia plugin, support impressive video Ad.
* [MobFox Plugin Pro](https://github.com/floatinghotpot/cordova-mobfox-pro), enhanced MobFox plugin, support video Ad and many other Ad network with server-side integration.
* [iAd Plugin](https://github.com/floatinghotpot/cordova-plugin-iad), Apple iAd service. 
* [FlurryAds Plugin](https://github.com/floatinghotpot/cordova-plugin-flurry), Yahoo Flurry Ads service.

More Cordova/PhoneGap plugins by Raymond Xie, [click here](http://floatinghotpot.github.io/).

Project outsourcing and consulting service is also available. Please [contact us](http://floatinghotpot.github.io) if you have the business needs.

