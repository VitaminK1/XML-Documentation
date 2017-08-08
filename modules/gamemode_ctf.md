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
          깃발 아래에 있는 블럭을 얼음으로 바꿈으로써 깃발을 물 위에 놓을 수 있게합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>참</td>
      </tr>
      <tr>
        <td>
          <code>beam</code>
        </td>
        <td>
          이 깃발에 대한 파티클 광선을 표시합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>참</td>
      </tr>
      <tr>
        <td>
          <code>flag-proximity-metric</code>
        </td>
        <td>
          깃발의 근접한 정도를 결정하는 데 사용되는 방식입니다.
          <br/>
          사용가능한 값: <code>closest player</code>, <code>closest block</code> or <code>closest kill</code>
        </td>
        <td>
          <span class='label label-primary'>근접도</span>
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
          깃발 근접 거리에 대한 수평 거리만 계산합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      <tr>
        <td>
          <code>net-proximity-metric</code>
        </td>
        <td>
          그물의 근접한 정도를 결정하는 데 사용되는 방식입니다.
          <br/>
          사용가능한 값: <code>closest player</code>, <code>closest block</code> or <code>closest kill</code>
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
          <code>net-proximity-horizontal</code>
        </td>
        <td>
          그물 근접 거리에 대한 수평 거리만 계산합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
    </tbody>
  </table>
</div>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>깃발 하위 요소</th>
        <th>설명</th>
        <th>종류</th>
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
          깃발을 캡처할 수 있는 그물, 여러개의 그물 하위 요소를 사용할 수 있습니다.
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
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          <span class='label label-danger'>필수</span>
          깃발의 초기 및 기본 기둥입니다.
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
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          누가 깃발을 픽업할 수 있는지 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<drop-filter>' | escape_once}}</code>
          </span>
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
          <span class='highlight'>
            <code>{{'<capture-filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          누가 깃발을 캡처할 수 있는지 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<pickup-kit>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          플레이어가 깃발을 픽업했을 때 주어지는 키트를 설정합니다.
        </td>
        <td>
          <a href='/modules/kits'>키트</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<drop-kit>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          어떤 이유로든 깃발 운반자가 깃발을 드롭했을 때 주어지는 키트를 성정합니다.
        </td>
        <td>
          <a href='/modules/kits'>키트</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<br/>

#### 기둥 {#posts}

**기둥(posts)**은 깃발이 캡처되거나 드롭된 후 다시 생성될 수 있는 지점 또는 지역입니다.
이것은 기본적으로 플레이어 대신 깃발을 위한 [스폰](/modules/spawns)입니다. 기둥은 스폰 처럼 [지점 제공자](/modules/regions#pointProviders)로 정의되고 무작위화될 수 있습니다.

깃발은 마지막 기둥(posts)를 기억하고 있으며, 드롭되거나 캡처된 후에 다시 생성됩니다.
각 깃발은 기본 기둥을 가지고 있어야 하며 경기가 시작할 때 배치됩니다.

만약 기둥이 지점이 아닌 지역으로 정의된 경우 깃발은 지역의 임의 지점에서 다시 생성됩니다.
여러 지점이나 지역이 주어지면 `sequential`옵션을 사용하지 않는 한 임의로 선택됩니다.
사용할 수 있는 공간이 있는 경우에만 여러 깃발을 동시에 세울 수 있습니다.

깃발을 다시 생성하는 데 필요한 시간은 설정할 수 있으며 드롭된 후 지상에서 보낼 시간도 설정할 수 있습니다.

기둥은 팀에 의해서 소유되며 깃발이 그곳에 있는 동안 지정된 속도로 점수를 부여할 수 있습니다.
`permanent`옵션은 기둥을 [모뉴먼트](/modules/gamemode_ctw)와 같은 것으로 만들 수 있습니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>기둥 요소</th>
        <th>설명</th>
        <th>값/하위</th>
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
          깃발이 스폰될 지점 또는 영역을 나타냅니다.
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
        <th style='min-width: 130px;'>기둥 속성</th>
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
        <td>XML의 다른 위치에서 이 기둥을 참조하는 데 사용되는 고유 식별자입니다.</td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>owner</code>
        </td>
        <td>이 기둥을 소유한 팀을 나타냅니다.</td>
        <td>
          <a href='/modules/teams'>팀 ID</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>permanent</code>
        </td>
        <td>
          깃발이 캡처되고 기둥으로 돌아왔을 때 깃발을 게임에서 삭제하고 이 깃발을 완료된 목표물로 취급합니다.
          <br/>
          <i>이 경우 목표에 대한 보상이 기둥의 <code>owner</code>에게 주어집니다.</i>
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      <tr>
        <td>
          <code>sequential</code>
        </td>
        <td>
          만약 이 기둥이 여러 지점 혹은 지역을 가지고 있는 경우 여기에서 깃발을 생성할 때 임의로 하나를 선택하는 대신 순서대로 시도합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      <tr>
        <td>
          <code>points-rate</code>
        </td>
        <td>
          깃발이 기둥에 있는 동안 소유자가 얻는 초당 점수입니다.
          <br/>
          <i><code>owner</code> 속성을 설정해야 합니다.</i>
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
          이 기둥에서 깃발을 집을 수 있는 사람을 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>recover-time</code>
        </td>
        <td>깃발이 드롭된 후 땅에 머물러있는 시간을 나타냅니다. 깃발을 땅에 영원히 머물게하려면 <code>oo</code>를 사용하십시오.</td>
        <td>
          <a href='/reference/time_periods'>시간 단위</a>
        </td>
        <td>30s</td>
      </tr>
      <tr>
        <td>
          <code>respawn-time</code>
        </td>
        <td>
          깃발이 캡처/복구되어 기둥에 다시 생성될 때 까지의 시간을 나타냅니다.
          <br/>
          <i>이 시간동안은 깃발은 완전히 사라지며 수비팀에게 그들의 기지로 깃발을 가져올 수 있는 기회를 줍니다.</i>
        </td>
        <td>
          <a href='/reference/time_periods'>시간 단위</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>respawn-speed</code>
        </td>
        <td>
          캡처/복구 된 후 이 기둥에서 깃발이 "이동"하여 다시 생성되는 속도를 나타냅니다.
          <br/>
          <i>이는 깃발이 이동해야 하는 거리를 기반으로 시간을 계산하는 <code>respawn-time</code>의 대안입니다.</i>
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
        <td>이 기둥으로 돌아온 후 배너가 향하는 방향을 나타냅니다.</td>
        <td>
          <span class='label label-primary'>-180 에서 180</span>
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
        <th>기둥 하위 요소</th>
        <th>설명</th>
        <th>값/하위</th>
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
          <span class='label label-default' title='속성이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          이 그물을 위해 누가 깃발을 픽업할 수 있는지 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<br/>

#### 그물(nets) {#nets}

`<net>`은 깃발을 캡처할 수 있는 영역입니다.
각 그물은 받아들일 수 있는 선택적 깃발 목록을 가지고 있습니다.
만약 그물이 깃발 안에 정의되면 그 깃발만이 그물에 캡처할 수 있습니다.
어떤 깃발을 캡처할 수 있는지 또 언제 캡처할 수 있는지 제어하기 위한 몇가지 옵션이 있습니다.

그물은 캡처된 후 어떤 깃발 기둥을 반환할 지 지정할 수 있습니다. 이것이 깃발들이 기둥 사이로 움직이는 방법입니다. 또한 그물은 깃발이 캡처되면 다른 깃발을 강제로 반환할 수 있습니다.

그물은 팀에 의해 소유될 수 있으며 그 그물안에 깃발을 캡처한 경우 점수를 받을 수 있습니다.
만약 그물의 소유자가 없다면 깃발을 들고있는 플레이어가 점수를 받게됩니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>그물 요소</th>
        <th>설명</th>
        <th>값/하위</th>
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
          깃발을 캡처할 수 있는 지역을 나타냅니다.
        </td>
        <td>
          <span class='label label-default'>그물 하위 요소</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 150px;'>그물 속성</th>
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
        <td>XML의 다른 위치에서 이 그물을 참조하는 데 사용되는 고유 식별자입니다.</td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>region</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          <span class='label label-danger'>필수</span>
          지역별 깃발 운반자가 이 그물에 캡처하려면 반드시 입력해야 합니다.
        </td>
        <td>
          <a href='/modules/regions'>지역</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>owner</code>
        </td>
        <td>이 그물을 소유한 팀을 나타냅니다.</td>
        <td>
          <a href='/modules/teams'>팀 ID</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>points</code>
        </td>
        <td>
          깃발을 이 그물안에 캡처함으로써 얻는 점수의 양입니다.
          <br/>
          만약 깃발에 <code>owner</code> 코드가 있으면 해당 팀이 포인트를 받습니다. 그렇지않으면 깃발을 운반한 사람의 팀이 점수를 받습니다.
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
          <code>post</code>
        </td>
        <td>
          깃발이 그물에 캡처된 이후에 반환할 깃발 기둥의 ID입니다.
        </td>
        <td>
          <a href='/modules/flags'>깃발 기둥</a>
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
          이 그물에 캡처할 수 있는 깃발을 나타냅니다.
          <br/>
          공백으로 구분된 깃발 ID의 목록입니다.
          <br/>
          <i>속성은 깃발 안에 정의 된 그물에 지정할 수 없습니다.</i>
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td>
          <span class='label label-default'>모든 깃발</span>
        </td>
      </tr>
      <tr>
        <td>
          <code>rescue</code>
        </td>
        <td>
          이 그물에 의해 "구출된" 깃발을 나타냅니다.
          <br/>
          공백으로 구분된 깃발 ID의 목록입니다.
          <br/>
          이 깃발들이 운반되는 동안 그물에는 아무것도 캡처할 수 없습니다.
          하지만 그 깃발들을 아무도 들고 있지 않다면 그들 중 일부는 땅에 떨어집니다. 그리고 이 그물에 있는 깃발을 캡처하면 즉시 떨어져 있던 깃발이 반환됩니다.
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>sticky</code>
        </td>
        <td>
          깃발을 그물에 캡처한 후에도 그물에 그대로 남아있게 합니다.
          <br/>
          깃발을 캡처할 수 없는 경우일때 플레이어가 그물에 진입하는 경우
          (예를 들어 <code>rescue</code> 나 <code>capture-filter</code>)
          그리고 나서 플레이어는 그물을 떠날 수 있고 깃발은 캡처가 허용되는 순간까지 그물에 머물러 있게됩니다.
          이것은 플레이어가 계속해서 깃발을 들고다닐 때만 일어납니다.
          그들이 그것을 떨어뜨리는 순간 깃발은 캡처됩니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>true</td>
      </tr>
      <tr>
        <td>
          <code>capture-filter</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          누가 이 그물에 캡처할 수 있는지 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>deny-message</code>
        </td>
        <td>
          캡처가 특별한 규칙 혹은 필터로 인해 제한되는 동안 깃발 운반자에게 표시할 사용자 지정 메시지입니다.
          <br/>
          이것은 혼란스러워하는 플레이어에게 <code>capture-filter</code> 를 설명하는 데 사용할 수 있습니다.
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>respawn-together</code>
        </td>
        <td>
          <em>모든</em> <code>flags</code>에 나열된 깃발은 다시 생성되기 전에 캡처해야 합니다.
        </td>
        <td>
          <span class='label label-primary'>침/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      <tr>
        <td>
          <code>respawn-filter</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          이 그물에 캡처 된 깃발이 다시 생성될 수 있을 때 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>respawn-message</code>
        </td>
        <td>
          깃발 리스폰이 특별한 규칙 혹은 필터로 인해 제한되는 동안 채팅으로 표시할 사용자 지정 메시지입니다.
          <br/>
          이것은 혼란스러워하는 플레이어에게 <code>respawn-filter</code> 를 설명하는 데 사용할 수 있습니다.
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>location</code>
        </td>
        <td>
          그물의 위치, 주로 근접 거리를 측정할 때 사용됩니다.
        </td>
        <td>
          <span class='label label-primary'>X,Y,Z</span>
        </td>
        <td>
          <span class='label label-default'>그물 중심 지역</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>그물 하위 요소</th>
        <th>설명</th>
        <th>값/하위</th>
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
          지역별 깃발 운반자가 이 그물에 캡처하려면 반드시 입력해야 합니다.
        </td>
        <td>
          <a href='/modules/regions'>지역</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<capture-filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          누가 이 그물안에 캡처할 수 있는지 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<respawn-filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          이 그물에 캡처 된 깃발이 다시 생성될 수 있을 때 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>

### 예시

#### Classic CTF

자신의 그물에다가 적의 깃발을 캡처하십시오.
적군이 깃발을 들고있는 동안에는 캡처할 수 없습니다.
적의 깃발을 캡처하면 땅에 떨어져 있는 아군 깃발은 바로 반환됩니다.

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

적의 그물에다 서로 공유하는 하나의 깃발을 캡처합니다.
각 캡처 후 중앙에서 깃발이 다시 생성됩니다.
깃발 운반자는 속도 부스트를 얻습니다.

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

서로 공유하는 깃발을 아군의 그물에다 캡처하고 아군 진영으로 가져온 다음 가능한 한 오랫동안 유지하십시오.

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

서로 공유하는 깃발을 점유하고있는 동안 점수를 얻습니다.
깃발을 드롭된 뒤 임의로 선택된 위치에서 다시 생성됩니다.
죽은 플레이어는 팀이 깃발을 가지고 있는 동안에는 리스폰할 수 없습니다. (관전은 가능합니다.)

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

각 적의 깃발을 한번 캡처하고 깃발 모뉴먼트에 놓습니다.

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
