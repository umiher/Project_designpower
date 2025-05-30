<div align="center">
<h1>Project_Design Power 📖</h1>
이 프로젝트는 기업을 소개하기 위한 반응형 웹 사이트로 제작되었습니다.
</div>

<br>

<image width="100%" src="main.png"></image>

📄 View : https://project-designpower.vercel.app/

<br>
<br>

## 💡 Stacks
<p>
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?&style=for-the-badge&logo=JavaScript&logoColor=white"/>
<img src="https://img.shields.io/badge/html5-E34F26?&style=for-the-badge&logo=HTML5&logoColor=white"/>
<img src="https://img.shields.io/badge/CSS3-1572B6?&style=for-the-badge&logo=CSS&logoColor=white"/>
</p>

> **JavaScript와 SiwperJS 라이브러리를 이용하여 리뉴얼 웹 페이지를 제작하고,**
> <br>
> **ScrollTrigger 라이브러리를 이용해 사이트가 스크롤에 반응하는 사이트를 구현하였습니다.**


<br>
<br>

## 🔖 주요 특징
### 1. Main : 
```c
let naviControl=document.querySelectorAll(".swiper-navi .swiper-pagination-switch");

const mainSwiper=new Swiper(".main-swiper", {
	speed: 1000,
	loop: true,
	effect: "fade",
	/*
	autoplay: {
		delay: 3000
	},
	*/
	pagination: {
		el: ".swiper-navi .swiper-pagination",
		type: "progressbar"
	},
	on: {
		init: function(){
			naviControl.forEach(function(item, i){
				if(i == this.realIndex){
					item.classList.add("active");
				}
				else{
					item.classList.remove("active");
				}
			});
		},
		slideChangeTransitionStart: function(){
			naviControl.forEach(function(item, i){
				if(i == this.realIndex){
					item.classList.add("active");
				}
				else{
					item.classList.remove("active");
				}
			});
		}
	}
});

naviControl.forEach(function(item, i){
	item.addEventListener("click", function(){
		mainSwiper.slideToLoop(i);
	});
});
```

<br>

> **swiperJS 기능을 활용하여 이미지 슬라이더를 구현하였습니다.**
> <br>
> **pagination을 적용하여 슬라이더 순서를 알려주는 네비게이션 역할을 설정하였습니다.**

<br>
<br>

### 2. GSAP :
```c
const tl1=gsap.timeline({
	scrollTrigger: {
		trigger: ".pin1",
		scrub: 1,
		pin: ".pin1",
		start:"top top",
		end: "+=300%"
	}
});

tl1.to(".sec2 .title-m", { color: "#fff", duration: 4 })
.to(".sec2 .color", { alpha: 0, duration: 4, delay: -3 })
.to(".sec2 .white", { alpha: 1, duration: 4, delay: -4 })
.to(".sec2 .image", { alpha:1, duration: 4, delay: -4 })
.to(".sec2 .title1", { alpha: 0, duration: 2, delay: 1 })
.to(".sec2 .title2", { alpha: 1 , duration: 2, delay: 1 })
.to(".sec2 .title2 p span", { y: 0, duration: 3, delay: 1 });
```

<br>

> **GSAP 라이브러리를 사용하여 자연스러운 애니메이션 효과를 구현하였습니다.**

<br>
<br>

### 3. Mobile Navigation :
```c
tab.addEventListener("click", function(e){
	e.preventDefault();

	if(header.classList.contains("menu-open") == false){
		header.classList.add("menu-open");

		menuLi.forEach(function(item){
			if(item.classList.contains("open") == true){
				item.classList.remove("open");
			}
		});
	}
	else{
		header.classList.remove("menu-open");
	}
});

dimmed.addEventListener("click", function(){
	header.classList.remove("menu-open");
});

menuLi.forEach(function(item, i){
	item.addEventListener("mouseenter", function(){
		if(device == "mobile") return;

		header.classList.add("on");

		for(let j=0; j<menuLi.length; j++){
			if(j == i){
				menuLi[j].classList.add("on");
			}
			else{
				menuLi[j].classList.remove("on");
			}
		}
	});
});

header.addEventListener("mouseleave", function(){
	if(device == "mobile") return;

	header.classList.remove("on");
});

menuLi.forEach(function(item, i){
	item.addEventListener("click", function(e){
		if(device == "desktop") return;

		e.preventDefault();

		if(e.currentTarget.classList.contains("open") == false){
			for(let j=0; j<menuLi.length; j++){
				if(j == i){
					menuLi[j].classList.add("open");
				}
				else{
					menuLi[j].classList.remove("open");
				}
			}
		}
		else{
			e.currentTarget.classList.remove("open");
		}
	});
});

function resizeFunction(){
	let winw=window.innerWidth;

	if(winw < 1281){ // mobile
		if(device == "mobile") return;
		device="mobile";
	}
	else{ // desktop
		if(device == "desktop") return;
		device="desktop";
	}
}

resizeFunction();

window.addEventListener("resize", function(){
	if(header.classList.contains("menu-open")){
		header.classList.remove("menu-open");
	}

	resizeFunction();
});
```

<br>

> **Tab을 이용하여 Mobile Menu를 구현하였습니다.**

<br>
<br>


