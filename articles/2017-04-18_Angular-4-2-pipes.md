# [Angular 4 (2)] Pipes 에 대해서

![](https://cdn-images-1.medium.com/max/1600/1*E4FoEv67VFa8cMWQIl2TkQ.png)

Angular 를 학습하면서 정리 목적의 포스팅으로 첫번째 내용은 Pipe 이다.

Pipe의 사용법, 내장 Pipe, 커스텀 Pipe 구현방법에 대해서 정리하였다.

### 작성 버전

* Angular 4.0.0
* Angular CLI 1.0.0

### Pipe 란?

Pipe 는 템플릿에서 값의 표시되는 형태를 변환해서 보여주기 위해서 사용한다.

AngularJS 에서는 Filter 라는 이름으로 불렸고, 파이프( | ) 를 사용하는 방법은 동일하다.

예를들어 날짜 데이터(Sun Apr 16 2017 17:35:39 GMT+0900 (KST))를 원하는 포멧(2017.4.16)으로 보여줄 수
있다.

### 사용법

HTML 마크업 상에서 변환하고자 하는 데이터에 다음과 같은 형태로 사용한다. (다른 Pipe를 연결해서 사용가능하고, 옵션은 콜론(:)을
연결해서 사용)

    {{ value | PipeName : customOption1 :  customOption2 }}
    {{ value | Pipe1 | Pipe2 }}

예)

    <p>오늘은 {{ today | date:“yyyy.MM.dd”}} 입니다.<p> 
    // input) today = Sun Apr 16 2017 17:35:39 GMT+0900 (KST)
    // output) 오늘은 2017.4.16 입니다

    <p>{{ text | slice:0:3 | uppercase }}</p>
    // input) text = 'abcdefghijk'
    // output) 'ABC'

### 내장 Pipe

![](https://cdn-images-1.medium.com/max/1600/1*KN0gyP7g7C0H05tP8Fjr9A.png)
<span class="figcaption_hack">[내장 Pipe](https://angular.io/docs/ts/latest/api/#!?query=pipe)</span>

[Angular Doc API Reference](https://angular.io/docs/ts/latest/api/#!?query=pipe)
에서 pipe 로 검색하면 기본적으로 제공하는 내장 Pipe 를 볼수 있다. 각 내장 Pipe에 대한 자세한 설명은 위의 링크 문서에서 확인하면
된다.

참고1) 내장 Pipe가 어떻게 만들어져 있는지는 [github
코드](https://github.com/angular/angular/tree/09d9f5fe54e7108c47de61393e10712f8239d824/packages/common/src/pipes)에서
확인

참고2) AngularJS 에서 제공하였던   는 제공되지 않는다. 자세한 내용은 Pipe 문서의
[부록](https://angular.io/docs/ts/latest/guide/pipes.html#!#no-filter-pipe)을 참고

### pure

Pipe는 pure와 impure(pure : false) 두개의 카테고리를 가지고 있다.

pure : Change to a primitive input value (String, Number, Boolean, Symbol) 또는
Changed object reference (Date, Array, Function, Object)) 을 감지할 때만 실행한다. 제한적이지만
빠르다 (예 : date, uppercase, number Pipe)

impure : 모든 변경사항에 대해서 감지하고 실행한다. 따라서 잦은 호출로 인한 사용성에 악영향을 끼칠수 있다. (예 : async,
json, slice Pipe)

예) pure 경우,  라는 배열이 있을때  를 이용해서 추가하게되면 배열의 참조가 변경되는것이 아니고 같은 배열이기 때문에 추가한 는 Pipe
가 적용되지 않는다.

Pipe의 적용을 위해서는 1)  를 이용하게 되면 원시 데이터를 변경한다. 2)  를 추가한다.

### 커스텀 Pipe 구현

입력값을 원하는 자리수(limit)만큼만 표시하고 뒤에 ‘…’ 을 추가하는 Pipe 를 구현하는 것을 예를 들어보겠다.

#### TypeScript (shorten.pipe.ts)

    import { Pipe, PipeTransform } from ‘@angular/core’;

    @Pipe(){
        name: 'shorten'
    }

    transform(value: any, limit: number) {    
        if (value.length > limit) {      
          return value.substr(0, limit) + ' ...';    
        }    
        return value;  
      }

데코레이터를 이용해서 과  여부를 작성한다. (  는 로 설정할 때만 추가)

transform 메소드를 통해서 input value 와 limit 라는 추가 옵션값을 받는다.

입력 값이 limit 수 보다 클 경우에 limit 만큼 자르고 ‘…’ 추가 후 리턴

#### HTML

    <p> {{ content | shorten:3 }} <p>
    // input) content = '안녕하세요 반갑습니다'
    // output) 안녕하세...

### 커스텀 Pipe ([source](https://github.com/schemr/angular4-pipes),
[demo](https://schemr.github.io/angular4-pipes/))

서비스에서 사용 목적으로 간단한 몇개의 Pipe를 구현했고, 계속 추가 예정입니다.

* Shoten : limit 값만큼만 표시하고 ‘…’ 추가 ( | shorten : limit )
* Linkify : 문자열에 포함된 링크, 이메일주소를 a tag 변환 ( | linkify )
* CommaSeparatedNumber : 숫자를 천단위로 구분하여 콤마로 구분하여 표현 ( | commaSeparatedNumber )

* [Angular 4](https://medium.com/tag/angular-4?source=post)
* [Angular Pipe](https://medium.com/tag/angular-pipe?source=post)
* [Angular 2](https://medium.com/tag/angular2?source=post)

### [스키머(schemr)](https://medium.com/@schemr)

행복한 프론트엔드 개발자

### [Witinweb](https://medium.com/witinweb?source=footer_card)

웹을 이해하고 웹에 wit를 불어넣는 놀이터
