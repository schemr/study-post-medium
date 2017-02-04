# CSS 방법론 (2) — OOCSS(**Object Oriented CSS**)

![](https://cdn-images-1.medium.com/max/800/1*AKO4ykgb--W11BzQDhgarg.png)
<span class="figcaption_hack">[Nicole Sullivan
Slide](http://www.slideshare.net/stubbornella/object-oriented-css/)</span>

[CSS 방법론(1)-BEM 방법론](https://medium.com/@schemr/css-ë°©ë²ë¡
-1-bem-block-element-modifier-1c03034e65a1#.hidm4lf5d)에 이어서 OOCSS 객체지향 CSS 방법론에
대해서 정리해 보았다.

*****

### 2가지 기본원칙

* 구조(structure)와 모양(skin)의 분리 : 반복적인 시각적 기능(배경, 테두리..)을 별도의 “스킨”으로 정의하여 다양한 객체와
혼합하여 중복 코드없이 시각적 다양성을 표현할 수 있다.
* 콘테이너와 콘텐츠의 분리 : 스타일을 정의할때 위치에 의존적인 스타일을 사용하지 않는다. 사물의 모양은 어디에 위치 하던지 동일하게 보인다.
(예: .object h2{} 사용하지 않고 h2에 .title(클래스 이름)을 부여하여 사용한다. 이렇게 하면 클래스가 없는 h2는 모두
동일한 모습이고, title 클래스 역시 동일하게 보일것이며, 불필요한 스타일을 중복해서 정의할 필요가 없다)

### 네이밍 방법

* 가능한 짧고 간결하게 작성한다.
* 동작과 형태가 예상 가능하도록 명확하게 작성한다.
* 어떻게 생겼는지 보다는 어떤 목적인지 알 수 있도록 의미있게 작성한다.
* 지나치게 구체적 이지 않게 일반적으로 사용가능 하도록 작성한다.

### 이점

* 많은 CSS 코드가 재사용되면서 코드의 길이가 줄어든다. 즉 css 파일 크기가 작아져서 속도를 향상 시킬 수 있다.
* 새로운 요소를 추가할때, 기존 모듈을 통해서 재사용이 가능하고 쉽게 확장 가능하여 유지보수성이 높아진다.

### OOCSS 예

* [니콜 설리반의 media
object](http://www.stubbornella.org/content/2010/06/25/the-media-object-saves-hundreds-of-lines-of-code/)
* 소셜 공유 버튼 구현

    // 기존 방식
    <a class=”facebook_btn”>Facebook</a>
    <a class=”twitter_btn”>Twitter</a>

    // OOCSS 적용
    <a class=”btn facebook”>Facebook</a>
    <a class=”btn twitter”>Twitter</a>

    .btn { 공통 버튼 스타일 정의 }

*****

OOCSS는 비판적인 시선이 많았다. 복잡해지는 HTML이 오히려 유지보수를 어렵게 한다라는 의견도 있고, 가독성도 떨어지며, 미디어객체와 같은
일부 모듈에 적용하기 좋아 보이지만 프로젝트 전반적으로 적용하기 어려워 보인다.

OOCSS의 단점을 보완하기 위해서 OOSass(OOCSS+Sass)와 같은 변형된 방법이 제시되었지만, 그닥 매력적이지 않다.

[Airbnb의 스타일가이드](https://github.com/airbnb/css#oocss-and-bem)를 보면 OOCSS 와 BEM
방법론을 혼용하여 사용하고 있다. 스타일시트를 재사용가능한 객체의 모음으로 구성하고, 클래스 이름 규칙을 BEM을 입맛에 맞춰 변형하여
사용한다.(PascalCase)

[BEM 방법론](https://medium.com/@schemr/css-ë°©ë²ë¡
-1-bem-block-element-modifier-1c03034e65a1#.nv72pvz2q), OOCSS 방법론에 대해서 알아보면서
개인적인 생각은 다음과 같다.

* 방법론은 방법론이다. 참고용 이지 바이블이 아니다.
* 재사용가능하고 유지보수를 잘 할수 있는 목적이 중요하다.
* CSS preprocessor(Sass, Less 등) 는 선택이 아니라 필수다.

분명한 점은 앞으로 CSS를 작성할때는 한번 더 생각할 것이고, 고민할 것이다. 나만의 방법론, 팀의 방법론을 만들어 가는것이 중요한것 같다.

### 참고

[OOCSS Github Wiki](https://github.com/stubbornella/oocss/wiki)

[Nicole Sullivan Slide — Object Oriented
CSS](http://www.slideshare.net/stubbornella/object-oriented-css/)

[[번역] 객체 지향 CSS(OOCSS) 소개](http://mytory.net/archives/8949) — mytory

[[번역] OOCSS(객체 지향 CSS)와 Sass를 결합하는 것이 최고의 CSS 코딩 방법이다(OOCSS + Sass = The best
way to CSS)](http://mytory.net/archives/8986) — mytory

### [스키머(schemr)](https://medium.com/@schemr)

행복한 프론트엔드 개발자

### [Witinweb](https://medium.com/witinweb?source=footer_card)

웹을 이해하고 웹에 wit를 불어넣는 놀이터
