[번역] jquery_coding_standard 제이쿼리 코딩 표준

2014.11.22

번역 : [공잠](https://medium.com/@jeongwooahn), 스키머

깃 허브 :
[https://github.com/witinweb/jquery_coding_standard](https://github.com/witinweb/jquery_coding_standard)

원문 :
[http://lab.abhinayrathore.com/jquery-standards/](http://lab.abhinayrathore.com/jquery-standards/)

### jQuery 로딩하기

1.여러분의 페이지에 jQuery를 삽입할 때 항상 CDN을 사용하도록 하십시요. [CDN을 사용해야하는 7가지
이유](https://www.sitepoint.com/7-reasons-to-use-a-cdn/)


[여기](http://lab.abhinayrathore.com/jquery-standards)에 가장 인기있는 jQuery CDN 리스트가
있습니다.

2.위 예시 처럼 여러분의 로컬 호스트에 동일한 버전의 대체 코드를 마련해두는 것이 좋습니다. [더
보기](http://css-tricks.com/snippets/jquery/fallback-for-cdn-hosted-jquery)

3.위 예시 처럼 [상대적 프로토콜](http://www.paulirish.com/2010/the-protocol-relative-url)
URL(http:또는 https:를 제거)을 사용하십시요.

4.가능하다면, 자바스크립트와 제이쿼리 파일들을 페이지 하단에 삽입하십시요. [더 많은
정보](http://developer.yahoo.com/blogs/ydn/high-performance-sites-rule-6-move-scripts-bottom-7200.html)
그리고 [HTML5
Boilerplate](https://github.com/h5bp/html5-boilerplate/blob/master/index.html)

5.어떤 버전을 사용해야하나?

-만약 여러분이 인터넷 익스플로러 6/7/8을 지원해야 한다면 2.x 버전을 사용하지 마십시요.

-호환성 이슈가 있는 플러그인을 사용하지 않는 새로운 앱의 경우 가장 최신 버전을 사용하는 것을 강하게 권합니다.

-CDN을 통해 제이쿼리를 로딩하고자 할때 항상 정확한 버전의 숫자를 기입하십시오(예: *1.11.0* as opposed to *1.11*
or just *1*).

-여러개의 버전을 동시에 로드하지 마십시오.

-제이쿼리 CDN으로 로드하고자 할때
[jquery-latest.js](http://t.umblr.com/redirect?z=http://blog.jquery.com/2014/07/03/dont-use-jquery-latest-js/&t=YWY4NjE2MzMwZjFmZTBkYjUwYjI5ZGYzY2ZiYjM0YTI3MTE0YTZjYSxGclh2Z0pYVg==&b=t:38afnIjGKgKLdaQ_X_rQaA&m=1)를
사용하지 마십시요.

6.만약 $ 표시를 사용하는 Protorype, MooTools, Zepto 등과 같은 라이브러리와 함께 사용한다면 제이쿼리 함수를 호출하기
위해 $를 사용하는 대신 jQuery를 사용하십시요. $.noConflict()를 호출함으로서 $의 제어를 다른 라이브러리에게 양보할 수
있습니다.

7.고급 브라우저 기능 탐지를 할 수 있는 [Modernizr](http://modernizr.com/)를 사용하십시요.

### 제이쿼리 변수

1.제이쿼리 객체로 저장/캐쉬 하기위해 사용되는 모든 변수는 이름 앞에 $가 있어야 합니다.

2.재사용을 위해 항상 객체를 반환하는 제이쿼리 선택자를 변수에 담아 사용하십시요.


3.변수의 이름은 [캐멀 케이스 표기법](http://en.wikipedia.org/wiki/CamelCase)을 사용하십시요.

### 선택자

1.가능하면 ID 선택자를 사용하세요. document.getElementById()를 이용하여 처리하기 때문에 더 빠릅니다.

2.클래스 선택자를 사용할 때에는 선택자의 요소 타입을 쓰지
마십시요.[성능비교](http://jsperf.com/jqeury-selector-test)


3.Id의 자식 내 집합을 선택하기 위해서 find를 사용하세요. 아래 예제에서 볼 수 있듯이 아이디 선택자는 Sizzle 선택자
엔진(제이쿼리가 사용하는 선택자 엔진)을 거치지 않기 때문에 .find()로 접근하는 것이 더 빠릅니다. [더
보기](http://learn.jquery.com/performance/optimize-selectors)


4.오른쪽편에 사용할 선택자를 명시하고 나머지는 왼쪽에 위치시킵니다.(가능하면 가장 오른쪽에는 tag.class형식으로 쓰고 왼쪽에는 그냥
tag나 .class를 쓰세요.) [더
보기](http://learn.jquery.com/performance/optimize-selectors)


5.복잡한 표현 방식은 피합니다. [더
보기](http://learn.jquery.com/performance/optimize-selectors) , [성능
비교](http://jsperf.com/avoid-excessive-specificity)


6.선택자에 범위를 기제합니다.


7.유니버셜 선택자(*) 사용을 피합니다. [더
보기](http://t.umblr.com/redirect?z=http://learn.jquery.com/performance/optimize-selectors/&t=YzViYTE5MTU3MzNkN2Q2OWI0Y2RiMjZlYzE2MjE1ZDI2NDgwNjRmMyxGclh2Z0pYVg==&b=t:38afnIjGKgKLdaQ_X_rQaA&m=1)


8.암시적인 전체 선택자는 피합니다. 셀렉터를 누락시켰을 때, 전체 선택자(*)를 여전히 내포하게 됩니다. [더
보기](http://t.umblr.com/redirect?z=http://learn.jquery.com/performance/optimize-selectors/&t=YzViYTE5MTU3MzNkN2Q2OWI0Y2RiMjZlYzE2MjE1ZDI2NDgwNjRmMyxGclh2Z0pYVg==&b=t:38afnIjGKgKLdaQ_X_rQaA&m=1)


9.ID를 선택할 때 중복 또는 다중 선택하지 마세요. document.getElementById를 사용하여 처리되기 때문에 다른선택자와
혼용하지말고 오직 ID선택자만 사용합니다.


### DOM 조작

1.항상 조작하기 전에 기존 요소를 분리하고 조작 후 다시 연결합니다. [더
보기](http://t.umblr.com/redirect?z=http://learn.jquery.com/performance/detach-elements-before-work-with-them/&t=ZDJiNmM1OWU4N2UzMjcwNDc1NzBhY2Q5MmVlMTgwNWU5ZTRhZWEwMyxGclh2Z0pYVg==&b=t:38afnIjGKgKLdaQ_X_rQaA&m=1)


2..append() 보다 array.join() 또는 문자열 연결을 사용하세요. [더 보기
](http://t.umblr.com/redirect?z=http://learn.jquery.com/performance/append-outside-loop/&t=MTQ5MWUzMjkxNmM3OGQxNGU4N2IwZGI5YTEwZjdhM2IyNjc2NGQxZCxGclh2Z0pYVg==&b=t:38afnIjGKgKLdaQ_X_rQaA&m=1)성능
비교:
[http://jsperf.com/jquery-append-vs-string-concat](http://t.umblr.com/redirect?z=http://jsperf.com/jquery-append-vs-string-concat&t=MmJkN2YyYTVlM2E5YWIzZWM4ZjU1ZjQ5MTJiMGExMTFlYmY1ODg5NixGclh2Z0pYVg==&b=t:38afnIjGKgKLdaQ_X_rQaA&m=1)


3.요소의 존재를 확인하고 실행하세요. [더
보기](http://t.umblr.com/redirect?z=http://learn.jquery.com/performance/dont-act-on-absent-elements/&t=MmEzMjUzYTExZmU4YWJjNWZjZTRkYzAyZmJmZDMzYTU2YTQxNTA4MSxGclh2Z0pYVg==&b=t:38afnIjGKgKLdaQ_X_rQaA&m=1)


### Events

1.하나의 페이지에서는 Document Ready 핸들러를 한 번만 사용하십시요. 디버깅을 더 쉽게해주고 동작의 흐름을 추적할 수 있습니다.

2.이벤트에 익명함수를 사용하지 마십시오. 익명함수는 디버깅, 유지보수, 테스트 또는 재사용을 어렵게 합니다. [더
보기](http://t.umblr.com/redirect?z=http://learn.jquery.com/code-organization/beware-anonymous-functions/&t=MDg1NjdmNDZkMzhkNDIzZTAwY2JhNzNlNDZhZTFmOWRlYTNiOGJiYSxGclh2Z0pYVg==&b=t:38afnIjGKgKLdaQ_X_rQaA&m=1)


3.이벤트 핸들러를 익명함수로 만들지 마십시오. 다시말하지만 익명함수는 디버깅, 유지보수, 테스트 또는 재사용을 어렵게 합니다.


4.이벤트 핸들러를 외부 파일로 삽입시킬 수도 있습니다. 그리고 인라인 자바스크립트는 초기 설정 후 ready 핸들을 호출하는 데 사용할 수
있습니다.


5.HTML에 동적 마크업을 사용하지 마십시오(JavaScript inlining), 이것은 디버깅의 악몽입니다. 항상 일관되게 제이쿼리로
이벤트를 바인드하면 이벤트를 동적으로 붙이거나 제거하기 쉽습니다.


6.가능하면 이벤트의
[네임스페이스](http://t.umblr.com/redirect?z=http://api.jquery.com/event.namespace/&t=M2VjZjc1MTFhZmQyNmQzZWVkNzEyM2RhNDcxNDI4NjA0OWQ5ZTIyMixGclh2Z0pYVg==&b=t:38afnIjGKgKLdaQ_X_rQaA&m=1)를
커스텀하여 사용하십시오. 돔 엘리먼트에 연결된 다른 이벤트에 영향을 주도록 붙여놓은 이벤트를 정확하게 해제하기가 쉽습니다.


7.여러 요소에 같은 이벤트를 붙이려 할때에는 [이벤트
위임](http://t.umblr.com/redirect?z=http://learn.jquery.com/events/event-delegation/&t=YTc1MTU5YTNmN2QzYzg2ZjdlZWUwMWViZWEyNjJkNDcwYWM1MzVjZSxGclh2Z0pYVg==&b=t:38afnIjGKgKLdaQ_X_rQaA&m=1)을
사용하십시오. 이벤트 위임은 하나의 부모 엘리먼트에 하나의 이벤트 리스터 만을 붙이며 이것으로 선택자와 매칭되는 모든 자손에게(그 자손이 지금
존재하든지 미래에 추가되던지 간에) 이벤트가 일어나게 됩니다.


### 아작스

1.*.getJson()*이나 *.get()*의 사용을 피하고 $.ajax()를 사용하십시요.

2.*https* 사이트에서 *http*를 사용하지 마십시오. 스키마 없는 URL을 더 선호합니다.(여러분의 URL에서 *http/https*
프로토콜을 제거하세요.)

3.request 파라미터에 붙이지 말고 데이터 객체 설정을 사용하여 전달하십시오.


4.*dataType*을 기입하는 것이 좋습니다. 어떤 종류의 데이터가 오고가는지 알기 더 쉽습니다.

5.Ajax로 로딩된 컨텐츠에 이벤트를 붙이기 위해서 위임된 이벤트 핸들러를 사용하세요. 위임된 이벤트는 나중에 document에 추가된
자식요소들에게도 이벤트를 진행시킬 수 있는 이점이 있습니다.[더
보기](http://t.umblr.com/redirect?z=http://api.jquery.com/on/#direct-and-delegated-events&t=NTk2MzQ3YWM2NGJiZjY5YjZiMzlhNjNjNjEwNjY2NzE5NGYzNjVkNCxGclh2Z0pYVg==&b=t:38afnIjGKgKLdaQ_X_rQaA&m=1)


6.Promise 인터페이스를 사용하세요: [예제 더
보기](http://t.umblr.com/redirect?z=http://www.htmlgoodies.com/beyond/javascript/making-promises-with-jquery-deferred.html&t=NDgwZGQ4NDZmOTlmOTVlOGZkMTAwNDg3MmY0ODhlZjUwMzljOWU3NCxGclh2Z0pYVg==&b=t:38afnIjGKgKLdaQ_X_rQaA&m=1)


7.Ajax 템플릿 샘플: [더
보기](http://t.umblr.com/redirect?z=https://api.jquery.com/jQuery.ajax/&t=YzBkMDQ0NTRiZDczOGVmY2ZiNTAzN2U4MTRiNWRkZmU0NWJlMThmOSxGclh2Z0pYVg==&b=t:38afnIjGKgKLdaQ_X_rQaA&m=1)


### 효과와 애니메이션

1.애니메이션 기능을 구현하기위해 절제되고 일관된 접근 방법을 채택하십시오.

2.UX 요구사항이 있기 전에 애니메이션 효과를 과도하게 하지 마십시오.

-토글 요소를 위해 show/hide, toggle 그리고 slideUp/slideDown 과 같이 간단한 기능을 사용하는것이 좋습니다.

-미리정의된 애니메이션 속도인 “slow”, “fast”를 사용하거나 중간속도를 위해서는 400을 사용하는 것이 좋습니다.

### 플러그인

1.플러그인을 선택할 때는 기술지원, 문서, 테스트 그리고 커뮤니티가 좋은지 따져 선택하십시오.

2.플러그인이 여러분이 사용하는 제이쿼리 버전과 호환되는지 체크하십시오.

3.어떤 공통의 재사용가능한 컴포넌트는 제이쿼리 플러그인으로 구현되야 합니다.[더
보기](http://t.umblr.com/redirect?z=http://lab.abhinayrathore.com/jquery-standards/#jQueryPluginBoilerplate&t=ODYzYTRiNzdmNGQ2ODZkZmE3OTQ3YjhlNjJiMzRkOWJhNjVmMjA5MSxGclh2Z0pYVg==&b=t:38afnIjGKgKLdaQ_X_rQaA&m=1)

### 체인

1.변수를 저장하고 동시에 여러 선택자를 호출하기위한 대안으로 체인을 사용하십시오.


2.체인의 링크가 3개가 넘거나 이벤트 할당으로 복잡해지면 줄바꿈을 하고 들여쓰기를 통해 가독성을 높이십시요.


3.긴 체인으로 변수에 중간 객체를 캐쉬하는 것이 가능해집니다.

### 기타

1.복수의 파라미터는 객체 표현식을 사용하십시오.


2.제이쿼리에 CSS를 혼용하지 마십시오.


3.비추천 메소드를 사용하지 마십시오. 새 버전이 나올때 마다 비추천된 메소드가 있는지 주의깊게 살펴보고 그것들을 사용하지 않도록 하십시오.
[비추천 메소드
리스트](http://t.umblr.com/redirect?z=http://api.jquery.com/category/deprecated/&t=ZjFmYjQ4NTMwOTg1MDdmM2Q1Mzk0OTY3OGY5NWY1YTEzMDY2M2U2MCxGclh2Z0pYVg==&b=t:38afnIjGKgKLdaQ_X_rQaA&m=1)

4.필요하다면 기본 자바스크립트 코드와 제이쿼리를 함께 사용하십시요. 아래 주어진 예제에서 성능차이를 보십시요 :
[http://jsperf.com/document-getelementbyid-vs-jquery/3](http://jsperf.com/document-getelementbyid-vs-jquery/3)


### 자료

* [제이쿼리 성능](http://learn.jquery.com/performance)
* [제이쿼리 학습](http://learn.jquery.com/)
* [제이쿼리 API 문서](http://api.jquery.com/)
* [제이쿼리 Coding Standards and Best
Practice](http://www.jameswiseman.com/blog/2010/04/20/jquery-standards-and-best-practice)
* [제이쿼리 Cheatsheet](http://lab.abhinayrathore.com/jquery-cheatsheet/)
* [제이쿼리 플러그인
표준코드](http://stefangabos.ro/jquery/jquery-plugin-boilerplate-revisited/)

### [스키머(schemr)](https://medium.com/@schemr)

행복한 프론트엔드 개발자
