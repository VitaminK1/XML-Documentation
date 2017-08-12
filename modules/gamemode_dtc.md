---
layout: page

category: "모듈"
title:  "코어 부수기 게임"

---

플레이어는 적 팀의 코어를 찾아내야 하며 보통 코어는 용암으로 가득 찬 흑요석 구로 이루어져 있습니다. 용암은 코어가 파괴되기 위해 일정한 거리까지 아래로 누출되어야 합니다. 용암은 맵의 다른 곳에서 사용할 수 없습니다. 그렇지 않으면 가짜로 코어가 유출된 것처럼 꾸밀 수 있기 때문입니다. 이것은 용암을 코어와 멀리 떨어뜨려 놓거나 플레이어에게 양동이를 조합할 수 없게 만들어 방지할 수 있습니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>코어 요소</th>
        <th>설명</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<cores> </cores>' | escape_once}}</code>
          </span>
        </td>
        <td>정의된 모든 코어가 포함된 노드입니다.</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<core> </core>' | escape_once}}</code>
          </span>
        </td>
        <td>
          단일 코어입니다.
        </td>
        <td>
          <span class='label label-default'>코어 하위 요소</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>코어 속성</h5>
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
          <code>id</code>
        </td>
        <td>XML의 다른 위치에서 코어를 참조하는 데 사용되는 고유 식별자입니다.</td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>name</code>
        </td>
        <td>알림 메시지에 사용되는 코어의 이름입니다.</td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>required</code>
        </td>
        <td>
          이 목표가 경기에서 이기기 위해 필요한 지 여부를 지정합니다.
          <br/>
          필요한 모든 목표를 완료한 팀은 점수 또는 Blitz설정에 관계없이 승리합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>
          참
        </td>
      </tr>
      <tr>
        <td>
          <code>region</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          <span class='label label-danger'>필수</span>
          코어를 포함하는 지역입니다.
        </td>
        <td>
          <a href='/modules/regions'>경계 지역</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>leak</code>
        </td>
        <td>용암이 누출되어야 하는 코어 <strong>지역</strong>의 바닥 아래 거리</td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td>5</td>
      </tr>
      <tr>
        <td>
          <code>material</code>
        </td>
        <td>파괴를 감지하고 모드 변경에 사용되는 코어 표면 재료를 나타냅니다.</td>
        <td>
          <a href='/reference/inventory#material_matchers'>단일 재료 패턴</a>
        </td>
        <td>흑요석</td>
      </tr>
      <tr>
        <td>
          <code>team</code>
        </td>
        <td>
          <span class='label label-danger'>필수</span>
          코어가 속한 팀, 즉 소유자를 말합니다.
        </td>
        <td>
          <a href='/modules/teams'>팀 ID</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>mode-changes</code>
        </td>
        <td>
          이 코어가 <a href='/modules/monument_modes'>모뉴먼트 모드</a>를 사용하는지 여부를 지정합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>show</code>
        </td>
        <td>
          플레이어에게서 보이는 모든 위치에서 목표를 숨겨야하는지 여부를 지정합니다. 이 위치에는 채팅, 보스바 및 스코어보드가 포함됩니다.
          <br/>
          <code>참고:</code>
          목표는 데이터베이스에 기록되지 않으며 플레이어는 목표를 완료하더라도 보상을 받지 못합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>참</td>
      </tr>
      <tr>
        <td>
          <code>proximity-metric</code>
        </td>
        <td>
          코어의 근접한 정도를 결정하는 데 사용되는 방식입니다.
          <br/>
          사용 가능한 값: <code>closest player</code>, <code>closest block</code> 혹은 <code>closest kill</code>
        </td>
        <td>
          <span class='label label-primary'>근접도</span>
        </td>
        <td>
          <code>closest player</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>proximity-horizontal</code>
        </td>
        <td>
          코어의 근접 거리에 대한 수평 거리만 계산합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
    </tbody>
  </table>
</div>
<h5>코어 하위 요소</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>요소</th>
        <th>설명</th>
        <th>값</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<region>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          <span class='label label-danger'>필수</span>
          코어를 포함하는 지역입니다.
        </td>
        <td>
          <a href='/modules/regions'>경계 지역</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
    <cores material="obsidian" leak="8">
        <core team="blue">
            <region><cuboid min="10,15,12" max="12,13,16"/></region>
        </core>
    </cores>

    <cores material="obsidian" leak="4">
        <core team="red" region="red-core"/>
    </cores>
