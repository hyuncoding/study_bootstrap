## 헷갈리거나 정리가 필요한 내용

### Grid 관련

-   `col-xs-숫자`는 가장 작은 화면(스마트폰 등) 너비에 맞게 grid가 css로 설정된 클래스이다.
-   `col-sm-숫자`는 그 다음 사이즈, `col-md-숫자`는 그 다음 사이즈이며, 가장 큰 건 `col-lg-숫자`이다.
-   만약 md 사이즈와 lg 사이즈 둘 다 같은 grid를 적용하고 싶다면 `col-md-숫자`만 작성하면 된다. 즉, 작은 것 기준.

### Responsive Column Resets

-   .visible-(사이즈)-(block, inline, inline-block): 설정한 사이즈에서만 설정한 형태(블록, 인라인...)로 보이게 하는 것.
-   .hidden-(사이즈): 설정한 사이즈에서만 숨기는 것.

-   **다만, 현재는 deprecated 되었다.**
-   따라서 이제는 아래와 같이 사용한다.
-   hidden-xs -> d-none d-sm-block
-   hidden-sm -> d-block d-sm-none d-md-block
-   hidden-md -> d-block d-md-none d-lg-block, ...
-   즉, 숨길 tier에 d-(사이즈)-none을 적용한 후, 나머지에 block을 주면 된다.
-   이때, Grid 관련 에서 적어놓았듯 더 큰 사이즈는 별다른 지시가 없을 경우 overwrite된다는 걸 명심하자.

### Offsetting, Ordering, and Nesting Columns

-   .offset-(사이즈)-(이동할 개수): 이동할 개수만큼 열을 이동하며, 설정한 사이즈에 적용된다.
-   .order-(사이즈)-(순서): 순서에 맞게 열을 배치하며, 설정한 사이즈에 적용된다.

### Badges

-   .badge와 .bg-(속성들 중 1개) 를 함께 span태그의 클래스에 작성할 경우 적용된다.
-   이전에는 .label이었으나 label태그와 혼동 우려로 인해 변경되었다.
-   cf) .text-dark는 글씨를 검정색으로 출력한다.

### Card

-   기존의 well, panel 등은 card로 대체되었다.
-   card-body 안에 card-title과 card-subtitle을 넣으면 깔끔하게 디자인할 수 있다.

### Jumbotron

-   기존의 Jumbotron은 bg-light 등 다양한 컴포넌트의 추가로 인해 삭제되었다.
-   기존과 동일한 방식으로 만들기 위해서는 `bg-light p-5 rounded-lg m-3`를 사용하면 된다.
-   위 언급한 클래스를 가진 div태그를 container 클래스 div태그 안에 넣을 경우 너비가 작아지며, 반대로 container div를 위 div 태그 안에 넣을 경우 full-screen width가 된다.

### Page-header

-   삭제되었다.
-   다만, 아래와 같이 구현하거나,

          .page-header {
                  padding-bottom: 9px;
                  margin: 40px 0 20px;
                  border-bottom: 1px solid #eee;
              }

-   `pb-2 mt-4 mb-2 border-bottom` 을 클래스로 부여하여 container div 안에 넣음으로써 가능하다.

### 텍스트 관련

-   `lead`: p 태그 등에 클래스로 부여하여 강조할 수 있다.
-   `text-left, text-center, ...`
-   `text-capitalize`: 각 단어의 첫 글자를 대문자로 표시한다.
-   `text-(muted, primary, success, ...)`, `bg-(primary, success, ...)`: 글자색 또는 배경색 변경

### Table

-   table 태그를 감싸는 div 태그의 클래스에 table-responsive를 부여할 경우,  
    반응형 화면에서 해당 테이블에 따로 가로 스크롤바가 생기며 스크롤이 편해진다.
-   하지만 내부적으로 overflow-y: hidden을 사용하므로 조심하자.

### Form

-   `form-group`, `form-row`, `form-inline` 클래스들은 Bootstrap 5에서 모두 deprecated 되었다.
-   따라서 `form-group`은 `mb-3`로 (margin-bottom: 1rem),  
    `form-row`는 `row`로,  
    `form-inline`은 `d-flex flex-row align-items-center flex-wrap`으로 대체한다.
-   control들에는 `form-control`을 작성한다.

-   특정 control에 대해 너비 등 속성을 부여하고 싶다면, id를 주어 id 선택자로 css를 따로 부여하자!

-   form 태그 안에 read-only text를 넣을 때 기존의 `form-control-static`은 `form-control-plaintext`로 대체되었다.

### Screen Reader 관련

-   screen reader 과 관련하여 `sr-only` 와 `sr-only-focusable` 은 각각,  
    `visually-hidden`과 `visually-hidden-focusable`로 변경되었다.

### 버튼 관련

-   `btn-default`(얕은 회색)은 `btn-outline-secondary`로 대체되었다.
-   버튼의 사이즈는 `btn-(lg, sm, xs)`로 설정한다.
-   버튼의 너비는 동일한 방식으로 `col-(숫자)`로 설정할 수 있다. 다만, `container` div 태그 안에 있어야 한다.

-   `btn-group`으로 버튼태그를 하나의 outline 안에 묶을 수 있다.

### Selectbox 관련

-   `optgroup` 태그로 `option`들을 그룹화할 수 있다.
-   그룹화된 `option` 태그들은 들여쓰기된다.
-   그룹마다 스타일 따로 부여하기 좋을듯.

### input-group

-   `input-group`으로 `span`과 `input` 태그를 묶을 수 있으며, span태그에 `input-group-text` 클래스를  
    부여하여 input 태그 왼쪽에 grey 배경으로 된 별도의 박스 형태로 붙일 수 있다.
-   이 때 span 태그 안에 또 다른 input(checkbox, radio 등)을 넣을 수 있다.

### Validations

-   `is-valid`(기존 `has-success`)와 `is-invalid`(기존 `has-error`)를 input태그 클래스로 부여하여  
    테두리 및 아이콘을 표시할 수 있다.
-   이는 기존의 `has-feedback` 클래스, 즉 아이콘을 표시해주는 클래스의 기능까지 포함하는 것이다.

### Images

-   기존의 `img-rounded`, `img-circle`은 대체되었다.
-   `rounded`를 사용하거나, 원형을 원할 경우 `rounded-circle ratio ratio-1x1`을 사용한다.
-   `img-thumbnail`을 부여하면 이미지 주변에 얇은 테두리가 생긴다.

### Media

-   기존의 `media`관련 클래스들은 모두 삭제되었다.
-   하지만 여러 클래스를 활용하여 같은 형태의 레이아웃을 만들 수 있다.
-   `media` -> `d-flex`
-   `media-left` -> `flex-shrink-0`
-   `media-object` -> 삭제
-   `media-body` -> `flex-grow-1 ms-3`

### Glyphicons

-   Bootstrap에서 제공하는 아이콘들이다.
-   현재는 bootstrap-icons 라는 이름으로 변경되었으며, Bootstrap 5 를 직접 설치하더라도  
    별도로 cdn 방식이든, npm 방식이든 import 해야한다.
-   cdn 방식 import:

          <link
              rel="stylesheet"
              href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.5.0/font/bootstrap-icons.css"
          />

-   i태그의 클래스에 `bi bi-(아이콘명)`을 작성하고, 색상은 style="color: (색상);"으로 작성한다.

### Navigations

-   `nav`태그 안에 `div class="collapse navbar-collapse"` 태그를 넣고,  
    `ul class="navbar-nav"`를 넣은 후, 해당 ul 태그의 클래스에 디자인적인 속성을 부여한다.
-   ul태그 안에 `li role="presentation" class="nav-item"`을 넣고, 그 안에는 `a class="nav-link"`를 넣는다.
-   a태그에는 `active` 클래스를 부여하여 처음부터 활성화시킬 수 있으며, 다른 a 태그들은 hover 시 활성화된다.

-   `navbar-default`는 `navbar-light` 또는 `navbar-dark`로 대체되었다.
-   `navbar-fixed-top`은 `fixed-top`으로 대체되었다.
-   `navbar-toggle`, `navbar-toggle collapsed`, `icon-bar`은 `navbar-toggler` 및 `navbar-toggler-icon`으로 대체되었다.

### Dropdown

-   먼저 Popper.js 를 import 해야한다.
-   Popper.js 링크:

          <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/2.9.2/umd/popper.min.js"></script>

-   아래와 같은 방식으로 dropdown을 간편하게 구현할 수 있다.

          <div class="dropdown">
                  <button
                      type="button"
                      class="btn btn-outline-secondary dropdown-toggle"
                      data-bs-toggle="dropdown"
                      aria-expanded="false"
                      id="dropdownMenuButton1"
                  >
                      Choose One...
                  </button>
                  <ul class="dropdown-menu">
                      <li><a href="#" class="dropdown-item">Item 1</a></li>
                      <li><a href="#" class="dropdown-item">Item 2</a></li>
                      <li><a href="#" class="dropdown-item">Item 3</a></li>
                      <li><a href="#" class="dropdown-item">Item 4</a></li>
                  </ul>
              </div>

-   중간에 divider를 만들고 싶을 경우, `li class="dropdown-divider"`를 추가한다.

### 글자색 또는 배경색 관련 주의점

-   CSS 우선순위로 인해 text-(muted, primary, ...) 와 bg-(primary, success, ...)에서  
    override될 수 있으므로, 아래 방법으로 하는 게 더 권장된다.
-   텍스트를 담고 있는 `span`태그에 text-_ 클래스를 부여하고, 이를 감싸는 `div`태그에 bg-_ 클래스를 부여한다.

### data-api

-   data-toggle 속성에 tooltip을 부여하면 버튼으로 툴팁을 표시할 수 있다.
-   이때 `data-html="true"`를 준 후,  
    `data-delay=(지연시간)`, `data-bs-trigger="click"`, `title="툴팁내용"` 등을 사용한다.
-   해당 기능을 사용하지 않으려면 아래와 같이 작성하면 된다.

          <script>
              $(document).off('.data-api');
          </script>

-   혹은, tooltip 등 특정 기능만 막으려면 아래와 같이 작성한다.

          <script>
              $(document).off('.tooltip.data-api')
          </script>

-   특정 태그 객체에 tooltip 기능을 활성화하려면 아래와 같이 작성한다.

          $('#class-name').tooltip('toggle');

### Modals

-   `.modal-header`: 모달창의 맨 윗부분에 들어갈 내용 작성. 닫기(`.close`) 버튼이 들어갈 자리.
-   `.modal-title`: 모달창의 제목
-   `.modal-body`: 모달창의 내용
-   `.modal-footer`: 모달창의 아랫부분. 확인/취소 버튼이 들어갈 자리.

-   `data-bs-toggle="modal"`을 부여하고, `data-bs-target` 속성의 값으로 표시할 모달 div태그의 id값을 부여한다.(`#` 포함)

### nav-tabs

-   `nav nav-tabs` 클래스를 가진 ul 태그 안에 `nav-item` 클래스를 가진 li 태그를 넣고, `nav-link` 클래스를 가진 a 태그를 넣으면 된다.
-   활성화시킬 탭에는 `active` 클래스를 부여한다.

### scrollspy

-   scroll event에 따라 nav의 특정 탭을 활성화하거나, nav의 특정 탭을 클릭하여 특정 부분으로 스크롤되도록 구현할 수 있다.
-   스크롤할 요소에 아래 속성들을 부여한다.

          .(클래스명) {
              position: relative;
              height: (높이);
              overflow: auto;
          }

-   이 중에서 중요한 건 `position: relative`이다.
-   또한 각 탭의 a태그 `href`를 스크롤할 요소의 id값으로 부여한다.
-   스크롤할 요소들을 감싸는 태그에 `data-bs-spy="scroll"`을 부여하고,  
    `data-bs-target`에 해당 navbar의 id를 적어준다.
-   키보드로 손쉽게 이동할 수 있도록 `tabindex="0"`을 부여해주면 좋다.

### Tooltips

-   툴팁을 표시할 버튼 태그에 `data-bs-toggle="tooltip"`을 작성한다.
-   툴팁 내용은 `title`속성에 부여한다.
-   `data-bs-placement`로 툴팁 표시 위치를 해당 태그 기준으로 조절할 수 있다.
-   `data-bs-trigger`로 클릭 또는 hover 등으로 툴팁 표시를 제어할 수 있다.

### Popover

-   popover 또한 tooltip과 비슷하지만 좀 더 세부 내용을 담을 수 있다.
-   제목과 내용을 모두 담을 수 있다.
-   `data-bs-toggle="popover"`를 부여하면 된다.
-   제목은 `title`, 내용은 `data-bs-content`에 작성한다.

### tooltip과 popover 관련 세부 내용

-   페이지가 로드되자마자 표시하고 싶다면 아래와 같이 JS 코드를 작성한다.

          document.addEventListener("DOMContentLoaded", function () {
                  // Initialize tooltips
                  var tooltipTriggerEl = document.getElementById("tooltipButton");
                  var tooltip = new bootstrap.Tooltip(tooltipTriggerEl);
                  // Show tooltip
                  tooltip.show();

                  // Initialize popovers
                  var popoverTriggerEl = document.getElementById("popoverButton");
                  var popover = new bootstrap.Popover(popoverTriggerEl);
                  // Show popover
                  popover.show();
              });

-   즉 각 툴팁 또는 popover 요소에 대하여,  
    객체로 가져와 trigger로 담고, 해당 trigger를 `boostrap.Tooltip()`생성자에 전달한다.
-   이후 해당 생성자로 만들어진 객체에 `show()` 메소드를 사용하여 표시하면 된다.

### 버튼 로딩 표시, 토글 버튼, 선토글 버튼

-   bootstrap5 부터는 jQuery에 의존하지 않으므로, 순수 Javascript로 구현할 수 있다.

          document
                  .getElementById("{버튼태그의 id}")
                  .addEventListener("click", function () {
                      var button = this;
                      button.disabled = true;
                      button.innerHTML =
                          '<span class="spinner-border spinner-border-sm" role="status" aria-hidden="true"></span> Loading...';

                      // Simulate a network request
                      setTimeout(function () {
                          button.disabled = false;
                          button.innerHTML = "Loading state";
                      }, 2000); // 2 seconds delay for demonstration
                  });

-   즉 button에 `disabled`를 부여한 뒤 spinner를 innerHTML로 넣어주고,  
    setTimeout()으로 원하는 시간(위: 2s) 후에 다시 원래 상태로 돌아오도록 하는 코드다.
-   해당 부분(setTimeout())에 전달하는 콜백함수 안에서 통신을 수행할 수 있을듯.

-   `data-bs-toggle="button"`을 부여하면 토글 버튼을 만들 수 있으며,  
    이때 class에 `active`를 부여하고 시작하면 페이지 로드 시 선토글된다.

### Alert 박스(js의 alert()와 다름)

-   버튼 태그의 클래스에 `alert` 및 `alert-(success, warning, ...)`등을 부여하고, `role="alert"`를 부여하여 만들 수 있다.
-   이때 사용자가 없앨 수 있게 하려면 button태그를 추가한다.

          <button
                      type="button"
                      class="btn-close"
                      data-bs-dismiss="alert"
                      aria-label="Close"
                  ></button>

### 진행도(Progress bar)

-   `<div class="progress">` 태그 안에 `<div class="progress-bar">` 태그를 넣고, 해당 태그의  
    style 속성에서 `width: (진행도)%;`를 부여해준다.
-   그리고 해당 태그에 라벨을 달고 싶을 경우 innerText로 넣어주면 된다.

-   마찬가지로 색상 변경 등을 위해 `progress-bar` 뒤에 `bg-warning`이나 `progress-bar-striped` 등을 부여할 수 있다.

-   Bootstrap 3 까지는 `progress-bar`에 `active`를 부여하여 애니메이션 효과를 줄 수 있었지만,  
    5버전에서는 별도로 아래와 같이 구현해야 한다.

            <style>
                @keyframes progress-bar-stripes {
                    0% {
                        background-position-x: 1rem;
                    }
                    100% {
                        background-position-x: 0;
                    }
                }

                .progress-bar.active {
                    -webkit-animation: progress-bar-stripes 2s linear infinite;
                    animation: progress-bar-stripes 2s linear infinite;
                }
            </style>

### Collapse

-   a태그에 버튼 관련 클래스를 부여한 뒤, `data-bs-toggle="collapse"`를 부여한다.
-   그리고 href 속성에 토글에 따른 표시를 원하는 태그의 id를 #과 함께 적어준다.
-   마찬가지로 표시될 부분에도 클래스로 `collapse`를 부여한다.

### Accordion

-   collapse와 비슷하지만, 아코디언은 여러 개의 collapse 요소가 있을 때  
    하나를 클릭 시 나머지는 다시 숨김처리되는 요소다.
-   `data-bs-toggle="collapse"`를 버튼에 부여하고, 해당 버튼에 `data-bs-target=` 속성에 표시하고자 하는 태그의 id를 #과 함께 적어준다.
-   class는 `accordion-button`으로 한다.
-   `accordion-header`로 헤더 효과를 줄 수 있다.
-   그리고 각 collapse에는 `accordion-item`을 부여하는데, 이때 전체를 감싸는 div태그에 `accordion`클래스를 주고 id를 따로 부여한다.
-   각 collapse요소에서 토글표시하고자 하는 부분에는 `accordion-collapse collapse`를 부여하고, 미리 표시하고자 할 경우 `show`도 부여한다.
-   그리고 `data-bs-parent`에 전체를 감싸는 `accordion`클래스가 부여된 div태그의 id를 #과 함께 적는다.

### Carousels (슬라이드 배너)

-   슬라이드 배너를 bootstrap에서는 carousel이라고 부른다.
-   구현이 굉장히 간단하고 간편하다.
-   part03/hour20_01.html에 있는 코드로 웬만한 건 다 구현 가능하다.
-   `carousel-indicators`를 부여한 태그는 편리한 이동을 위한 버튼이며,  
    `carousel-caption`으로 배너 이미지 아랫쪽에 글을 작성할 수 있다.
-   `data-bs-interval`은 슬라이드 간격(delay 시간)이며 각 요소마다 다르게 설정도 가능하다.
-   왼쪽 및 오른쪽 버튼 또한 `carousel-inner` 클래스를 가진 태그 다음에 button 태그 2개로 작성할 수 있다.

-   `data-bs-interval="false"`로 작성하면 자동 슬라이드를 방지할 수 있다.
-   `data-bs-touch="false"`로 작성하면 모바일 화면 등 터치로 이동하는 걸 방지할 수 있다.

-   참고로, **배너 안에 마우스를 hover하고 있을 경우 자동슬라이드는 방지된다.**
