---
layout: page

category: "모듈"
title:  "모뉴먼트 부수기 게임"

---

플레이어는 흑요석 기둥과 같은 적 팀의 특정 물체를 찾아서 파괴해야 합니다. 팀은 적 팀의 파괴 가능 물질이 특정 퍼센트만큼 파괴되면 승리합니다. 팀은 여러 개의 파괴 가능 파괴 가능 물질을 가질 수 있으며 여러 가지 물질로 만들 수 있습니다.

완료는 모뉴먼트 지역 안의 물질이 파괴된 것으로 계산되기 위해 제거되어야 하는 물질의 양을 말합니다. 예를 들어 모뉴먼트가 흑요석이고 완료가 100%로 설정된 경우 모뉴먼트가 파괴된 것으로 간주되기 위해서는 모든 흑요석을 제거해야 합니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>파괴 가능 물질 요소</th>
        <th>설명</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<destroyables> </destroyables>' | escape_once}}</code>
          </span>
        </td>
        <td>정의된 모든 파괴 가능한 것을 포함하는 노드입니다.</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<destroyable> </destroyable>' | escape_once}}</code>
          </span>
        </td>
        <td>
          단일 파괴 가능 물질입니다.
        </td>
        <td>
          <span class='label label-default'>파괴 가능 하위 요소</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>파괴 가능 물질 속성</h5>
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
        <td>XML의 다른 위치에서 모뉴먼트를 참조하는 데 사용되는 고유 식별자입니다.</td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>name</code>
        </td>
        <td>
          <span class='label label-danger'>필수</span>
          파괴 가능 물질의 이름입니다.
        </td>
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
          파괴 가능 물질을 포함하는 지역입니다.
        </td>
        <td>
          <a href='/modules/regions'>경계 지역</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>materials</code>
        </td>
        <td>
          파괴 가능 물질의 재료, 여러개의 재료는 세미콜론으로 구분됩니다.
          <code>;</code>
        </td>
        <td>
          <a href='/reference/inventory#material_matchers'>재료 패턴</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>owner</code>
        </td>
        <td>
          <span class='label label-danger'>필수</span>
          파괴 가능 물질의 주인을 나타냅니다.
        </td>
        <td>
          <a href='/modules/teams'>팀 ID</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>completion</code>
        </td>
        <td>승리를 위해 파괴해야 할 파괴 가능 물질의 양을 나타냅니다(퍼센트)</td>
        <td>
          <span class='label label-primary'>0 - 100</span>
        </td>
        <td>100%</td>
      </tr>
      <tr>
        <td>
          <code>mode-changes</code>
        </td>
        <td>
          이 파괴 가능 물질이 사용자 정의 <a href='/modules/monument_modes'>모뉴먼트 모드</a>를 사용하는지 지정합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      <tr>
        <td>
          <code>show-progress</code>
        </td>
        <td>
          스코어 보드에 파괴 가능 물질의 파괴 진행 상황을 보여줍니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      <tr>
        <td>
          <code>repairable</code>
        </td>
        <td>
          파괴 가능 물질이 수리될 수 있는지 여부를 지정합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>참</td>
      </tr>
      <tr>
        <td>
          <code>sparks</code>
        </td>
        <td>
          파괴된 블럭을 위한 폭죽 입자 및 폭죽 소리를 모든 플레이어에게 들려줍니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
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
      <!--
      <tr>
        <td>
          <code>proximity-metric</code>
        </td>
        <td>
          파괴 가능 물질의 근접한 정도를 결정하는 데 사용되는 방식입니다.
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
          파괴 가능 물질 근접 거리에 대한 수평 거리만 계산합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      -->
    </tbody>
  </table>
</div>
<h5>파괴 가능 물질 하위 요소</h5>
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
          파괴 가능 물질을 포함하는 지역입니다.
        </td>
        <td>
          <a href='/modules/regions'>경계 지역</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
    <destroyables name="Monument" materials="obsidian" completion="100%">
        <destroyable owner="blue">
           <region><cuboid min="46,16,26" max="45,14,25"/></region>
        </destroyable>
        <destroyable owner="red">
           <region><cuboid min="-44,16,-24" max="-45,14,-25"/></region>
        </destroyable>
    </destroyables>
