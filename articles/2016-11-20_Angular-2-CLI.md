# Angular 2 CLI 로 프로젝트 시작하기

![](https://cdn-images-1.medium.com/max/800/1*ZiJgzPilviOINztnFEDVRw.png)
<span class="figcaption_hack">Angular CLI 사이트</span>

[Angular 2 CLI](https://cli.angular.io/) 는 기본 구조, 컴포넌트 생성, 빌드, 유닛테스트, 개발서버, 배포를
관리 할 수 있도록 도와주는 커멘드라인 인터페이스 입니다. cli를 이용해서 프로젝트를 시작하는 방법을 알아보겠습니다.

*****

### 필수 사항

Angular CLI는 Node 4 이상, NPM 3 이상에서 가능합니다.

### Angular CLI 설치

    npm install -g angular-cli

### 프로젝트 생성 (ng new)

    ng new [프로젝트명]

기본 구조, 컴포넌트 생성, 빌드, 유닛테스트, 개발서버, 배포에 관련된 모든 의존성 라이브러리를 설치합니다.

### 개발서버 실행 (ng serve)

    cd [프로젝트명]

    ng serve

Webpack 빌드과정이 끝나면 [http://localhost:4200](http://localhost:4200/) 접속하면 개발서버를 확인할
수 있습니다.

### 컴포넌트, 디렉티브, 서비스, 파이프 생성(ng generate)

Angular CLI 에서는 컴포넌트, 디렉티브, 서비스, 파이프의 생성을 쉽게 할 수 있습니다.

새로운 컴포넌트를 생성하려면 아래의 명령어를 입력하면 됩니다.

    ng generate component [컴포넌트명] 또는,
    ng g component [컴포넌트명]

src/app/[컴포넌트명] 아래 4개의 파일이 생성됩니다.

    [컴포넌트명].component.css
    [컴포넌트명].component.html
    [컴포넌트명].component.spec.ts
    [컴포넌트명].component.ts

디렉티브, 서비스, 파이프, 클래스 등 같은 형태로 쉽게 폴더 구조 및 파일을 생성할 수 있습니다.

<span class="figcaption_hack">ng generate</span>

### 테스트(ng test)

    ng test

카르마를 통한 유닛테스트를 진행하고 결과를 확인할 수 있습니다.

### 빌드(ng build)

    ng build

dist/ 폴더에 실제 서비스를 위한 파일이 생성됩니다.

*****

Angular CLI 를 통해서 프로젝트를 생성하고, 개발서버, 컴포넌트 생성, 테스트, 빌드 명령어를 간략히 살펴보았습니다. 자세한 내용은
[github](https://github.com/angular/angular-cli) 를 참고하세요

아직 Angular CLI는 베타 버전이므로, 당분간 많은 변화와 발전 가능성이 높습니다. Router 관련된 기능도 추가될 예정이라고 합니다.

### [스키머(schemr)](https://medium.com/@schemr)

행복한 프론트엔드 개발자

### [Witinweb](https://medium.com/witinweb?source=footer_card)

웹을 이해하고 웹에 wit를 불어넣는 놀이터
