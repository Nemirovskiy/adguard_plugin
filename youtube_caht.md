# YouTube Chat
**Заголовок**
Скрипт добавляет кнопку в меню для отображения видео и чата
код для добавления кнопки отображения видео и чата на всю ширину экрана

+ кнопка добавляется только если есть чат
+ добавляется с задержкой, что б точно проверить есть ли чат

## Необходимые доработки
- [x] переделать на валидный код - изменить оформление кнопки
- [x] сделать кнопку вернуть всё как было вместо перезагрузки
- [ ] сделать кнопки увеличения и уменьшения видео
- [ ] Add a new colum

добавление: настроки плагина - Пользовательский фильтр
код для добавления в плагин
```
youtube.com#%#var panel,btn=document.createElement("button"),video,html5pl,player,wchat=300;function skypeChatOff(){html5pl.style.cssText="",player.style.cssText="",document.getElementById("chat").style.cssText="",document.getElementsByTagName("body")[0].style.cssText="",document.getElementsByClassName("ytp-chrome-bottom")[0].style.width=document.getElementsByClassName("ytp-chrome-bottom")[0].parentElement.clientWidth-24+"px",document.getElementsByClassName("ytp-fullscreen-button")[0].style.cssText="",document.getElementsByClassName("ytp-size-button")[0].style.cssText="",document.getElementsByClassName("ytp-next-button")[0].style.cssText="",video.style.height=video.getAttribute("original-height")+"px",video.style.width=video.getAttribute("original-width")+"px",btn.removeEventListener("click",skypeChatOff),btn.addEventListener("click",skypeChatOn),createBtn()}function skypeChatOn(){video.setAttribute("original-width",video.clientWidth),video.setAttribute("original-height",video.clientHeight),html5pl.style.width=window.innerWidth-wchat+"px",html5pl.style.height=window.innerHeight-10+"px",player.style.cssText="position:fixed;top:0;left:0;z-index: 999999;width: "+(window.innerWidth-wchat)+"px;height:"+window.innerHeight+"px;",document.getElementById("chat").style.cssText="position: fixed;top:0;right:0;z-index: 999999; background:#fff; margin:0; padding:0; width:"+wchat+"px;height:"+(window.innerHeight+30)+"px;",video.style.top=0,video.style.left=0,video.style.height=(window.innerWidth-wchat)*(parseInt(video.style.height)/parseInt(video.style.width))+"px",video.style.width=window.innerWidth-wchat+"px",document.getElementsByTagName("body")[0].style.overflow="hidden",document.getElementsByClassName("ytp-chrome-bottom")[0].style.width=window.innerWidth-wchat-24+"px",document.getElementsByClassName("ytp-fullscreen-button")[0].style.display="none",document.getElementsByClassName("ytp-size-button")[0].style.display="none",document.getElementsByClassName("ytp-next-button")[0].style.display="none",btn.innerHTML="<div style=\"border:2px solid #fff;width: 15px;height: 8px;background: #aaa;\"></div>",btn.title="\u0412\u0435\u0440\u043D\u0443\u0442\u044C \u043D\u043E\u0440\u043C\u0430\u043B\u044C\u043D\u043E",btn.removeEventListener("click",skypeChatOn),btn.addEventListener("click",skypeChatOff)}function createBtn(){panel=document.getElementsByClassName("ytp-right-controls")[0],btn.title="\u041F\u043E\u043B\u043D\u044B\u0439 \u044D\u043A\u0440\u0430\u043D \u0441 \u0447\u0430\u0442\u043E\u043C",btn.innerHTML="<div style=\"border:2px solid #fff; width: 15px;height: 13px;float: left;\"></div> <div style=\"border:2px solid #fff;width: 5px;height: 13px;float: left;border-left: 0;\"></div>"}function skypeChatInit(){null!=document.getElementById("chat")&&null==document.getElementsByClassName("ytd-message-renderer")[0]&&(video=document.getElementsByTagName("video")[0],html5pl=document.getElementsByClassName("html5-video-player")[0],player=document.getElementById("player-container"),createBtn(),panel.appendChild(btn),btn.className="ytp-button",btn.addEventListener("click",skypeChatOn))}window.onload=function(){setTimeout(skypeChatInit,1200)};
```

исходный код скрипта
```javascript
var panel;    /* место крепления кнопки*/
var btn = document.createElement('button');     /* наша кнопка */
var video;   /*  */
var html5pl; /*  */
var player;  /*  */
var wchat = 300; /* ширина чата */

function skypeChatOff(){
 	/*функция возврата*/
	html5pl.style.cssText="";
	player.style.cssText="";
	document.getElementById('chat').style.cssText="";
	document.getElementsByTagName('body')[0].style.cssText="";
	document.getElementsByClassName('ytp-chrome-bottom')[0].style.width=document.getElementsByClassName('ytp-chrome-bottom')[0].parentElement.clientWidth - 24 + 'px';
	document.getElementsByClassName('ytp-fullscreen-button')[0].style.cssText="";
	document.getElementsByClassName('ytp-size-button')[0].style.cssText="";
	document.getElementsByClassName('ytp-next-button')[0].style.cssText="";
	video.style.height = video.getAttribute('original-height') + "px";
	video.style.width  = video.getAttribute('original-width') + "px";
	btn.removeEventListener('click', skypeChatOff);
	btn.addEventListener('click', skypeChatOn);
	createBtn();
};
 function skypeChatOn(){
	 /*функция включения чата на весь экран*/
	video.setAttribute("original-width", video.clientWidth);
	video.setAttribute("original-height", video.clientHeight);
	html5pl.style.width= window.innerWidth - wchat + 'px';
	html5pl.style.height= window.innerHeight - 10 + "px";
	player.style.cssText="position:fixed;top:0;left:0;z-index: 999999;width: "+(window.innerWidth - wchat )+ 'px;height:' + window.innerHeight + "px;";
	document.getElementById('chat').style.cssText = "position: fixed;top:0;right:0;z-index: 999999; background:#fff; margin:0; padding:0; width:"+wchat+"px;height:"+(window.innerHeight+30)+ "px;";
	video.style.top=0;
	video.style.left=0;
	video.style.height= (window.innerWidth - wchat) * (parseInt(video.style.height)/parseInt(video.style.width)) + "px";
	video.style.width= window.innerWidth - wchat + 'px';
	document.getElementsByTagName('body')[0].style.overflow="hidden";
	document.getElementsByClassName('ytp-chrome-bottom')[0].style.width=window.innerWidth - wchat - 24 + 'px';
	document.getElementsByClassName('ytp-fullscreen-button')[0].style.display="none";
	document.getElementsByClassName('ytp-size-button')[0].style.display="none";
	document.getElementsByClassName('ytp-next-button')[0].style.display="none";
	btn.innerHTML = '<div style="border:2px solid #fff;width: 15px;height: 8px;background: #aaa;"></div>';
	btn.title="Вернуть нормально";
	btn.removeEventListener('click', skypeChatOn);
	btn.addEventListener('click', skypeChatOff);
};
function createBtn(){
	panel = document.getElementsByClassName('ytp-right-controls')[0];/*находим место подключения кнопки*/
	btn.title="Полный экран с чатом";
	btn.innerHTML='<div style="border:2px solid #fff; width: 15px;height: 13px;float: left;"></div> <div style="border:2px solid #fff;width: 5px;height: 13px;float: left;border-left: 0;"></div>';
}
function skypeChatInit(){
	/* функция инициализации */
	if(document.getElementById('chat') != null){
		if(document.getElementsByClassName('ytd-message-renderer')[0] == null){
			video = document.getElementsByTagName('video')[0];
			html5pl = document.getElementsByClassName('html5-video-player')[0];
			player = document.getElementById('player-container');
			createBtn();
			panel.appendChild(btn);/* возникает ошибка*/
			btn.className="ytp-button";
			btn.addEventListener('click',skypeChatOn);
		};
	};
};
/* после загрузки страницы ждем 1,2 сек и запускаем инициализацию */
window.onload = function(){
	setTimeout(skypeChatInit, 1200);
};
```
