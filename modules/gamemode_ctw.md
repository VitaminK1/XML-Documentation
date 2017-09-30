---
layout: page

category: "모듈"
title:  "양털 쟁탈 게임"

---

플레이어는 맵의 적 팀의 측면에서 양털을 회수해야 하고 그것들을 승리 모뉴먼트에 올려 놓아야 합니다. 양털이 있는 부분은 기본적으로 다른 블럭으로 차단되지 않도록 보호되어야 합니다.

    <wools>
        <wool team="blue" color="lime">
            <monument><block>0.5,11,-92.5</block></monument>
            <!-- 블루 팀이 승리하기 위해서는 0.5,11,-92.5에 연두색 양털을 놓아야 합니다. -->
        </wool>
        <wool team="green" color="light blue" craftable="false">
            <monument><block>0.5,11,93.5</block></monument>
            <!-- 하늘색 양털은 조합할 수 없으며 직접 가져와야 합니다. -->
        </wool>
    </wools>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>양털 요소</th>
        <th>설명</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<wools> </wools>' | escape_once}}</code>
          </span>
        </td>
        <td>이 맵에 대한 모든 양털을 포함하는 노드입니다.</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<wool> </wool>' | escape_once}}</code>
          </span>
        </td>
        <td>
          양털 승리 모뉴먼트입니다.
        </td>
        <td>
          <span class='label label-default'>양털 하위 요소</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>양털 속성</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>속성</th>
        <th>설명</th>
        <th>값</th>
        <th style='min-width: 63px;'>기본값</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>id</code>
        </td>
        <td>XML의 다른 위치에서 양털 모뉴먼트를 참조하는 데 사용되는 고유 식별자입니다.</td>
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
          경기에서 이기기 위해 이 목표가 필요한지 여부를 지정합니다.
          <br/>
          필요한 모든 목표를 완료한 팀은 점수 또는 Blitz 설정에 관계없이 승리합니다.
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
          <code>team</code>
        </td>
        <td>
          <span class='label label-danger'>필수</span>
          양털을 놓아야 하는 팀입니다.
        </td>
        <td>
          <a href='/modules/teams'>팀 ID</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>color</code>
        </td>
        <td>
          <span class='label label-danger'>필수</span>
          양털의 색깔입니다.
        </td>
        <td>
          <a href='/reference/colors'>염료 색깔 이름</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>monument</code>
        </td>
        <td>
          <span class='label label-default' data-toggle='tooltip' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          <span class='label label-danger'>필수</span>
          양털을 놓아야 하는 모뉴먼트를 설정합니다.
        </td>
        <td>
          <a href='/modules/regions'>지역</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>craftable</code>
        </td>
        <td>양털을 조합할 수 있는지를 설정합니다. (예: 흰 양털과 염료)</td>
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
          목표가 플레이어에게 보이는 모든 위치에서 숨겨져야 하는지 여부를 지정합니다. 이 위치는 채팅, 보스바 및 스코어보드가 포함됩니다.
          <br/>
          <i>만약 false로 설정하면 목표는 데이터베이스에 기록되지 않으며 플레이어는 목표를 완료하여도 보상을 받지 못합니다.</i>
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>참</td>
      </tr>
      <tr>
        <td>
          <code>location</code>
        </td>
        <td>
          <span class='label label-danger' title='프로토콜 버전 1.3.4 이후 필수 항목'>필수</span>
          양털을 찾을 수 있는 위치, 접근 알림을 결정하는 데 사용됩니다.
        </td>
        <td>
          <span class='label label-primary'>X,Y,Z</span>
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>
<h5>양털 하위 요소</h5>
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
            <code>{{'<monument>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' data-toggle='tooltip' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          <span class='label label-danger'>필수</span>
          양털이 놓여야 하는 모뉴먼트를 설정합니다.
        </td>
        <td>
          <a href='/modules/regions'>지역</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>

하나의 `<wools team="team-id">` 요소 안에 여러 팀의 승리 모뉴먼트를 그룹화 할 수 있습니다. `<wool>` 요소 내부에서 팀이 개별 앙털 색상을 정의할 수 있습니다.

    <wools team="red">
        <wool color="cyan" location="32.5,14,0.5">
            <monument><block>-60,26,-118</block></monument>
        </wool>
        <wool color="lime" location="0.5,10,21.5">
            <monument><block>-60,26,-121</block></monument>
        </wool>
    </wools>

    <wools team="blue">
        <wool color="magenta" location="-32.5,14,0.5" monument="magenta-monument"/>
        <wool color="lime" location="0.5,10,21.5" monument="lime-monument"/>
    </wools>
