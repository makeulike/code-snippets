# Youtube Video Background
Like [http://www.seanmccambridge.com/tubular/](http://www.seanmccambridge.com/tubular/)

## mui.util with jQuery Use
mui.util.js 의 setBackground 함수를 이용하여 유튜브 API에서 생성하는 iframe 태그를 부모 엘리먼트 높이에 비례하게 확대
```JavaScript
var $target = $('#bg-video');
var _youtube = {
    'width': 1920,
    'height': 1080,
    'id': '000000000'
};

var resizeInterface = function() {
	mui.util.setBackground($target, _youtube.width, _youtube.height, 300);
};

$(window).resize(function() {
	resizeInterface();
});
```

## Youtube API Use
```JavaScript
/**
 * Youtube background
 */
var tmpPlayer;

var tag = document.createElement('script');
tag.src = "https://www.youtube.com/iframe_api";
var firstScriptTag = document.getElementsByTagName('script')[0];
firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

function onYouTubeIframeAPIReady() {
  tmpPlayer = new YT.Player('bg-video', {
    width: _youtube.width,
    height: _youtube.height,
    videoId: _youtube.id,
    playerVars: {
      'autoplay': 1,
      'rel': 0,
      'wmode': 'transparent',
      'controls': 0,
      'showinfo': 0
    },
    events: {
      'onReady': onPlayerReady,
      'onStateChange': onPlayerStateChange
    }
  });
}

function onPlayerReady(event) {
  tmpPlayer.mute();
}

function onPlayerStateChange(event) {
  if (event.data == YT.PlayerState.ENDED)
    tmpPlayer.playVideo();
  if (event.data == YT.PlayerState.PLAYING) {
    event.target.setPlaybackQuality('hd720');
  }
}

function onPlayerStateChange2(event) {
  if (event.data == YT.PlayerState.PLAYING) {
    event.target.setPlaybackQuality('hd1080');
  }
}

```