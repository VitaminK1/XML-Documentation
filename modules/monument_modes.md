---
layout: page

category: "모듈"
title:  "모뉴먼트 모드"

---

이 모듈은 코어 및 파괴 가능 물질이 순환하는 모드를 사용자 정의하는 데 사용할 수 있습니다. 모뉴먼트 모드가 변경되면 대개 재료가 단단한 블럭에서 단단하지 않은 블럭으로 변경됩니다.

`<modes>`태그는 기간이 다른 임의의 `<mode>`태그를 포함할 수 있습니다. 각 `<mode>` 태그는 그것을 정의할 수 있는 특성을 가지고 있습니다.

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
            <code>{{'<modes> </modes>' | escape_once}}</code>
          </span>
        </td>
        <td>이 경기의 모뉴먼트 모드를 포함한 노드입니다.</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<mode/>' | escape_once}}</code>
          </span>
        </td>
        <td>개별 모뉴먼트 모드입니다.</td>
        <td>
          <span class='label label-default'>없음</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>모드 속성</h5>
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
          <code>after</code>
        </td>
        <td>
          <span class='label label-danger'>필수</span>
          이 모드가 적용될 때 까지 게임 시작부터 걸리는 시간을 나타냅니다.
        </td>
        <td>
          <a href='/reference/time_periods'>시간 단위</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>material</code>
        </td>
        <td>
          <span class='label label-danger'>필수</span>
          변경될 코어 / 파괴 가능 물질의 재료를 나타냅니다.
        </td>
        <td>
          <a href='/reference/inventory#material_matchers'>단일 재료 패턴</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>name</code>
        </td>
        <td>모드 변경 알림에 사용되는 사용자 정의 모드 이름입니다.</td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>show-before</code>
        </td>
        <td>
          모드가 변경되기 전에 보스바에 표시되는 시간입니다.<br/>
          <code>show-before</code>이 0으로 설정되면 모드는 보스바에 전혀 표시되지 않습니다.
        </td>
        <td>
          <a href='/reference/time_periods'>시간 단위</a>
        </td>
        <td>
          60초
        </td>
      </tr>
    </tbody>
  </table>
</div>

예시

    <modes>
        <mode after="10m" material="gold block"/>
    </modes>

게임시작 10분이 지나면 영향을 받는 목표의 재료를 금 블럭으로 변경하는 모드를 지정합니다.

    <modes>
        <mode after="5m" material="coal block" name="`e쉬운 모드"/>
    </modes>

게임 시작 10분이 지나면 영향을 받은 목표의 재료를 석탄 블럭으로 변경하는 모드를 지정합니다. 다음 채팅 메시지가 표시됩니다: `> > > 쉬운 모드 < < <`

`참고:` 목표가 모드를 변경하려면 요소 태그에 `mode-changes="true"`가 있어야 합니다.

    <destroyables name="Monument" materials="obsidian" mode-changes="true">
        <!-- 파괴 가능 물질 -->
    </destroyable>
