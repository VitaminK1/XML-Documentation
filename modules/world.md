---
layout: page

category: "모듈"
title:  "월드와 지형"
nav_content:
  - path: "#terrain"
    name: "지형"
  - path: "#internal"
    name: "맵 내부"

---

### 지형 {#terrain}
월드의 지형 생성기는 바닐라 청크 생성기가 사용되는지 여부 및 특정 시드, 월드를 사용하도록 수정할 수 있습니다. 기본적으로 시드가 시드 속성에 지정되지 않으면 각 경기마다 새로운 임의의 시드가 생성됩니다.

바닐라 생성기를 사용하면 기본 마인크래프트 지형 생성기가 null청크를 생성하는 대신 사용됩니다.
평평한 월드와 같은 특정한 월드 규칙은 NBT Editor로 월드의 `level.dat`파일을 편집하여 변경할 수 있습니다. 레벨 데이터 파일의 `RandomSeed`값은 사용되지 않습니다.

`region/`폴더에 없는 모든 청크는 마인크래프트 청크 생성 규칙에 따라 생성됩니다. 즉, 변경한 지형만 월드와 함께 저장하면 됩니다.


`world=""` 속성은 맵의 `region/`과 `level.dat`파일을 포함하는 서브 폴더를 지정하는 데 사용됩니다.
이것은 [조건문](/modules/includes_conditionals#conditionals)과 함께 특정 이벤트를 위한 맵을 자동으로 로드하는 데 사용됩니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>요소</th>
        <th>설명</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<terrain/>' | escape_once}}</code>
          </span>
        </td>
        <td>
          월드 생성기의 속성을 정의하는 노드입니다.
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>
<h5>지형 속성</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>속성</th>
        <th>설명</th>
        <th>값</th>
        <th>기본값</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>world</code>
        </td>
        <td>
          이 맵에서 사용할 레벨 데이터 하위 폴더입니다.
        </td>
        <td>
          <span class='label label-primary'>하위 폴더 이름</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>vanilla</code>
        </td>
        <td>
          이 월드가 바닐라 또는 null청크 생성기를 사용하는 경우 지정합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      <tr>
        <td>
          <code>seed</code>
        </td>
        <td>
          이 월드의 생성 시드입니다.
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>pre-match-physics</code>
        </td>
        <td>
          경기가 시작되기 전에 물이 흐르는 것과 같은 물리적인 현상을 허용합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
    </tbody>
  </table>
</div>
    <terrain vanilla="true" seed="qwerty"/>

    <!-- 크리스마스 월드 조건문 -->
    <if christmas="true">
        <terrain world="christmas"/>
    </if>
    <if christmas="false">
        <terrain world="normal"/>
    </if>

<br/>

### 맵 내부 {#internal}
완전히 실내 또는 지하에 있는 지도는 [기본 맵 요소](/modules/main)에 있는 `internal`속성을 사용할 수 있습니다. 이 속성은 관전자가 실수로 나침반 도구를 사용하여 맵 위에 순간이동하는 것을 방지합니다.
이 작업을 수행하려면 맵의 외부가 최대 건축 가능한 높이 까지 솔리드 블럭으로 채워져야 합니다.

[기본 맵 요소](/modules/main)를 참고하세요
