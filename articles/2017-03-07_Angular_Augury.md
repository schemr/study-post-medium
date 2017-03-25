# Angular 2 디버깅 툴 “Angular Augury”

Angular 2 를 비롯한 SPA 프레임워크를 이용해 개발을 하다보면 디버깅이 쉽지 않아서 고생을 많이 하게 된다. React, Vue 역시
크롬 확장 도구로 디버깅 툴이 있는데, Angular 2 도 찾아보니 [Angular
Augury](https://augury.angular.io/) 라는 이름의 크롬확장도구가 있었다.

![](https://cdn-images-1.medium.com/max/1600/1*zxUTgwfg7DFJRz5mJPv6aw.png)
<span class="figcaption_hack">[Angular Augury](https://augury.angular.io/)</span>

### 설치방법

[Angular Augury](https://augury.angular.io/) 사이트에서 “INSTALL” 버튼을 클릭하면 바로 크롬 확장도구
설치로 이동한다.

아니면 [크롬 웹 스토어](https://chrome.google.com/webstore/category/extensions)에서 angury
를 검색해서 바로 설치할 수 있다.

### 사용방법

Augury 는 개발자도구에 탭 형태로 추가 된다.

![](https://cdn-images-1.medium.com/max/1600/1*ZfCCQBminqYdF_knAM4fhQ.png)
<span class="figcaption_hack">Dev Tools</span>

### 특징

Augury는 컴포넌트 트리와 시각적 도구를 통해 어플리케이션 구조를 파악하기 쉽다.

#### Tree 탭

* Component Tree : 앱의 전체 컴포넌트의 구조를 한눈에 볼 수 있다. 각 컴포넌트를 클릭하면 속성(properties)과
구조(Hierarchy, Graph)를 확인할 수 있다.
* Router Tree : 앱의 라우트 구조를 도식화 하여 보여준다.
* NgModules : AppModule, BrowserModule, FormsModule, HttpModule 등 루트 모듈과 라이브러리 모듈,
피처모듈의 자세한 정보를 확인할 수 있다.

#### 소스파일로 이동

유용한 기능중에 하나는 소스파일로 이동이 가능하다.

컴포넌트 트리에서 왼쪽에 선택한 컴포넌트의 상세 정보가 표시 된다.

위의 이미지에서 보이는 를 클릭하면 해당 컴포넌트의 소스맵 파일로 이동합니다.

여기서 breakpoint 를 걸어서 디버깅을 할 수 있다.

#### 의존성(dependency) 확인 및 조작

컴포넌트의 의존성에 대한 확인과 조작이 쉽다.

<span class="figcaption_hack">Augury Guide 내 이미지</span>

컴포넌트에 사용되고 있는 서비스, 디렉티브 등과 상태를 확인할 수 있고, 값을 변경하여 확인할 수 있다.

이외에 다양한 기능을 제공하는데 모든 특징과 상세 설명은 [Augury
Guide](https://augury.angular.io/pages/guides/)에서 확인 가능하다.

*****

규모가 커지면 커질수록 디버깅에 대한 필요성이 크고, 앱의 성능과 유지보수에도 꼭 필요하다. 그리고 Augury 를 확인하다보니 Angular
2 의 구조와 동작에 대해서도 조금은 이해도가 생기는것 같다. Angular 2 를 개발한다면 꼭 사용하는걸 추천한다.

* [Angular 2](https://medium.com/tag/angular-2?source=post)
* [Debugging](https://medium.com/tag/debugging?source=post)
* [Augury](https://medium.com/tag/augury?source=post)

### [스키머(schemr)](https://medium.com/@schemr)

행복한 프론트엔드 개발자
