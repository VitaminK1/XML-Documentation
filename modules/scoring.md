---
layout: page

category: "모듈"
title:  "점수"

---

점수 모듈은 경기에 점수 제한을 두고 매번 죽거나 죽일 때마다 점수에 추가되는 포인트의 수를 수정하는 데 사용될 수 있습니다. 또한 플레이어나 팀에게 점수를 부여할 때 일정 점수를 주는 스코어 박스를 만드는 데에도 사용할 수 있습니다.
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>점수 요소</th>
        <th>설명</th>
        <th></th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<score> </score>' | escape_once}}</code>
          </span>
        </td>
        <td colspan='3'>점수 설정 및 스코어 박스가 포함 된 노드입니다.</td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위</th>
        <th>기본값</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<limit>' | escape_once}}</code>
          </span>
        </td>
        <td>
          경기가 끝나기 전에 도달할 수 있는 최대 점수를 설정합니다.
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td>
          제한 없음
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<kills>' | escape_once}}</code>
          </span>
        </td>
        <td>
          적 팀 플레이어를 죽인 후 주어지는 <strong>점수</strong>를 설정합니다.
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td>
          0
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<deaths>' | escape_once}}</code>
          </span>
        </td>
        <td>
          팀원이 <strong>실수로</strong> 사망했을 때 팀에게서 <strong>가져갈</strong> 점수를 설정합니다.
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td>
          0
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<box>' | escape_once}}</code>
          </span>
        </td>
        <td>
          단일 스코어 박스 입니다.
        </td>
        <td>
          <a href='#score_box'>스코어 박스</a>
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>

예시

    <score>
        <!-- 먼저 100점에 도달하는 팀이 경기를 승리합니다. -->
        <limit>100</limit>

        <kills>3</kills> <!-- 상대를 제거할 때마다 3점을 줍니다. -->
        <deaths>2</deaths> <!-- 실수로 죽을 때마다 2점을 차감합니다. -->
    </score>


<br/>

#### 스코어 박스 {#score_box}
스코어 박스는 스코어 박스 지역에서 교환할 수 있는 아이템을 가져오거나 스코어 박스에 들어가면 점수를 부여합니다. 다중 득점을 방지하기 위해 [포탈](/modules/portals)을 설정하여 스코어 박스 부근에서 플레이어를 제거해야 합니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>스코어 박스 요소</th>
        <th>설명</th>
        <th>값/하위</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<box>' | escape_once}}</code>
          </span>
        </td>
        <td>
          단일 스코어 박스 입니다.
        </td>
        <td>
          <span class='label label-default'>스코어 박스 하위 요소</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>스코어 박스 속성</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>속성</th>
        <th>설명</th>
        <th>종류</th>
        <th>기본값</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>points</code>
        </td>
        <td>Points awarded for entering the box.</td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td>0</td>
      </tr>
      <tr>
        <td>
          <code>silent</code>
        </td>
        <td>Don't notify players when points are scored in this box.</td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
      <tr>
        <td>
          <code>region</code>
        </td>
        <td>
          <span class='label label-default' title='Can be either this attribute or a sub-element.'>Property</span>
          <span class='label label-danger'>Required</span>
          The location and size of the score box.
        </td>
        <td>
          <a href='/modules/regions'>Region</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>filter</code>
        </td>
        <td>
          <span class='label label-default' title='Can be either this attribute or a sub-element.'>Property</span>
          Filter who can score in this box.
        </td>
        <td>
          <a href='/modules/filters'>Filter</a>
        </td>
        <td>
          <span class='label label-default'>No Filter</span>
        </td>
      </tr>
      <tr>
        <td>
          <code>trigger</code>
        </td>
        <td>
          <span class='label label-default' title='Can be either this attribute or a sub-element.'>Property</span>
          Dynamic conditions under which this score box is applied.
        </td>
        <td>
          <a href='/modules/filters'>Dynamic Filter</a>
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>
<h5>Score Box Sub-elements</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Element</th>
        <th>Description</th>
        <th>Value/Children</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<redeemables>' | escape_once}}</code>
          </span>
        </td>
        <td>
          Items that can be redeemed at this score box for points.
        </td>
        <td>
          <code>{{'<item points="1">' | escape_once}}</code>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<region>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          <span class='label label-danger'>Required</span>
          The region where this score box is located.
        </td>
        <td>
          <a href='/modules/regions'>Regions</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          Filter who can score in this box.
        </td>
        <td>
          <a href='/modules/regions'>Filters</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<trigger>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          Dynamic conditions under which this score box is applied.
        </td>
        <td>
          <a href='/modules/filters'>Dynamic Filters</a>
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>

Example

    <score>
        <!-- Only allow red team to use this score box, and give them two points -->
        <box points="2" filter="only-red">
            <region><cylinder base="21,8,63" radius="1" height="2"/></region>
        </box>
    </score>

    <score>
        <box value="8" filter="cyan" region="cyan-scorebox"/>
    </score>

<br/>

#### Redeemables
A score box can also award points in exchange for particular items carried by the player when they
enter the box. These items are defined inside a `<redeemables>` score box sub-element as `<item>` tags.
Each item contains a [material name](/reference/inventory#material_finder)
and an optional `points="..."` attribute specifying the number of points awarded for each item.

Example

    <score>
        <box filter="only-red" region="red-depot">
            <redeemables>
                <item points="5">diamond</item>
                <item points="3">emerald</item>
                <item points="1">gold nugget</item>
            </redeemables>
        </box>
    </score>


<br/>

### Time Limit {#timeLimit}
Give the match a time limit, the result attribute determines how the winning team or player is calculated when the time runs out.
Result can be the name of a team, or one of the special values; "tie" for no winner, or "objectives" for the team that has the most objectives completed. The time limit can be specified in minutes, etc., by formatting it as a [time period](/reference/time_periods).

`NOTE!` This tag is **not** placed inside the score module, instead it is located in the root `<map>` element.

    <time result="objectives">5m</time>


##### Time Attributes

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Attribute</th>
        <th>Description</th>
        <th>Type</th>
        <th>Default</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>result</code>
        </td>
        <td>
          Change how the winning team or player is calculated.
          <br/>
          Accepts <code>default</code>, <code>tie</code>, <code>objectives</code> or a Team ID.
        </td>
        <td>
          <span class='label label-primary'>Victory Condition</span>
          |
          <span class='label label-primary'>Team ID</span>
        </td>
        <td>default</td>
      </tr>
      <tr>
        <td>
          <code>show</code>
        </td>
        <td>Show the remaining time in the chat and boss bar.</td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>true</td>
      </tr>
    </tbody>
  </table>
</div>
