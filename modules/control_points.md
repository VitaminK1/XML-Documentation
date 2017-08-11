---
layout: page

category: "모듈"
title:  "점령 지점"

---

점령 지점은 현재 점령하고 있는 팀에게 일정량의 포인트를 줍니다. 탐아 모든 지점을 점령하거나 특정 점수에 도달하면 ([점수 모듈](/modules/scoring)을 사용하여)경기가 종료됩니다. 점령 지점은 다른 게임 모드와 혼합하여 사용할 수 있습니다. 점령 지점의 다른 용도로는 목표 필터를 사용하여 맵 영역 잠금 해제와 같은 것들을 포함합니다.

    <control-points capture-players="lead" incremental="true" show-progress="true">
        <control-point name="Center" capture-time="20s">
            <capture><cylinder base="0.5,23,7.5" radius="7" height="5"/></capture>
            <progress><cylinder base="0.5,22,7.5" radius="7" height="4"/></progress>
            <captured><cylinder base="0.5,64,7.5" radius="7" height="5"/></captured>
        </control-point>
    </control-points>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 300px;'>점령 지점 요소</th>
        <th>설명</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<control-points> </control-points>' | escape_once}}</code>
          </span>
        </td>
        <td colspan='2'>단일 점령 지점 또는 여러 점령 지점을 포함하는 노드입니다.</td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<control-point> </control-point>' | escape_once}}</code>
          </span>
        </td>
        <td>
          단일 점령 지점입니다.
        </td>
        <td>
          <span class='label label-default'>점령 지점 하위 요소</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>점령 지점 속성</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 150px;'>속성</th>
        <th>설명</th>
        <th style='min-width: 100px;'>값</th>
        <th>기본값</th>
        <th>KotH</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>id</code>
        </td>
        <td>XML의 다른 위치에서 점령 지점을 참조하는 데 사용되는 고유 식별자입니다.</td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td colspan='2'></td>
      </tr>
      <tr>
        <td>
          <code>name</code>
        </td>
        <td>
          스코어 보드에 표시되는 점령 지점의 이름입니다.
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td colspan='2'></td>
      </tr>
      <tr>
        <td>
          <code>required</code>
        </td>
        <td>
          이 목표가 경기에서 이기기 위해 필요한지 여부를 지정합니다.
          <br/>
          필요한 모든 목표를 완료한 팀은 점수 또는 Blitz설정에 관계없이 승리합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td colspan='2'>
          true
        </td>
      </tr>
      <tr>
        <td>
          <code>capture-time</code>
        </td>
        <td>
          점령 지점을 캡처하는 데 걸리는 시간을 지정합니다.
        </td>
        <td>
          <a href='/reference/time_periods'>시간 단위</a>
        </td>
        <td colspan='2'>30초</td>
      </tr>
      <tr>
        <td>
          <code>points</code>
        </td>
        <td>
          거점을 소유한 팀에게 주어지는 초당 포인트를 지정합니다.
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td colspan='2'>1</td>
      </tr>
      <tr>
        <td>
          <code>points-growth</code>
        </td>
        <td>
          점수 값이 두배가 되는 시간(초) 입니다.
          만약 이 값이 주어진 경우 점령 지점이 점수를 주는 비율이 시간이 지남에 따라 기하 급수적으로 증가할 것입니다.
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td colspan='2'></td>
      </tr>
      <tr>
        <td>
          <code>capture-rule</code>
        </td>
        <td>
          주어진 특정 순간에 누가 지점을 제어할 지 결정하는 데 사용되는 규칙입니다.
        </td>
        <td>
          <a href='#capture_rule'>점령 규칙</a>
        </td>
        <td colspan='2'>
          독점
        </td>
      </tr>
      <tr>
        <td>
          <code>time-multiplier</code>
        </td>
        <td>
          점령 지점에서 팀 플레이어의 양을 기준으로 캡처 시간을 조정합니다.
        </td>
        <td>
          <span class='label label-primary'>소수</span>
        </td>
        <td>
          0
        </td>
        <td>
          0.1
        </td>
      </tr>
      <tr>
        <td>
          <code>show-progress</code>
        </td>
        <td>
          스코어보드에 점령 진행 상황 퍼센트를 표시합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>
          false
        </td>
        <td>
          true
        </td>
      </tr>
      <tr>
        <td>
          <code>neutral-state</code>
        </td>
        <td>
          점령 지점을 다시 점령하려면 점령되지 않은 상태여야 합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>
          거짓
        </td>
        <td>
          참
        </td>
      </tr>
      <tr>
        <td>
          <code>incremental</code>
        </td>
        <td>
          <span class='label label-warning' title='이 속성은 더이상 사용되지 않아야 합니다.'>더이상 사용되지 않음</span>
          점령이 중단되더라도 점령 진행률은 유지됩니다.
          <br/>
          <i>점령 진행 상황을 훨씬 더 자세히 제어할 수 있는 recovery 및 decay 속성으로 대체되었습니다.</i>
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>
          거짓
        </td>
        <td>
          참
        </td>
      </tr>
      <tr>
        <td>
          <code>recovery</code>
        </td>
        <td>
          점령 진행률을 복구합니다. 지금 거점을 점령하고 있는 플레이어의 진행률을 되돌립니다.
          <br/>
          <code>incremental</code> 속성과 함께 사용할 수 없습니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>
          oo
        </td>
        <td>
          1
        </td>
      </tr>
      <tr>
        <td>
          <code>decay</code>
        </td>
        <td>
          진행률을 캡처하고 진행률이 변하는 비율을 그대로 유지합니다. 이때는 아무도 점령 지점을 지배하지 않습니다.
          <br/>
          <code>incremental</code> 속성과 함께 사용할 수 없습니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>
          oo
        </td>
        <td>
          0
        </td>
      </tr>
      <tr>
        <td>
          <code>permanent</code>
        </td>
        <td>
          점령 지점은 경기 중에 한번만 점령할 수 있습니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>
          거짓
        </td>
        <td>
          참
        </td>
      </tr>
      <tr>
        <td>
          <code>initial-owner</code>
        </td>
        <td>
          경기가 시작될 때 점령 지점을 소유하는 팀을 지정합니다.
        </td>
        <td>
          <a href='/modules/teams'>팀 ID</a>
        </td>
        <td colspan='2'></td>
      </tr>
      <tr>
        <td>
          <code>show</code>
        </td>
        <td>
          목표를 인터페이스에 표시하고 목표 완료시 폭죽을 터뜨립니다.
          <br/>
          <i>숨겨진 목표는 완료된 목표에 포함되지 않으며 크리스탈 보상도 주어지지 않습니다.</i>
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td colspan='2'>참</td>
      </tr>
      <tr>
        <td>
          <code>visual-materials</code>
        </td>
        <td>
          점령 진행률 지역을 업데이트 할 때 수정된 재질을 필터링합니다.
          <br/>
          <i>기본값은 양털, 카펫, 굳은 점토, 염색된 유리 및 염색된 유리판입니다.</i>
        </td>
        <td>
          <a href='/modules/filters'>블럭 필터</a>
        </td>
        <td colspan='2'></td>
      </tr>
      <tr>
        <td>
          <code>capture</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          <span class='label label-danger'>필수</span>
          이 점령 지점을 점령할 수 있는 지역을 나타냅니다.
        </td>
        <td>
          <a href='/modules/regions'>지역</a>
        </td>
        <td colspan='2'></td>
      </tr>
      <tr>
        <td>
          <code>progress</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          이 점령 지점 진행률이 표시되는 지역을 나타냅니다.
        </td>
        <td>
          <a href='/modules/regions'>경계 지역</a>
        </td>
        <td colspan='2'></td>
      </tr>
      <tr>
        <td>
          <code>captured</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          이 점령 지점의 소유자가 표시되는 지역입니다.
        </td>
        <td>
          <a href='/modules/regions'>경계 지역</a>
        </td>
        <td colspan='2'></td>
      </tr>
      <tr>
        <td>
          <code>capture-filter</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          누가 이 점령 지점을 점령할 수 있는지 필터링합니다. 기본값은 모든팀입니다. 이 필터와 일치하지 않는 팀은 점령 지점에서 다른 팀이 캡처하지 못하게 할 수 있습니다. 또한 중립 상태가 활성화 된 경우 점령 지점의 점령을 해제할 수 있습니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
        <td colspan='2'></td>
      </tr>
      <tr>
        <td>
          <code>player-filter</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          누가 이 점령 지점을 점령할 수 있는지 필터링합니다. 이 필터와 일치하지 않는 플레이어는 어떤 방식으로든 점령 지점에 영향을 줄 수 없습니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
        <td colspan='2'></td>
      </tr>
    </tbody>
  </table>
</div>
<h5>점령 지점 하위 요소</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 160px;'>요소</th>
        <th>설명</th>
        <th>값/하위</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<capture>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          <span class='label label-danger'>필수</span>
          점령 지점을 캡처하기 위해 플레이어들이 서 있어야 하는 지역을 나타냅니다.
        </td>
        <td>
          <a href='/modules/regions'>지역</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<progress>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>Property</span>
          점령 진행률을 표시할 지역입니다.
        </td>
        <td>
          <a href='/modules/regions'>경계 지역</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<captured>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          만약 점령 지점이 점령된 경우 표시 할 지역입니다.
        </td>
        <td>
          <a href='/modules/regions'>경계 지역</a>
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
          누가 이 점령 지점을 점령할 수 있는지 필터링합니다. 기본값은 모든팀입니다. 이 필터와 일치하지 않는 팀은 점령 지점에서 다른 팀이 캡처하지 못하게 할 수 있습니다. 또한 중립 상태가 활성화 된 경우 점령 지점의 점령을 해제할 수 있습니다..
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<player-filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          누가 이 점령 지점을 점령할 수 있는지 필터링합니다. 이 필터와 일치하지 않는 플레이어는 어떤 방식으로든 점령 지점에 영향을 줄 수 없습니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>

#### 점령 규칙 {#capture_rule}
점령 규칙은 점령 지점을 제어하는 팀을 결정하는 데 사용되는 로직을 정의합니다. `capture-rule`의 값은 다음 중 하나일 수 있습니다.

* `exclusive` 팀은 점령 지점에 있는 유일한 팀이어야 합니다. (기본값)
* `majority` 팀은 다른 모든 팀을 합친것 보다 많은 수의 플레이어가 점령 지점에 있어야 합니다.
* `lead` 팀은 다른 하나의 팀보다 점령 지점에 더 많은 플레이어가 있어야 합니다.

`capture-filter`또는 `player-filter`와 일치하는 플레이어는 `capture-rule`을 계산할 때 사용됩니다. 두 필터 중 어느 하나와 일치하지 않는 플레이어는 점령 지점에 영향을 줄 수 없습니다.

<br/>

#### 점령 지점 지역

점령 진행 상황은 지배하고 있는 팀 색상을 사용하여 정의 된 `<progress>`영역 내에 표시됩니다. 점령 지점이 점령된 뒤에 `<captured>`지역도 그 색상으로 채워집니다. 진행 및 캡처된 지역은 경계 지역이어야 합니다. (예: 원기둥 및 직육면체는 작동하지만 원과 사각형은 작동하지 않습니다.) '시각 자료'에 정의된 기본 시각 자료 또는 자료만 업데이트 될 때 진행 상황 지역에서 수정됩니다.
