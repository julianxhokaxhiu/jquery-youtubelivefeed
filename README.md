#jQuery YouTube Live Feed

###INTRODUCTION
This plugin wil let you get the VideoID of your live-stream based upon your User ID (you can get it at http://www.youtube.com/account_advanced),
your comments and if you're live or not.

###CHANGELOG
0.2: added onLive event<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;bugfixes<br>
0.1: initial relase version.

###OPTIONS
uid: the user ID of your channel
checkLiveInterval: set the timeout interval (in ms) of the Live check.
onComplete([data]): callback function that will be called upon completition of the request. After that you can call "getComments" to get comments of your video. The "data" parameter will be the returned object with infos (if you're Live or your video ID that after you can embed).
onLive([data]): callback function that will be called when a live stream will be detected every "checkLiveInterval" time. The "data" parameter will be the returned object with infos (like videoID of the live stream).

###METHODS
getComments(callback([data])): this method will give you all the comments of your video. They're NOT progressive, you will ALWAYS get ALL the comments under your video upon time. The "callback" parameter, has it's own "data" parameter which will contain all the comments. It will be an Array of objects.

clearLiveCheck(): this method will clear the live check interval set if no one is detected the first time this plugin will be used.

###LICENSE
This plugin is licensed as GPLv3. Read the attached LICENSE file for major informations.

###EXAMPLES
This is a pure example of obtaining data. This will NOT embed the player automatically, you will have to do it by your own.

```html
<div class="videocontainer"></div>
<script type="text/javascript">
	$('.videocontainer').youtubeLiveFeed({
		'uid':'YOUR-UID-HERE',
		'onComplete':function(data){
			console.log(data);
			$('.videocontainer').youtubeLiveFeed('getComments',function(comments){
				console.log(comments);
			})
		}
	})
</script>
```
