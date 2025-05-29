<div align="center">
<h1>Project_Design Power 📖</h1>
이 프로젝트는 기업을 소개하기 위한 반응형 웹 사이트로 제작되었습니다.
</div>

<br>
<br>

<image width="100%" src="header.png"></image>

<br>
<br>

## 💡 Skills
<p>
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?&style=for-the-badge&logo=JavaScript&logoColor=white"/>
<img src="https://img.shields.io/badge/html5-E34F26?&style=for-the-badge&logo=HTML5&logoColor=white"/>
<img src="https://img.shields.io/badge/CSS3-1572B6?&style=for-the-badge&logo=CSS&logoColor=white"/>
</p>

<br>
<br>

## 🔖 주요 특징
### 1. Main : 
```
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

initHeader();
initTopMove();
initFamilySite();
```

<br>
<br>

## 📂 주요 프로젝트
### 1. Design Power 리뉴얼
- 기술스택 : JavaScript, GSAP, Mobile Navigation, HTML, CSS3
- 상세설명 :
  * Design Power는 기업을 소개하기 위한 반응형 웹 사이트로 제작
  * GSAP 라이브러리를 사용하여 자연스러운 애니메이션 효과 구현

<br>

### 2. O'kitchen 리뉴얼
- 기술스택 : JavaScript, SwiperJS, Google Maps API, Mobile Navigation, HTML5, CSS
- 상세설명 :
  * HTML, CSS, JavaScript를 활용하여 반응형 웹 디자인과 모바일 내비게이션 기능을 제공
  * Google Maps API와 Swiper.js를 이용해 동적인 지도 표시와 슬라이더 효과 등을 구현

<br>

### 3. Wylie 리뉴얼
- 기술스택 : JavaScript, GSAP, HTML, CSS3
- 상세설명 :
  * GSAP를 활용하여 스크롤 애니메이션 및 다양한 UI구현
  * 직관적인 네비게이션, 모바일 메뉴, 위치 기반 시각적 효과로 모바일과 웹에서 최적화된 사용자 경험을 제공

<br>
<br>

## 💬 Contact
#### E-mail : uumih98@gmail.com
