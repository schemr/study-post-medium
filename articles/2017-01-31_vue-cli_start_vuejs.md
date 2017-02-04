# Vue-CLI 로 Vue.js 시작하기 (browserify / webpack)

React, AngularJS 와 함께 최근 가장 뜨거운 프레임워크가 Vue.js 인것 같다. [공식
문서](https://kr.vuejs.org/)가 한글 번역되어 있어 너무나 쉽게 시작할 수 있고, 상대적으로 진입장벽이 조금 낮다.

![](https://cdn-images-1.medium.com/max/1600/1*11dpXFZgKDYZ6o2mZn1xUQ.png)
<span class="figcaption_hack">[Vue.JS 한글 사이트](https://kr.vuejs.org/)</span>

Vue를 처음 접한다면 먼저 공식문서에 [시작하기](https://kr.vuejs.org/v2/guide/#시작하기)에 있는[ JSFiddle
Hello World 예제](https://jsfiddle.net/chrisvfritz/50wL7mdz/)나 [velopert님의
블로그](https://velopert.com/)의 [Vue.js 2.0 소개 및 시작하기](https://velopert.com/3007)를
통해서 어떻게 동작하는지 맛보는걸 추천한다. 특히 velopert님도 언급했듯이 공식문서의 [다른 프레임워크와의
비교](https://kr.vuejs.org/v2/guide/comparison.html) 글은 꼭 읽어보길 추천한다.

이 글에서는 [vue-cli](https://github.com/vuejs/vue-cli) 를 통해서 빠르게 기본환경 세팅 및 개발서버,
테스트, 빌드에 대해서 알아보겠다. (vue-cli
[v2.8.0](https://github.com/vuejs/vue-cli/releases/tag/v2.8.0) 기준)

*****

### 설치

최소 요구사항으로 Node.js 4.x 이상(6.x 추천)과 [Git](https://git-scm.com/) 이 설치되어 있어야 한다.

    // vue-cli 전역 설치, 권한에러시 sudo 추가
    npm install -g vue-cli

### 프로젝트 생성

    // vue init <template-name> <project-name>
    vue init webpack my-project

정말 간단하게 webpack 과 vue 프로젝트를 시작할 수 있다. 아래의 템플릿중에서 필요에 따라 선택하여 생성하면 된다.

### 템플릿

vue-cli 에서는 미리 세팅된 몇가지 템플릿을 제공한다. 제공되는 템플릿은
[vuejs-templates](https://github.com/vuejs-templates) 에 각각의 레퍼로 저장되어 있다.  명령어를
통해서 제공되는 템플릿 리스트를 확인할 수 있다.

![](https://cdn-images-1.medium.com/max/1600/1*XnACPcDU_RONvoTr-X9YfQ.png)
<span class="figcaption_hack">vue list 목록</span>

#### [browserify](https://github.com/vuejs-templates/browserify)

    vue init browserify test-vue

Browserify+vueify 조합으로 hot-reload, linting(ESLint), unit testing(karma-jasmine)
지원 템플릿 (설치시 사용여부 선택)

> [vueify](https://github.com/vuejs/vueify) 는 Browserify 변환을 위한 하나의 Vue 컴포넌트 이다.

#### [browserify-simple](https://github.com/vuejs-templates/browserify-simple)

빠른 프로토타이핑을 위한 간단한 Browserify+vueify 조합 템플릿 (hot-reload 포함)

#### [simple](https://github.com/vuejs-templates/simple)

    vue init simple test-vue

하나의 index.html 파일 생성 (script 포함)

#### [webpack](https://github.com/vuejs-templates/webpack)

webpack+vue-loader 조합으로 hot-reload, linting(ESLint), unit testing(karma+mocha),
e2e test([Nightwatch](http://nightwatchjs.org/)) 지원 템플릿

설치시 선택사항

* ESLint preset : [Standard](https://github.com/feross/standard),
[AirBNB](https://github.com/airbnb/javascript), none (사용자 설정)
* unit test (Karma + Mocha) (Yes/No)
* e2e test ([Nightwatch](http://nightwatchjs.org/)) (Yes/No)

> [vue-loader](https://github.com/vuejs/vue-loader) 는 webpack 에서 사용하는 Vue 컴포넌트 로더
> 이다.

#### [webpack-simple](https://github.com/vuejs-templates/webpack-simple)

빠른 프로토타이핑을 위한 간단한 webpack+vue-loader 조합 템플릿 (hot-reload 포함)

### 개발서버, 빌드, 테스팅(Webpack 템플릿)

    // 기본 템플릿중 webpack 템플릿
    vue init webpack vue-project
    cd vue-project

    // npm 패키지 설치
    npm install

#### npm run dev

* 컴파일, ESLint 과정을 거치고 로컬서버로 페이지를
실행시켜준다([http://localhost:8080/](http://localhost:8080/))
* 코드 수정후 저장하면 ESLint, hot-reload 동작(변경된 상태만 변경)
* Source maps 설정

#### npm run build

* /dist 폴더에 Production 파일 생성
* JavaScript([UglifyJS](https://github.com/mishoo/UglifyJS2)),
HTML([html-minifier](https://github.com/kangax/html-minifier)) 최소화
* 하나의 CSS 파일로 최소화([cssnano](https://github.com/ben-eb/cssnano))
* 모든 정적 파일은 파일명에 hash값이 추가되고 index.html에 자동으로 hash가 포함된 URL이 추가

<span class="figcaption_hack">dist 폴더 struncture</span>

<span class="figcaption_hack">index.html (minifier, hash URL)</span>

#### npm run unit

* 단위 테스트는 Karma + Mocha + karma-webpack 으로 PhantomJS에서 실행
* /test/unit/specs 에 정의된 테스트 코드가 실행된다.

#### npm run e2e

* end to end 테스트는 [Nightwatch](http://nightwatchjs.org/) 로 실행
* [Nightwatch](http://nightwatchjs.org/).js 는 Selenium / WebDriver 서버에서 실행되는
Node.js 기반의 e2e 테스트 솔루션
* /test/e2e/specs 에 정의된 테스트 코드가 실행된다.
* Selenium server 는 Java 환경에서 실행되므로 최소 7버전 이상의 Java SE Development Kit이 필요

*****

Vue.js 는 React, Angular와 충분히 경쟁할 만큼 문서와 CLI를 보면 개발자의 편의를 위해서 많은 노력을 한 것 같다.

또 하나 공부해야 할 프레임워크가 늘어난 것 같아서 마음이 무겁기도 하지만, 웹 프레임워크가 빠르게 발전하고 있는건 설레이는 일인것 같다.

얼마 전까지만해도 웹팩 설정을 하는데만 수많은 삽질을 했었는데 지금은 그런 노력들이 줄어들고 있는것도 반가운 일이다.

React, Angular 를 시작할 엄두가 나지 않았다면 Vue 로 시작해 보는것도 괜찮은 선택일것 같다.

### [스키머(schemr)](https://medium.com/@schemr)

행복한 프론트엔드 개발자

### [Witinweb](https://medium.com/witinweb?source=footer_card)

웹을 이해하고 웹에 wit를 불어넣는 놀이터
