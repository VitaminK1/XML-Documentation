---
layout: page

category: "모듈"
title:  "규칙"

---

규칙 모듈을 사용하여 아비스 네트워크 표준 규칙에 포함되지 않은 사용자 지정 규칙을 맵에 추가할 수 있습니다. 액세스와 차단 규칙을 적용하려면 영역 및 필터를 사용해야 합니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>규칙 요소</th>
        <th>설명</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<rules> </rules>' | escape_once}}</code>
          </span>
        </td>
        <td>정의 된 모든 사용자 정의 규칙을 포함하고 있는 노드입니다.</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<rule> </rule>' | escape_once}}</code>
          </span>
        </td>
        <td>
          사용자 정의 맵 규칙입니다.
        </td>
        <td>
          <span class='label label-primary'>텍스트</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>

예시

    <rules>
        <rule>경기 지역을 숨기거나 나가서 의도적으로 경기를 연장하지 마십시오</rule>
    </rules>
