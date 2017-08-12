---
layout: page

category: "모듈"
title:  "팀"

---

이 모듈은 경기에 사용된 팀과 그 속성을 지정하는 데 사용됩니다.
팀이 없는 경기는 [플레이어](/modules/players) 모듈을 사용하여 설정할 수 있습니다.

각 팀의 소프트 플레이어 제한은 `max=""` 속성과 `max-overfill`을 가진 하드 제한으로 설정됩니다. 만약 최대 overfill이 정의되지 않은경우 기본값은 최대 팀 크기보다 25% 크게 설정됩니다. 최대 플레이어 overfill크기에 도달하면 플레이어가 팀에 합류할 수 없습니다.

팀의 이름은 `<team>`요소 내에서 지정됩니다. 이름은 "Team"을 포함하지 말고 가능한 한 짧게 유지해야 합니다. (예: "Azure Team" 대신 "Azure")
팀의 `<plural>`속성은 팀 이름이 복수인지 여부를 지정합니다. (예: Attackers); Game 플러그인은 적절한 승리 메시지를 선택하기 위해 이를 사용할것입니다. `show-name-tags` 속성은 플레이어 이름표를 볼 수 있는 사람을 지정합니다. 이것은 플레이어에게만 적용되며 관전자는 항상 모든 이름 태그를 볼 수 있습니다.

보통 맵은 2개의 팀을 가지고 있는것이 일반적이지만 더 많이 사용할 수는 있습니다. 하지만 더 많은 경우 혼란을 야기할 수 있습니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>팀 요소</th>
        <th>설명</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<teams> </teams>' | escape_once}}</code>
          </span>
        </td>
        <td>모든 개별 팀을 포함하는 팀 노드입니다.</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<team> </team>' | escape_once}}</code>
          </span>
        </td>
        <td>
          팀 이름이 포함된 단일 팀 노드입니다.
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>팀 속성</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 130px;'>속성</th>
        <th>설명</th>
        <th style='min-width: 120px;'>값</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>id</code>
        </td>
        <td>XML의 다른 위치에서 팀을 참조하는 데 사용되는 고유 식별자입니다.</td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
      </tr>
      <tr>
        <td>
          <code>color</code>
        </td>
        <td>팀의 보여지는 색상입니다.</td>
        <td>
          <a href='/reference/formatting#chatColors'>채팅 색상 이름</a>
        </td>
      </tr>
      <tr>
        <td>
          <code>overhead-color</code>
        </td>
        <td>해당 팀의 플레이어 머리위에 보여지는 이름표의 색상을 지정합니다.</td>
        <td>
          <a href='/reference/formatting#chatColors'>채팅 색상 이름</a>
        </td>
      </tr>
      <tr>
        <td>
          <code>plural</code>
        </td>
        <td>
          팀의 이름이 복수임을 나타냅니다. 주로 상태 메시지에 사용됩니다.
          <br/>
          예: <code>Defenders wins!</code> 대신 <code>Defenders win!</code>처럼 표시됩니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
      </tr>
      <tr>
        <td>
          <code>show-name-tags</code>
        </td>
        <td>
          이 팀에서 플레이어의 이름표를 볼 수있는 사용자를 지정합니다.
          <br/>
          사용 가능한 값:
          <code>true</code>, <code>false</code>, <code>allies</code> 혹은 <code>enemies</code>
        </td>
        <td>
          <span class='label label-primary'>열거형</span>
        </td>
      </tr>
      <tr>
        <td>
          <code>min</code>
        </td>
        <td>
          이 팀에 필요한 최소 플레이어의 수를 나타냅니다.
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
      </tr>
      <tr>
        <td>
          <code>max</code>
        </td>
        <td>
          이 팀의 최대 플레이어 수를 나타냅니다. 일반 플레이어는 이 크기에 도달하면 팀에 합류할 수 없습니다.
          <br/>
          <i>프리미엄 플레이어는 <code>max-overfill</code>에 도달할 때 까지 이 제한을 초과할 수 있습니다.</i>
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
      </tr>
      <tr>
        <td>
          <code>max-overfill</code>
        </td>
        <td>
          이 팀의 최대 플레이어 수 제한을 나타냅니다. 이 한도에 도달하면 아무도 팀에 합류할 수 없습니다.
          <br/>
          <i>앞에서 정의한 <code>max</code>값보다 커야 합니다.</i>
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>

예시  

    <teams>
       <team id="red-team" color="dark red" max="50" max-overfill="70">Red</team>
       <team id="blue-team" color="blue" max="50" max-overfill="70">Blue</team>
    </teams>
