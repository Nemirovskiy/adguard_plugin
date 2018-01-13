код для добавления кнопки отображения видео и чата на всю ширину экрана

добавление: настроки плагина - Пользовательский фильтр
код для добавления в плагин
```
youtube.com#%#window.onload=function(){setTimeout(function(){if(document.getElementById('chat')!=null){if(document.getElementsByClassName('ytd-message-renderer')[0]==null){var ctrl=document.getElementsByClassName('ytp-right-controls')[0];var btn=document.createElement('button');btn.className="ytp-button";btn.title="Полный экран с чатом";btn.innerHTML='<div style="border:2px solid #fff; width: 15px;height: 13px;float: left;"></div><div style="border:2px solid #fff;width: 5px;height: 13px;float: left;border-left: 0;"></div>';ctrl.appendChild(btn);btn.addEventListener('click',function(){var wchat=300;var video=document.getElementsByTagName('video')[0];var html5pl=document.getElementsByClassName('html5-video-player')[0];var player=document.getElementById('player-container');html5pl.style.width=window.innerWidth-wchat+'px';html5pl.style.height=window.innerHeight-10+"px";player.style.cssText="position:fixed;top:0;left:0;z-index: 999999;width: "+(window.innerWidth-wchat)+'px;height:'+window.innerHeight+"px;";document.getElementById('chat').style.cssText="position: fixed;top:0;right:0;z-index: 999999; background:#fff;margin:0; padding:0; width:"+wchat+"px;height:"+(window.innerHeight+30)+"px;";video.style.top=0;video.style.left=0;video.style.height=(window.innerWidth-wchat)*(parseInt(video.style.height)/parseInt(video.style.width))+"px";video.style.width=window.innerWidth-wchat+'px';document.getElementsByTagName('body')[0].style.overflow="hidden";document.getElementsByClassName('ytp-chrome-bottom')[0].style.width=window.innerWidth-wchat-30+'px';document.getElementsByClassName('ytp-fullscreen-button')[0].style.display="none";document.getElementsByClassName('ytp-size-button')[0].style.display="none";document.getElementsByClassName('ytp-next-button')[0].style.display="none";btn.innerHTML='<div style="border:2px solid #fff;width: 15px;height: 8px;background: #aaa;"></div>';btn.title="Вернуть нормально";btn.addEventListener('click',function(){location.reload()})})}}},1200)};
```

сам код скрипта
```javascript
window.onload = function(){
	setTimeout(function(){
		if(document.getElementById('chat') != null){
			if(document.getElementsByClassName('ytd-message-renderer')[0] == null){
				var ctrl = document.getElementsByClassName('ytp-right-controls')[0];
				var btn = document.createElement('button');btn.className="ytp-button";
				btn.title="Полный экран с чатом";
				btn.innerHTML = '<div style="border:2px solid #fff; width: 15px;height: 13px;float: left;"></div>
					<div style="border:2px solid #fff;width: 5px;height: 13px;float: left;border-left: 0;"></div>';
				ctrl.appendChild(btn);
				btn.addEventListener('click', function() {
					var wchat = 300;
					var video = document.getElementsByTagName('video')[0];
					var html5pl = document.getElementsByClassName('html5-video-player')[0];
					var player = document.getElementById('player-container');
					html5pl.style.width= window.innerWidth - wchat + 'px';
					html5pl.style.height= window.innerHeight - 10 + "px";
					player.style.cssText="position:fixed;top:0;left:0;z-index: 999999;width: "+(window.innerWidth - wchat )+ 'px;height:' + window.innerHeight + "px;";
					document.getElementById('chat').style.cssText = "position: fixed;top:0;right:0;z-index: 999999; background:#fff;
						margin:0; padding:0; width:"+wchat+"px;height:"+(window.innerHeight+30)+ "px;";
					video.style.top=0;
					video.style.left=0;
					video.style.height= (window.innerWidth - wchat) * (parseInt(video.style.height)/parseInt(video.style.width)) + "px";
					video.style.width= window.innerWidth - wchat + 'px';
					document.getElementsByTagName('body')[0].style.overflow="hidden";
					document.getElementsByClassName('ytp-chrome-bottom')[0].style.width=window.innerWidth - wchat - 30 + 'px';
					document.getElementsByClassName('ytp-fullscreen-button')[0].style.display="none";
					document.getElementsByClassName('ytp-size-button')[0].style.display="none";
					document.getElementsByClassName('ytp-next-button')[0].style.display="none";
					btn.innerHTML = '<div style="border:2px solid #fff;width: 15px;height: 8px;background: #aaa;"></div>';
					btn.title="Вернуть нормально";
					btn.addEventListener('click', function() {
						location.reload();
					});
				});
			};
		};
	}, 1200);
};
```
