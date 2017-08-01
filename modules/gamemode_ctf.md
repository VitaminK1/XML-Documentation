---
layout: page

category: "모듈"
title:  "깃발 쟁탈 게임"

---

깃발은 플레이어가 픽업하고 운반할 수 있는 [배너](http://minecraft.gamepedia.com/Banner)이며 지정된 지역에서 캡처됩니다.

깃발의 모양을 정의하려면 맵에 있는 깃발의 처음 위치에 맵 제작자가 수동으로 배너를 배치해야 합니다.
이것은 배너의 색깔과 패턴을 완벽하게 제어할 수 있게 해줍니다. [양털 쟁탈 게임](/modules/gamemode_ctw)과는 달리 XML에서 정의된 각 깃발은 게임에서 하나의 물리적 깃발을 만듭니다.
같은 깃발을 나타내는 항목이나 아이템이 절대 여러개 존재하지 않습니다.

깃발 외에도 CTF맵에는 깃발을 캡처하기 위한 **그물(nets)**이 필요하고 **기둥(posts)**은 그것들이 리스폰하기 위해서 필요합니다.

    <flags>
        <post id="red-flag-post" pickup-filter="blue-only">2,5,11</post>
        <flag id="red-flag" name="Red Flag" color="red" post="red-flag-post"/>
        <net post="red-flag-post" points="1" region="blue-net" capture-filter="blue-only"/>
    </flags>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>깃발 요소</th>
        <th>설명</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<flags> </flags>' | escape_once}}</code>
          </span>
        </td>
        <td>이 경기에 대한 깃발, 네트, 포스트를 포함한 노드입니다.</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<flag>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#flags'><i class="fa fa-chevron-down"></i></a>
          맵에서의 단일 물리적 깃발(배너)입니다.
        </td>
        <td>
          <span class='label label-default'>깃발 하위 요소</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<post>X,Y,Z</post>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#posts'><i class="fa fa-chevron-down"></i></a>
          깃발이 스폰될 지점 또는 영역을 나타냅니다.
        </td>
        <td>
          <a href='/modules/regions#pointProviders'>지점 제공자</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<net>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#nets'><i class="fa fa-chevron-down"></i></a>
          깃발이 캡처될 수 있는 지역을 나타냅니다.
        </td>
        <td>
          <span class='label label-default'>그물 하위 요소</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<br/>

#### 깃발 {#flags}

`<flag>`는 픽업하고, 드롭하고 캡처할 수 있는 단일 실제 배너입니다.
이것의 모양은 맵에 내장된 실제 배너로 정의되며 XML로 다시 정의할 수 있는 이름과 색상이 있습니다.
또한 깃발은 특정 팀이 소유하거나 공유할 수 있습니다.
이것은 양털 쟁탈 게임과 비슷한 일회성 목적으로 사용되거나 [점수](/modules/scoring)를 부여하거나 차감할 수 있게 바꿀 수 있습니다.
깃발을 캡처한 경우 점수를 부여할 수 있으며 깃발을 얼마나 오래 점유하느냐에 따라 점수를 부여할 수도 있습니다.
또한 이것은 [키트](/modules/kits)와 함께 사용할 수 있습니다.
필터를 사용하여 누가 언제 깃발을 픽업하거나 캡처할 수 있는지 제어 할 수 있습니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>깃발 요소</th>
        <th>설명</th>
        <th>값/하위</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<flag>' | escape_once}}</code>
          </span>
        </td>
        <td>
          맵에서의 단일 물리적 깃발(배너)입니다.
        </td>
        <td>
          <span class='label label-default'>깃발 하위 요소</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 150px;'>깃발 속성</th>
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
        <td>XML의 다른 위치에서 이 깃발을 참조하는 데 사용되는 고유 식별자입니다.</td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>필수</code>
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
          <code>name</code>
        </td>
        <td>깃발과 스코어보드 위에 표시되는 이름을 나타냅니다.</td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>color</code>
        </td>
        <td>
          깃발의 이름, 파티클 등에 사용되는 깃발의 색을 나타냅니다.
          <br/>
          만약 생략될 경우 배너의 기본 색상이 사용됩니다.
        </td>
        <td>
          <a href='/reference/colors'>염료 색깔 이름</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>show</code>
        </td>
        <td>스코어보드, 채팅에 깃발을 표시할지 설정합니다.</td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>참</td>
      </tr>
      <tr>
        <td>
          <code>post</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          <span class='label label-danger'>필수</span>
          깃발의 초기 및 기본 기둥입니다.
        </td>
        <td>
          <a href='/modules/gamemode_ctf#posts'>깃발 기둥</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>owner</code>
        </td>
        <td>
          이 깃발을 방어하는 팀, 즉 픽업 또는 캡처되지 못하게 하려고 하는 팀을 말합니다.
          <br/>
          이 팀에 속해있는 플레이어들은 깃발이 픽업되거나 드롭될때 이를 알아차리기 위해 특별한 음향 효과를 들을 수 있습니다.
        </td>
        <td>
          <a href='/modules/teams'>팀 ID</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>shared</code>
        </td>
        <td>
          이 깃발은 여러 팀이 운반할 수 있습니다.
          <br/>
          깃발의 스코어보드 아이콘이 깃발 자체의 색이 아닌 팀의 색을 가지고 있게 합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      <tr>
        <td>
          <code>carry-message</code>
        </td>
        <td>
          이 깃발을 들고있는 플레이어에게 표시할 사용자 지정 메시지입니다.
          <br/>
          필요한 경우 예를 들어, "깃발을 들고 당신의 기지로 돌려 보내십시오!"라는 특별한 지시를 내리는 데 사용할 수 있습니다.
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>points</code>
        </td>
        <td>
          이 깃발을 캡처함으로써 얻는 점수의 양입니다.
          <br/>
          만약 깃발에 <code>owner</code>코드가 있으면 해당 팀이 포인트를 받습니다. 그렇지않으면 깃발을 운반한 사람의 팀이 점수를 받습니다.
          <br/>
          <i>음수는 점수를 부여하는 대신 점수를 빼는 데 사용할 수 있습니다.</i>
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td>0</td>
      </tr>
      <tr>
        <td>
          <code>points-rate</code>
        </td>
        <td>
          이 깃발이 운반되는 동안 초당 획득하는 점수의 양입니다.
          <br/>
          만약 깃발에 <code>owner</code>코드가 있으면 해당 팀이 포인트를 받습니다. 그렇지않으면 깃발을 운반한 사람의 팀이 점수를 받습니다.
          <br/>
          <i>음수는 점수를 부여하는 대신 점수를 빼는 데 사용할 수 있습니다.</i>
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td>0</td>
      </tr>
      <tr>
        <td>
          <code>pickup-filter</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          누가 깃발을 픽업할 수 있는지 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>drop-filter</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          깃발이 현재 위치에서 드롭될 수 있는지 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>capture-filter</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          누가 깃발을 캡처할 수 있는지 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>pickup-kit</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          플레이어가 깃발을 픽업했을 때 주어지는 키트를 설정합니다.
        </td>
        <td>
          <a href='/modules/kits'>키트</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>drop-kit</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          어떤 이유로든 깃발 운반자가 깃발을 드롭했을 때 주어지는 키트를 성정합니다.
        </td>
        <td>
          <a href='/modules/kits'>키트</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>carry-kit</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          플레이어가 깃발을 들고 있을때 주어지고 드롭했을 때 없어지는 키트를 설정합니다.
          제거할 수 있는 키트만 허용됩니다. 키트 페이지에서 제거할 수 있는 키트 유형을 볼 수 있습니다.
        </td>
        <td>
          <a href='/modules/kits'>제거할 수 있는 키트</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>drop-on-water</code>
        </td>
        <td>
          Allow this flag to be dropped on water, freezing the block under it into ice.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>true</td>
      </tr>
      <tr>
        <td>
          <code>beam</code>
        </td>
        <td>
          Show a particle beam for this flag.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>true</td>
      </tr>
      <tr>
        <td>
          <code>flag-proximity-metric</code>
        </td>
        <td>
          Metric used to determine proximity to the flag.
          <br/>
          Accepts <code>closest player</code>, <code>closest block</code> or <code>closest kill</code>
        </td>
        <td>
          <span class='label label-primary'>Proximity Metric</span>
        </td>
        <td>
          <code>closest kill</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>flag-proximity-horizontal</code>
        </td>
        <td>
          Only calculate horizontal distance for flag proximity.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
      <tr>
        <td>
          <code>net-proximity-metric</code>
        </td>
        <td>
          Metric used to determine proximity to the net.
          <br/>
          Accepts <code>closest player</code>, <code>closest block</code> or <code>closest kill</code>
        </td>
        <td>
          <span class='label label-primary'>Proximity Metric</span>
        </td>
        <td>
          <code>closest player</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>net-proximity-horizontal</code>
        </td>
        <td>
          Only calculate horizontal distance for net proximity.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
    </tbody>
  </table>
</div>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Flag Sub-elements</th>
        <th>Description</th>
        <th>Type</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<net>' | escape_once}}</code>
          </span>
        </td>
        <td>
          A net where only this flag can be captured, flags accept multiple net sub-elements.
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<post>X,Y,Z</post>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          <span class='label label-danger'>Required</span>
          The flag's initial & default post.
        </td>
        <td>
          <a href='/modules/regions#pointProviders'>지점 제공자</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<pickup-filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be this sub-element or an attribute.'>Property</span>
          Filter who can pickup the flag.
        </td>
        <td>
          <a href='/modules/filters'>Filters</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<drop-filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be this sub-element or an attribute.'>Property</span>
          Filter if the flag can be dropped at the current location.
        </td>
        <td>
          <a href='/modules/filters'>Filters</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<capture-filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be this sub-element or an attribute.'>Property</span>
          Filter who can capture the flag.
        </td>
        <td>
          <a href='/modules/filters'>Filters</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<pickup-kit>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be this sub-element or an attribute.'>Property</span>
          Given to players when they pick up the flag.
        </td>
        <td>
          <a href='/modules/kits'>Kit</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<drop-kit>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be this sub-element or an attribute.'>Property</span>
          Given to flag carriers when they lose the flag, for whatever reason.
        </td>
        <td>
          <a href='/modules/kits'>Kit</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<br/>

#### Posts {#posts}

A **post** is a point or region where flags can respawn after being captured or dropped.
It is essentially a [spawn](/modules/spawns) for flags instead of players,
and like spawns, they are defined with [point providers](/modules/regions#pointProviders), and can be randomized.

A flag remembers the last post it was at and will respawn there after being dropped or captured.
Each flag must have a default post, where it will be placed at the start of the match.

If a post is defined with a region rather than a point, flags will respawn at a random point in the region.
If multiple points or regions are given, one will be chosen at random (unless the `sequential` option is used).
Multiple flags can be at a post simultaneously only if there is space available for them.

The time required for a flag to respawn is configurable, as well as the time it spends on the ground after being dropped.

Posts can be owned by a team, and award them points at a specified rate while a flag is there.
The `permanent` option can be used to make a post into something like a [monument](/modules/gamemode_ctw), where the flag is mounted after being captured once.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Post Element</th>
        <th>Description</th>
        <th>Value/Children</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<post>X,Y,Z</post>' | escape_once}}</code>
          </span>
        </td>
        <td>
          A point or region(s) for flags to spawn at.
        </td>
        <td>
          <a href='/modules/regions#pointProviders'>지점 제공자</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 130px;'>Post Attributes</th>
        <th>Description</th>
        <th>Value</th>
        <th>Default</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>id</code>
        </td>
        <td>Unique identifier used to reference this post from other places in the XML.</td>
        <td>
          <span class='label label-primary'>String</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>owner</code>
        </td>
        <td>The team that owns this post.</td>
        <td>
          <a href='/modules/teams'>Team ID</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>permanent</code>
        </td>
        <td>
          When a flag is captured and returned to this post, remove the flag from the game and consider it a completed objective.
          <br/>
          <i>The objective is credited to the <code>owner</code> of the post, which is required in this case.</i>
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
      <tr>
        <td>
          <code>sequential</code>
        </td>
        <td>
          If this post has multiple points or regions, try them in order instead of choosing one at random, when spawning a flag here.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
      <tr>
        <td>
          <code>points-rate</code>
        </td>
        <td>
          Points awarded per second to this post's owner while any flag is at the post.
          <br/>
          <i>Requires the <code>owner</code> attribute to be set.</i>
        </td>
        <td>
          <span class='label label-primary'>Number</span>
        </td>
        <td>0</td>
      </tr>
      <tr>
        <td>
          <code>pickup-filter</code>
        </td>
        <td>
          <span class='label label-default' title='Can be this attribute or a sub-element.'>Property</span>
          Filter who can pickup a flag from this post.
        </td>
        <td>
          <a href='/modules/filters'>Filter</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>recover-time</code>
        </td>
        <td>Time that a flag stays on the ground after being dropped. Use <code>oo</code> to let the flag stay on the ground forever.</td>
        <td>
          <a href='/reference/time_periods'>Time Period</a>
        </td>
        <td>30s</td>
      </tr>
      <tr>
        <td>
          <code>respawn-time</code>
        </td>
        <td>
          Time between a flag being captured/recovered and respawning at this post.
          <br/>
          <i>During this time, the flag is completely gone, giving defenders a chance to return to their base.</i>
        </td>
        <td>
          <a href='/reference/time_periods'>Time Period</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>respawn-speed</code>
        </td>
        <td>
          Speed that a flag "moves" to respawn at this post, after being captured/recovered.
          <br/>
          <i>This is an alternative to <code>respawn-time</code> that calculates the time based on the distance the flag must travel.</i>
        </td>
        <td>
          <span class='label label-primary'>M/s</span>
        </td>
        <td>8</td>
      </tr>
      <tr>
        <td>
          <code>yaw</code>
        </td>
        <td>The direction a banner faces after it is returned to this post.</td>
        <td>
          <span class='label label-primary'>-180 to 180</span>
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Post Sub-elements</th>
        <th>Description</th>
        <th>Value/Children</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<pickup-filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          Filter who can pickup the flag for this net.
        </td>
        <td>
          <a href='/modules/filters'>Filters</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<br/>

#### Nets {#nets}

A `<net>` is a region that flags can be captured in.
Each net has a optional list of flags that it will accept.
If a net is defined inside a flag, only that flag can be captured in the net.
Several other options are available to control which flags can be captured and when.

A net can specify which post flags are returned to after being captured. This is how flags move between posts.
A net can also force other flags to be returned when any flag is captured.

A net can be owned by a team, who will receive points for the flags captured in it.
If the net has no owner, then the player carrying the flag will receive the points.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Net Element</th>
        <th>Description</th>
        <th>Value/Children</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<net>' | escape_once}}</code>
          </span>
        </td>
        <td>
          A region that flags can be captured in.
        </td>
        <td>
          <span class='label label-default'>Net Sub-elements.</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 150px;'>Net Attributes</th>
        <th>Description</th>
        <th>Value</th>
        <th>Default</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>id</code>
        </td>
        <td>Unique identifier used to reference this net from other places in the XML.</td>
        <td>
          <span class='label label-primary'>String</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>region</code>
        </td>
        <td>
          <span class='label label-default' title='Can be this attribute or a sub-element.'>Property</span>
          <span class='label label-danger'>Required</span>
          The region flag carriers must enter to capture in this net.
        </td>
        <td>
          <a href='/modules/regions'>Region</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>owner</code>
        </td>
        <td>The team that owns this net.</td>
        <td>
          <a href='/modules/teams'>Team ID</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>points</code>
        </td>
        <td>
          The amount of points awarded for capturing a flag in this net.
          <br/>
          If the net has an <code>owner</code>, that team receives the points. Otherwise, the carrier's team receives them.
          <br/>
          <i>A negative number can be used to take away points rather than give them.</i>
        </td>
        <td>
          <span class='label label-primary'>Number</span>
        </td>
        <td>0</td>
      </tr>
      <tr>
        <td>
          <code>post</code>
        </td>
        <td>
          The ID of the post a flag returns to after being captured in this net.
        </td>
        <td>
          <a href='/modules/flags'>Flag Post</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>flag</code>
          |
          <code>flags</code>
        </td>
        <td>
          Flag(s) that can be captured in this net.
          <br/>
          This is a list of flag IDs, separated with spaces.
          <br/>
          <i>Attribute can not be specified on nets that are defined inside a flag.</i>
        </td>
        <td>
          <span class='label label-primary'>String</span>
        </td>
        <td>
          <span class='label label-default'>ALL Flags</span>
        </td>
      </tr>
      <tr>
        <td>
          <code>rescue</code>
        </td>
        <td>
          Flag(s) that are "rescued" by this net.
          <br/>
          This is a list of flag IDs, separated with spaces.
          <br/>
          Nothing can be captured in the net while any of these flags are being carried.
          However, if none of them are being carried, but some of them are dropped on the ground,
          capturing any flag in this net will instantly return the dropped flags.
        </td>
        <td>
          <span class='label label-primary'>String</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>sticky</code>
        </td>
        <td>
          A flag carrier stays "in" the net, even after they leave.
          <br/>
          If a player enters the net at a time when the flag can't be captured
          (e.g. because of <code>rescue</code> or <code>capture-filter</code>)
          they can then leave the net and the flag will still be captured the moment it is allowed to be.
          This only happens if the player continues to carry the flag.
          As soon as they drop it, they are no longer "in" the net.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>true</td>
      </tr>
      <tr>
        <td>
          <code>capture-filter</code>
        </td>
        <td>
          <span class='label label-default' title='Can be this attribute or a sub-element.'>Property</span>
          Filter players who can capture in this net.
        </td>
        <td>
          <a href='/modules/filters'>Filter</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>deny-message</code>
        </td>
        <td>
          Custom message to display to flag carriers while capture is being prevented by a special rule or filter.
          <br/>
          This can be used to explain an unusual <code>capture-filter</code> to a confused player.
        </td>
        <td>
          <span class='label label-primary'>String</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>respawn-together</code>
        </td>
        <td>
          <em>All</em> the flags listed in <code>flags</code> must be captured before <em>any</em> of them respawn.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
      <tr>
        <td>
          <code>respawn-filter</code>
        </td>
        <td>
          <span class='label label-default' title='Can be this attribute or a sub-element.'>Property</span>
          Filter when the flags captured in this net are allowed to respawn.
        </td>
        <td>
          <a href='/modules/filters'>Filter</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>respawn-message</code>
        </td>
        <td>
          Custom message to broadcast in chat when flag respawn is prevented by a special rule or filter.
          <br/>
          This can be used to explain an unusual <code>respawn-filter</code> to confused players.
        </td>
        <td>
          <span class='label label-primary'>String</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>location</code>
        </td>
        <td>
          Location where the net can be found at, used to determine proximity.
        </td>
        <td>
          <span class='label label-primary'>X,Y,Z</span>
        </td>
        <td>
          <span class='label label-default'>Net Region Center</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Net Sub-elements</th>
        <th>Description</th>
        <th>Value/Children</th>
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
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          <span class='label label-danger'>Required</span>
          The region flag carriers must enter to capture in this net.
        </td>
        <td>
          <a href='/modules/regions'>Regions</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<capture-filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          Filter players who can capture in this net.
        </td>
        <td>
          <a href='/modules/filters'>Filters</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<respawn-filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          Filter when the flags captured in this net are allowed to respawn.
        </td>
        <td>
          <a href='/modules/filters'>Filters</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>

### Examples

#### Classic CTF

Capture the enemy's flag in your own net.
You can't capture while the enemy is carrying your flag.
Capturing the enemy's flag returns yours if it is dropped on the ground.

    <score>
        <limit>3</limit>
    </score>

    <flags>
        <flag id="blue-flag" name="Blue Flag" owner="blue-team">
            <post pickup-filter="red-only">2,5,11</post>
        </flag>

        <flag id="red-flag" name="Red Flag" owner="red-team">
            <post pickup-filter="blue-only">24,5,11</post>
        </flag>

        <flags points="1">
            <net region="red-net" flag="blue-flag" rescue="red-flag"/>
            <net region="blue-net" flag="red-flag" rescue="blue-flag"/>
        </flags>
    </flags>

<br/>

#### Flag Football

Capture a shared flag in the enemy's net.
The flag respawns in the center after each capture.
Flag carriers get a speed boost.

    <score>
        <limit>3</limit>
    </score>

    <flags>
        <flag id="flag" name="Flag" color="white" shared="true">
            <post id="center-post">
                <cylinder base="13,1,11" radius="5" height="1"/>
            </post>
            <pickup-kit force="true">
                <potion amplifier="2" duration="oo">speed</potion>
            </pickup-kit>
            <drop-kit force="true">
                <potion duration="0">speed</potion>
            </drop-kit>

            <net points="1" region="red-net" capture-filter="blue-only"/>
            <net points="1" region="blue-net" capture-filter="red-only"/>
        </flag>
    </flags>

<br/>

#### King of the Flag

Capture a shared flag in your own net to bring it to your side, then keep it there as long as possible.

    <score>
        <limit>180</limit>
    </score>

    <flags>
        <flag name="Flag" color="white" shared="true">
            <post>13,1,11</post>
            <net owner="yellow-team" region="yellow-net" post="yellow-post" capture-filter="yellow-only"/>
            <net owner="blue-team" region="blue-net"   post="blue-post"   capture-filter="blue-only"/>
        </flag>

        <flags points-rate="1">
            <post id="red-post"
                  owner="red-team"
                  yaw="90"
                  pickup-filter="blue-only">
                24,5,11
            </post>
            <post id="blue-post"
                  owner="blue-team"
                  yaw="-90"
                  pickup-filter="red-only">
                2,5,11
            </post>
        </flags>
    </flags>

<br/>

#### Flag Blitz

Earn points while carrying a shared flag.
The flag respawns at a randomly chosen location after being dropped.
Dead players cannot respawn while their team has the flag (but they can spectate).

    <spawns>
        <spawn team="red" region="red-spawn"/>
        <spawn team="blue" region="blue-spawn"/>
        <filter>
            <not>
                <same-team>
                    <carrying-flag>flag</carrying-flag>
                </same-team>
            </not>
        </filter>
    </spawns>

    <respawn spectate="true">
        <!-- "You will respawn when the flag is dropped..." -->
        <message>{ translate: "death.respawn.confirmed.waiting.flagDropped" }</message>
    </respawn>

    <flags>
        <post id="post" return-time="0s" respawn-time="7s">
            <block> 3.5,15,-445.5 </block>
            <block> 3.5,20,-475.5 </block>
            <block> 3.5,20,-415.5 </block>
        </post>
        <flag id="flag" name="Flag" shared="true" post="post" points-rate="1"/>
    </flags>

<br/>

#### Complete the Flag

Capture each enemy flag (once) and place them on your flag monument.

    <flags>
        <flags owner="blue-team" pickup-filter="red-only">
            <flag id="cyan-flag" name="Cyan Flag">
                <post>2,5,10</post>
            </flag>
            <flag id="magenta-flag" name="Magenta Flag">
                <post>2,5,12</post>
            </flag>
        </flags>

        <flags owner="red-team" pickup-filter="blue-only">
            <flag id="yellow-flag" name="Yellow Flag">
                <post>24,5,10</post>
            </flag>
            <flag id="orange-flag" name="Orange Flag">
                <post>24,5,12</post>
            </flag>
        </flags>

        <net region="red-net"
             flags="cyan-flag magenta-flag"
             post="red-monument"/>

        <net region="blue-net"
             flags="orange-flag yellow-flag"
             post="blue-monument"/>

        <flags permanent="true" sequential="true">
            <post id="blue-monument"
                  owner="blue-team"
                  yaw="-90">
                <!-- room for two flags -->
                <block>2, 1, 10</block>
                <block>2, 1, 12</block>
            </post>
            <post id="red-monument"
                  owner="red-team"
                  yaw="90">
                <!-- room for two flags -->
                <block>24, 1, 10</block>
                <block>24, 1, 12</block>
            </post>
        </flags>
    </flags>
