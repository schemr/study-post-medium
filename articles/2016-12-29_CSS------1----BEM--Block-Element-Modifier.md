# CSS 방법론 (1) — BEM (Block Element Modifier)

![](https://cdn-images-1.medium.com/max/800/1*skBP7rA5aYgb45U63OincQ.png)
<span class="figcaption_hack">BEM([https://en.bem.info/](https://en.bem.info/))</span>

[WSConf](http://wsconf.org/)에서 CSS 방법론(OOCSS, BEM)에 대한 세션을 들으면서 CSS를 작성할때 어떤
방법론을 통해서 작성해 본적이 없었고 그냥 생각나는데로, 또는 다른데서 봤던 형태로 작성하고 있었던거 같다.

id, class명을 작성할때, 항상 고민이였던 부분이 네이밍이였고, 그때그때 떠오르는데로 작성하는 경우가 많았다. 그러다 보니 나중에 이게
어떤놈인지 알기 힘들었고 수정하려면 HTML과 CSS를 다 찾아보아야 했다.

CSS 방법론은 쉽게 유지보수가 가능하게 하고, 재사용 할 수 있도록 구현하며, 쉽게 확장가능하게 하는 공통의 목적을 가지고 있다.

여러 방법론 중에서 BEM과 OOCSS에 대해서 알아보고 어떻게 적용할지 고민해보기로 했다.

먼저 BEM 방법론에 대해서 정리해 보았다.

*****

### 작명규칙(Naming Convention)

* 개발, 디버깅, 유지보수를 위하여 CSS 선택자의 이름을 가능한 한 명확하게 만드는 것이 목표이다.
* 소문자, 숫자 만을 이용해서 작명한다.
* 여러단어의 조합은 하이픈(-)으로 연결하여 작명한다.

### 블록(Block)

* 재사용 할 수있는 기능적으로 독립적인 페이지 구성 요소. HTML에서 블록은 class 속성으로 표시된다.
* 형태(red, big)가 아닌 목적(menu, button)에 맞게 결정해야 한다.
* 블록은 환경에 영향을 받지 않아야 한다. 즉, 여백이나 위치를 설정하면 안된다.
* 태그, id 선택자를 사용하면 안된다.
* 블록은 서로 중첩해서 작성 할 수 있다.
* 예) header, menu, search-form ….

### 요소(Element)

* 블록안에서 특정 기능을 담당하는 부분.
* block__element 형태로 사용 (더블 언더바)
* 형태(red, big)가 아닌 목적(item, text, title)에 맞게 결정해야 한다.
* 요소는 중첩해서 작성 할 수 있다.
* 요소는 블록의 부분으로만 사용 할 수 있고 다른 요소의 부분으로 사용할 수 없다.
* 모든 블록에서 요소는 필수가 아닌 선택적으로 사용한다. 즉 블록안에 요소가 없을 수도 있다.
* 예) menu__item, header__title …

### 수식어(Modifier)

* 블록이나 요소의 모양(color, size..), 상태(disabled, checked..)를 정의한다.
* block__element — modifier, block — modifier 형태로 사용(더블 하이픈)
* 수식어의 **블리언 타입**과 **키-벨류** 타입이 있다.
* 블리언 타입 : 수식어가 있으면 값이 true 라고 가정한다. (form__button — disabled)
* 키-벨류 타입 : 키, 벨류를 하이픈으로 연결하여 표시한다. (color-red, theme-ocean)
* 수식어는 단독으로 사용할 수 없다. 즉 기본 블록과 요소에 추가하여 사용해야 한다. ( class=”**block__element**
**block__element — modifier**”)

### 혼합사용 (Mix)

* block1, block2__element 형태로 사용할 수 있다.
* block2__element 에 여백이나 위치를 지정하고 block1은 독립적으로 유지할 수 있다.
* 예)

    <div class=”header”>

         <div class=”search-form header__search-form”></div> 

    </div>

*****

BEM에 대해서 알아보고 직접 구현을 해보면서 느꼈던 점은 다소 복잡한 클래스 명이지만, 실제로 나중에 클래스명만 보더라도 이게 어떤 용도이고
어떤 형태일지가 그려졌다. 그리고 어짜피 네이밍은 어려운데, 그나마 규칙을 정하고 블록, 요소, 수식어의 목적을 생각하다보니 조금은 네이밍이
수월해졌다.

그리고 BEM은 클래스 명이 길게 이어지다보니 바로 css 로 작성하는것 보다 sass나 less를 이용하는것이 효율적이다.

좀더 체계적으로 관리 할 수 있도록 파일 구조에 대한 설명도 자세히 되어 있으니 밑에 링크를 참고하자.

BEM 방법론은 괴이한 모습으로 거부감이 들 수 있고, 엄청 긴 클래스명이 부담 될 수도 있다. 따라서 프로젝트의 규모나 성격에 따라 팀원과
규칙을 정의해서 입맛에 맞게 변형해서 사용하는 것이 효율적일 수 있다.

*****

### 참고

* [BEM](https://en.bem.info/)
* [getBEM](http://getbem.com/)
* [BEM File Structure](https://en.bem.info/methodology/filestructure/)

### [스키머(schemr)](https://medium.com/@schemr)

행복한 프론트엔드 개발자

### [Witinweb](https://medium.com/witinweb?source=footer_card)

웹을 이해하고 웹에 wit를 불어넣는 놀이터
