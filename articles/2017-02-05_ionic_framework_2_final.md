# Ionic 2.0.0 final 요약 (Ionic 2)

지난 2017년 1월 25일 Ionic블로그에 2.0.0 Final 릴리즈에 대한 공지가 올라왔다.

Ionic 2 는 2016.1.26일 첫 alpha버전을 공개 한 후에 딱 1년만에 정식버전을 릴리즈 하였다. ([alpha, beta, rc
총 25번의 릴리즈](https://github.com/driftyco/ionic/releases))

최종 릴리즈는 [Virtual
Scroll](http://ionicframework.com/docs/v2/api/components/virtual-scroll/VirtualScroll/)을
제외하고 크게 추가된 내용은 없었고 정리차원에서 주요 내용에 대해서 간단히 정리하였다.
([원문링크](http://blog.ionic.io/announcing-ionic-2-0-0-final/))

![](https://cdn-images-1.medium.com/max/1600/1*fUTnNvL68WNogno9KcTZ0A.jpeg)
<span class="figcaption_hack">[Ionic 2](http://blog.ionic.io/announcing-ionic-2-0-0-final/)</span>

*****

ionic 2.0.0 은 이미 알고 있는 ionic 2 의 첫 안정화 제품 버전(stable, production version)이다.

### Ionic 2 의 새로운 특징

#### Components

[크로스 플랫폼 컴포넌트](http://ionicframework.com/docs/v2/components/)로 Material 디자인의
100% 지원 (FAB(Float Action Button)포함), 더 유용한 modal, menu, toast, navigation 지원,
그리고 브라우저에서 사용할 수 있는 [DateTime
Picker](http://ionicframework.com/docs/v2/components/#datetime) 와 같은 새로운 폼 컨트롤을
개발하였다.

#### Ionic 2 Native

강력하고 새로운 [native plugin system](http://ionicframework.com/docs/v2/native/)을 지원.
70개가 넘는 네이티브 기능을 Web API 와 같이 사용 할 수 있다.

#### Theming

최소한의 코드로 앱의 모양을 쉽게 커스텀 할 수 있도록 [테마](http://ionicframework.com/docs/v2/theming/)를
새롭게 개편하였다.

Ionic 2 는 iOS, Material Design, Windows 의 세가지 모드를 지원하여 각 플랫폼의 모양과 느낌을 일치시켜서
사용자에게 유사한 경험을 줄 것이다. 각각의 디자인은 Sass 변수를 사용하거나 컴포넌트의 속성을 추가하여 수정할 수있다.

Light 테마가 기본으로 적용되어 있고, 조만간 더 많은 테마를 선보일 예정이다.

#### Website & Docs

Ionic Framework 홈페이지가 새롭게 디자인 되었으며, [문서](http://ionicframework.com/docs/v2/)가 크게
개선되었다.

### 향상된 성능

가장 큰 특징은 하나의 코드베이스로 웹표준과 API를 사용하여 다양한 플랫폼에서 느껴지는 앱을 구축하는데 도움이 된다. 앱 성능과 관련해서
끊임없이 노력하고 있다.

Ionic 2 에서는 더이상 자바스크립트 스크롤을 사용하지 않아 Android, iOS에서 60FPS로 스크롤 된다. 최종 버전에서 추가된
[Virtual
Scroll](http://ionicframework.com/docs/v2/api/components/virtual-scroll/VirtualScroll/)을
사용하면 스크롤 이벤트 기반으로 애니메이션을 적용하고, 큰 이미지 리스트를 스크롤 할 수 있는 앱을 제작할 수 있다.

또한 컨포넌트와 공유되는 새로운 렌더링 파이프 라인은 레이아웃 thrashing 과 repaints를 줄여주고, Web API의 새로운 기능을
사용하여 변경된 뷰 부분만 다시 그린다.

마지막으로 Ionic 2 는 Angular 2 기반으로 구축되었기 때문에 기존의 Angular 1기반보다 훨신 빠르다.

### 새 도구

#### 에러처리

첫번째 rc 버전에서 앱 구축, 테스트, 실행을 도와주는 App Scripts라는 새로운 빌드 도구를 출시 하였고, 에러처리 및 디버깅 기능이
있다.

ionic serve 명령어를 사용하여 컴파일 오류가 발생하면 브라우저에 상세 에러 정보가 표시된다. 이 기능을 통해서 코드 에러를 추적하는데
매우 유용하다.

#### Ionic Serve Lab

브라우저에서 다른 플랫폼을 미리보기 할 수 있다.

    ionic serve --lab

<span class="figcaption_hack">Ionic Serve Lab (ionic blog)</span>

### 제품 출시

Ionic 2.0.0 최종버전 릴리즈로 Ionic 2 제품 출시 준비과 완료 되었고 안정적인 API를 사용할 수 있다. 지속적으로 컴포넌트,
기능, 성능 향상을 위해 노력할 것이며 다만 API의 변경은 크게 없을 것이다.

*****

Ionic 2 를 학습 하고 있고, 실제 제품을 만들어 보고 싶었는데 안정화 버전 릴리즈가 되어 좀더 속도를 내야 겠다.

처음 Ionic 2 를 접한다면 이전에 작성한 [Ionic 2
시작하기](https://medium.com/witinweb/ionic-2-ììíê¸°-ed011c7fe69b#.ryaxk7tna)를
통해서 빠르게 시작해 볼 수 있을 것이라 생각한다.

### 링크

[Announcing Ionic 2.0.0
Final](http://blog.ionic.io/announcing-ionic-2-0-0-final/)

[Ionic 2
시작하기](https://medium.com/witinweb/ionic-2-ììíê¸°-ed011c7fe69b#.ryaxk7tna)

### [스키머(schemr)](https://medium.com/@schemr)

행복한 프론트엔드 개발자

### [Witinweb](https://medium.com/witinweb?source=footer_card)

웹을 이해하고 웹에 wit를 불어넣는 놀이터
