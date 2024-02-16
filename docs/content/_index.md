---
aliases:
  - /font/
---

## 설치

Bootstrap Icons은 npm으로 배포되지만 수동으로 다운로드할 수도 있습니다.

<div class="row my-4">
  <div class="col-md-4">
{{< md >}}
### 패키지 관리자
npm 또는 Composer로 SVG, 아이콘 스프라이트, 아이콘 폰트가 포함된 [Bootstrap Icons](https://www.npmjs.com/package/bootstrap-icons)를 설치하세요. 그런 다음에 [사용법](#사용법)에서 아이콘을 포함할 방법을 선택하면 됩니다.

{{< highlight sh >}}
npm i bootstrap-icons
{{< /highlight >}}
{{< highlight sh >}}
composer require twbs/bootstrap-icons
{{< /highlight >}}
{{< /md >}}
  </div>
  <div class="col-md-4">
{{< md >}}
### 다운로드
[모든 버전은 GitHub에 게시되며](https://github.com/twbs/icons/releases/), SVG, 폰트, 라이선스, readme가 포함되어 있습니다. 우리의 개발 워크플로에 주로 사용하는 npm 스크립트가 작성된 `package.json`도 포함되어 있습니다.

<a class="btn btn-outline-primary" href="https://github.com/twbs/icons/releases/latest/">최신 ZIP 다운로드</a>
{{< /md >}}
  </div>
  <div class="col-md-4">
{{< md >}}
### CDN
jsDelivr를 통해서 아이콘 폰트 스타일시트를 웹사이트 내의 `<head>`나 `@import`를 통해 포함시켜서 빠르게 시작하세요. [아이콘 폰트 문서](#아이콘-폰트)에서 예제를 확인할 수 있습니다.

{{< highlight html >}}
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@{{< param version >}}/font/bootstrap-icons.min.css">
{{< /highlight >}}

{{< highlight css >}}
@import url("https://cdn.jsdelivr.net/npm/bootstrap-icons@{{< param version >}}/font/bootstrap-icons.min.css");
{{< /highlight >}}
{{< /md >}}
  </div>
</div>

## 사용법

Bootstrap Icons는 SVG이기 때문에 프로젝트 구성 방식에 따라 몇 가지 방법으로 이를 HTML에 포함시킬 수 있습니다. `font-size`를 통해 쉽게 크기를 조정할 수 있도록 `width: 1em` (및 선택적으로 `height: 1em`)을 사용하는 것이 좋습니다.

<div class="row my-4">
  <div class="col-md-4">
{{< md >}}
### 임베드
아이콘을 (외부 이미지 파일이 아닌) 페이지의 HTML에 임베드합니다. 여기에서는 커스텀 width와 height를 사용하고 있습니다.
{{< /md >}}
  </div>
  <div class="col-md-8">
    {{< example >}}<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-emoji-heart-eyes" viewBox="0 0 16 16"><path d="M8 15A7 7 0 1 1 8 1a7 7 0 0 1 0 14zm0 1A8 8 0 1 0 8 0a8 8 0 0 0 0 16z"/><path d="M11.315 10.014a.5.5 0 0 1 .548.736A4.498 4.498 0 0 1 7.965 13a4.498 4.498 0 0 1-3.898-2.25.5.5 0 0 1 .548-.736h.005l.017.005.067.015.252.055c.215.046.515.108.857.169.693.124 1.522.242 2.152.242.63 0 1.46-.118 2.152-.242a26.58 26.58 0 0 0 1.109-.224l.067-.015.017-.004.005-.002zM4.756 4.566c.763-1.424 4.02-.12.952 3.434-4.496-1.596-2.35-4.298-.952-3.434zm6.488 0c1.398-.864 3.544 1.838-.952 3.434-3.067-3.554.19-4.858.952-3.434z"/></svg>{{< /example >}}
  </div>
</div>

<div class="row my-4">
  <div class="col-md-4">
{{< md >}}
### 스프라이트
SVG 스프라이트를 사용해서 `<use>` 요소로 아이콘을 삽입합니다. fragment 식별자로는 아이콘의 파일명을 사용합니다 (예: `toggles`는 `#toggles`). SVG 스프라이트에서는 `<img>` 요소와 마찬가지로 외부 파일을 참조할 수 있지만, `currentColor`를 이용해서 간단하게 테마를 설정할 수 있습니다.

**주의!** Chrome에서 [`<use>`가 여러 도메인 간에 작동하지 않는 문제](https://bugs.chromium.org/p/chromium/issues/detail?id=470601)가 있습니다.
{{< /md >}}
  </div>
  <div class="col-md-8">

<div class="bd-example" style="font-size: 32px;">
  <i class="bi bi-heart-fill"></i>
  <i class="bi bi-toggles"></i>
  <i class="bi bi-shop"></i>
</div>
{{< highlight html >}}
<svg class="bi" width="32" height="32" fill="currentColor">
  <use xlink:href="bootstrap-icons.svg#heart-fill"/>
</svg>
<svg class="bi" width="32" height="32" fill="currentColor">
  <use xlink:href="bootstrap-icons.svg#toggles"/>
</svg>
<svg class="bi" width="32" height="32" fill="currentColor">
  <use xlink:href="bootstrap-icons.svg#shop"/>
</svg>
{{< /highlight >}}
  </div>
</div>

<div class="row my-4">
  <div class="col-md-4">
{{< md >}}
### 외부 이미지
Bootstrap Icons의 SVG를 지정 디렉토리에 복사하면 일반 이미지처럼 `<img>` 요소로 포함시킬 수 있습니다.
{{< /md >}}
  </div>
  <div class="col-md-8">
    {{< example >}}<img src="/assets/icons/bootstrap.svg" alt="Bootstrap" width="32" height="32">{{< /example >}}
  </div>
</div>

<div class="row my-4">
  <div class="col-md-4">
{{< md >}}
### 아이콘 폰트
각 아이콘의 클래스를 가진 아이콘 폰트도 Bootstrap Icons에 포함되어 있습니다. CSS를 통해 페이지 내에 아이콘 웹 폰트를 넣어 필요에 따라 HTML 내에서 클래스를 사용할 수 있습니다 (예: `<i class="bi-alarm-clock"></i>`).

`font-size`나 `color`를 사용해서 아이콘의 모습을 변경할 수 있습니다.
{{< /md >}}
  </div>
  <div class="col-md-8">
    {{< example >}}<i class="bi-alarm"></i>{{< /example >}}
    {{< example >}}<i class="bi-alarm" style="font-size: 2rem; color: cornflowerblue;"></i>{{< /example >}}
  </div>
</div>

<div class="row">
  <div class="col-md-4">
{{< md >}}
### CSS

CSS 내에서 SVG를 사용할 수도 있습니다 (헥스 색상 값을 지정할 때 `#`은 `%23`로 입력하는 것처럼 **모든 문자를 이스케이프 처리해야 함**). `<svg>`에서 너비와 높이를 통해 크기를 지정하지 않으면 아이콘이 사용 가능한 공간을 채웁니다.

`background-size`로 아이콘의 크기를 조정하려면 `viewBox` 속성이 필요합니다. `xmlns` 속성은 필수 속성입니다.
{{< /md >}}
  </div>
  <div class="col-md-8">
{{< highlight css >}}
.bi::before {
  display: inline-block;
  content: "";
  vertical-align: -.125em;
  background-image: url("data:image/svg+xml,<svg viewBox='0 0 16 16' fill='%23333' xmlns='http://www.w3.org/2000/svg'><path fill-rule='evenodd' d='M8 9.5a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3z' clip-rule='evenodd'/></svg>");
  background-repeat: no-repeat;
  background-size: 1rem 1rem;
}

{{< /highlight >}}
  </div>
</div>

<div class="row my-4">
  <div class="col-md-4">
{{< md >}}
## Styling
`.text-*` 클래스 또는 커스텀 CSS로 색상을 변경할 수 있습니다:
{{< /md >}}
  </div>
  <div class="col-md-8">
    <div class="bd-example">
      <svg class="bi bi-exclamation-triangle text-success" width="32" height="32" fill="currentColor" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
        <path d="M7.938 2.016A.13.13 0 0 1 8.002 2a.13.13 0 0 1 .063.016.146.146 0 0 1 .054.057l6.857 11.667c.036.06.035.124.002.183a.163.163 0 0 1-.054.06.116.116 0 0 1-.066.017H1.146a.115.115 0 0 1-.066-.017.163.163 0 0 1-.054-.06.176.176 0 0 1 .002-.183L7.884 2.073a.147.147 0 0 1 .054-.057zm1.044-.45a1.13 1.13 0 0 0-1.96 0L.165 13.233c-.457.778.091 1.767.98 1.767h13.713c.889 0 1.438-.99.98-1.767L8.982 1.566z"/>
        <path d="M7.002 12a1 1 0 1 1 2 0 1 1 0 0 1-2 0zM7.1 5.995a.905.905 0 1 1 1.8 0l-.35 3.507a.552.552 0 0 1-1.1 0L7.1 5.995z"/>
      </svg>
    </div>
{{< highlight html >}}
<svg class="bi bi-exclamation-triangle text-success" width="32" height="32" fill="currentColor" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
  ...
</svg>
{{< /highlight >}}
  </div>
</div>

<div class="row my-4">
  <div class="col-md-4">
{{< md >}}
## 접근성
아이콘을 장식용으로만 쓴다면 `aria-hidden="true"`를 추가해주세요. 그게 아니라면 적절한 대체 텍스트를 제공해야 합니다. 아이콘을 추가할 때 사용한 방법과 아이콘을 사용하는 위치 (예: 독립 이미지 또는 버튼 또는 유사한 컨트롤의 유일한 컨텐츠)에 따라 다양한 방법이 있습니다. 다음은 몇 가지 예시입니다:
{{< /md >}}
  </div>
  <div class="col-md-8">
    <div class="bd-example">
      <img src="/assets/icons/bootstrap.svg" alt="Bootstrap" width="32" height="32">
    </div>
{{< highlight html >}}
<!-- alt="..." on <img> element -->
<img src="/assets/icons/bootstrap.svg" alt="Bootstrap" ...>
{{< /highlight >}}
    <div class="bd-example">
      <i class="bi-github" role="img" style="font-size: 2em" aria-label="GitHub"></i>
      <i class="bi-tools" role="img" style="font-size: 2em" aria-label="Tools"></i>
    </div>
{{< highlight html >}}
<svg class="bi" ... role="img" aria-label="Tools">
  <use xlink:href="bootstrap-icons.svg#tools"/>
</svg>
{{< /highlight >}}
    <div class="bd-example">
      <button type="button" class="btn btn-primary" aria-label="Mute">
        <svg class="bi bi-volume-mute-fill" width="32" height="32" viewBox="0 0 16 16" fill="currentColor" xmlns="http://www.w3.org/2000/svg" aria-hidden="true"><path d="M6.717 3.55A.5.5 0 017 4v8a.5.5 0 01-.812.39L3.825 10.5H1.5A.5.5 0 011 10V6a.5.5 0 01.5-.5h2.325l2.363-1.89a.5.5 0 01.529-.06zm7.137 2.096a.5.5 0 010 .708L12.207 8l1.647 1.646a.5.5 0 01-.708.708L11.5 8.707l-1.646 1.647a.5.5 0 01-.708-.708L10.793 8 9.146 6.354a.5.5 0 11.708-.708L11.5 7.293l1.646-1.647a.5.5 0 01.708 0z"></path></svg>
      </button>
    </div>
{{< highlight html >}}
<!-- aria-label="..." on the control -->
<button ... aria-label="Mute">
  <svg class="bi bi-volume-mute-fill" aria-hidden="true" ...>
  ...
  </svg>
</button>
{{< /highlight >}}
  </div>
</div>

<div class="row my-4">
  <div class="col-md-4">
{{< md >}}
## SVG로 작업하기
SVG는 작업하기에 훌륭하지만 해결해야 할 몇 가지 알려진 단점이 있습니다. SVG를 사용할 수 있는 방법은 여러가지라는 점을 고려해 이러한 속성과 해결 방법은 코드에 포함하지 않았습니다.
{{< /md >}}
  </div>
  <div class="col-md-8">
{{< md >}}
알려진 문제점:

- **SVG는 Internet Explorer 및 Edge Legacy에서 기본적으로 포커스를 받습니다.** SVG를 포함할 때 `focusable="false"`를 `<svg>` 요소에 추가하세요. [Stack Overflow에서 자세히 알아보세요.](https://stackoverflow.com/questions/18646111/disable-onfocus-event-for-svg-element)

- **`<img>` 요소로 SVG를 사용할 때 스크린 리더는 이를 이미지로 알리지 않거나 이미지를 완전히 건너뛸 수 있습니다.** 문제를 방지하려면 `<img>` 요소에 추가적으로 `role="img"`를 포함시켜야 합니다. [자세한 사항을 이 글에서 확인해보세요.](https://web.archive.org/web/20201112013541/https://simplyaccessible.com/article/7-solutions-svgs/#acc-heading-2)

- **Internet Explorer에서는 외부 SVG 스프라이트가 정상적으로 작동하지 않을 수 있습니다.** 필요하다면 [svg4everybody](https://github.com/jonathantneal/svg4everybody) 폴리필(polyfill)을 사용해보세요.

SVG와 관련된 다른 문제를 발견하셨나요? [이슈]({{< param repo >}}/issues)를 만들어서 세부 사항을 공유해주세요.
{{< /md >}}
  </div>
</div>
