---
layout: page

category: "모듈"
title:  "필터"
nav_content:
  - path: "#list"
    name: "필터 매처 (Filter Matchers)"
  - path: "#filterModifiers"
    name: "필터 한정자 (Filter Modifiers)"
  - path: "#killStreakFilter"
    name: "연속 처치 필터"
  - path: "#randomFilter"
    name: "랜덤 필터"
  - path: "#rank_score"
    name: "랭크 &amp; 점수 필터"
  - path: "#players"
    name: "플레이어 수 필터"
  - path: "#objectiveFilter"
    name: "목표 필터"
  - path: "#flagFilter"
    name: "깃발 필터"
  - path: "#causeFilters"
    name: "이벤트 사유 필터"
  - path: "#relationFilters"
    name: "플레이어 관계 필터"
  - path: "#itemFilters"
    name: "아이템 필터"
  - path: "#structuralLoadFilters"
    name: "구조 로드 필터"
  - path: "#voidFilter"
    name: "보이드 필터"

---

필터는 일반적으로 플레이어, 블럭 또는 일반적인 게임에 대한 참/거짓 조건입니다.
다른 모듈은 필터를 사용하여 플레이어, 블럭, 또는 전체 경기의 **언제** 그리고 **어디서** 일이 발생해야하는지 여부를 결정합니다.

필터는 **매처 (Matchers)** 와 **한정자 (Modifiers)**로 작성됩니다.
매처는 다음과 같은 구체적인 질문들에 대한 답이 될 수 있습니다.

* 나무로 만들어졌나요?
* 그 플레이어가 레드 팀에 속해있나요?
* 지역의 X축 안에 있나요?
* 경기가 5분동안 진행 되었나요?

한정자는 다음과 같은 논리를 사용하여 질문을 결합할 수 있습니다.

* A 와 B
* A 또는 B
* A 아님
* (A 또는 B)가 아니라 (A 와 B)

한정자는 또한 다양한 방식으로 질문 혹은 답변의 의미를 변형시킬 수 있습니다.

다른 모듈에 대한 문서에서는 필터를 사용할 수 있는 위치와 필터가 모듈의 동작에 미치는 영향에 대해 설명합니다.
일반적으로 다른 모듈은 다음 두가지 방법중 하나로 필터를 사용합니다.
<ul>
  <li>
    <em>수동적으로 말하자면,</em>
    그 모듈이 작동할 때마다 필터는 필터를 확인하여 그것이 작동되어야하는지 여부를 결정합니다.
  </li>
  <li>
    <em>동적으로 말하자면,</em>
    필터는 무언가를 할 시간이 되었을 때 모듈에 알리고 그것을 누가 처리해야 하는지를 알려줍니다.
  </li>
</ul>
<p>
  <span class='label label-primary'>동적</span>
  이라고 표시된 필터만이 후자의 필터를 사용할 수 있습니다. 동적 필터가 필요한 모듈은 각 모듈 문서에서 찾을 수 있습니다.
</p>

### 기권
일부 필터는 특정 상황에서 아무 의미가 없습니다. 예를 들어, 블럭이 레드 팀에 있는지 또는 플레이어가 나무로 제작되었는지 또는 경기가 지역 내에 있는지 물어볼 필요가 없습니다.

잘못된 유형의 필터를 사용하려고 하면 일부 모듈에서 오류가 발생하지만 다른 모듈에서는 허용할 수 있습니다.
특정 결정에 필터가 적용되지 않으면 해당 결정을 **기권**하고 필터가 존재하지 않는것처럼 행동합니다.
일반적으로 이 방법은 혼란을 야기할 수 있기때문에 기권할 수 있는 방식으로 필터를 사용하지 않아야 합니다.

그러나 [이벤트 규칙 모듈](/modules/regions#applying)은 매우 복잡한 조건을 쉽게 표현할 수 있도록 필터 기권을 사용합니다.
그것은 필터 *체인*을 허용하고 기권하지 않는 체인의 첫번째 필터를 사용합니다.

필터는 `<allow>` 와 `<deny>` 한정자를 사용하여 **강제로** 기권할 수 있습니다.


### 필터 정의하기
필터는 최상위 `<filters>` 요소 안에 정의될 수 있으며,
다른 곳에서 참조하기 위해 `id` 를 사용합니다.

    <filters>
        <any id="filter-name">
            <!-- 필터 요소 -->
        </any>

        <team id="viridescent-team-filter">viridescent-team</team>

        <!-- 더 많은 필터 -->
    </filters>

<br/>

### 매처 요소 {#list}
필터 매처는 특정 조건이나 사물의 속성을 테스트합니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 300px;'>요소</th>
        <th>설명</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th colspan='3'>일반 필터 (모든 것에 적용)</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<filter id="filter1"/>' | escape_once}}</code>
          </span>
        </td>
        <td>ID로 필터를 참조합니다.</td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<always/>' | escape_once}}</code>
          </span>
        </td>
        <td>
          모든 것을 매치/허용합니다.<br/>
          <code>always</code>로 참조할 수 있습니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<never/>' | escape_once}}</code>
          </span>
        </td>
        <td>
          아무것도 매치하지 않고 모든 것을 거부합니다.<br/>
          <code>never</code>로 참조할 수 있습니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<match-started/>' | escape_once}}</code>
          </span>
        </td>
        <td>
          경기가 시작되었는지 필터링합니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<match-running/>' | escape_once}}</code>
          </span>
        </td>
        <td>
          경기가 진행중인지 필터링합니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<match-finished/>' | escape_once}}</code>
          </span>
        </td>
        <td>
          경기가 끝났는지 필터링합니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<time>duration</time>' | escape_once}}</code>
          </span>
        </td>
        <td>
          경기가 시작된 이후 지정된
          <a href='/reference/time_periods'>시간 단위</a>가 경과한 경우 필터링합니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<completed>objective_id</completed>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#objectiveFilter'><i class="fa fa-chevron-down"></i></a>
          목표가 완료되면 매칭합니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<captured>objective_id</captured>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#objectiveFilter'><i class="fa fa-chevron-down"></i></a>
          현재 목표를 제어하는 플레이어 또는 팀을 매칭합니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<flag-carried>flag_id</flag-carried>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#flagFilter'><i class="fa fa-chevron-down"></i></a>
          깃발이 누군가에 의해 운반되어지고 있다면 매칭합니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<flag-dropped>flag_id</flag-dropped>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#flagFilter'><i class="fa fa-chevron-down"></i></a>
          깃발이 땅에 떨어지면 매칭합니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<flag-returned>flag_id</flag-returned>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#flagFilter'><i class="fa fa-chevron-down"></i></a>
          깃발이 반환 지점에 있으면 매칭합니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<flag-captured>flag_id</flag-captured>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#flagFilter'><i class="fa fa-chevron-down"></i></a>
          깃발이 캡처되면 매칭합니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <th colspan='3'>공간 필터 (물리적 위치가 있는 모든 것들에 적용)</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<void/>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#voidFilter'><i class="fa fa-chevron-down"></i></a>
          이 위치의 수직 축에서 Y = 0에 공기 블럭이 있으면 매칭합니다.
        </td>
        <td></td>
      </tr>
      <tr>
        <td colspan='3'>
          <em>
            모든
            <a href='/modules/regions'>지역</a>
            요소
          </em>
        </td>
      </tr>
      <tr>
        <th colspan='3'>블럭 필터</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<material>block</material>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a href='/reference/inventory#material_finder'>재료</a>
          이름으로 블럭을 찾습니다.
          <br/>
          <a href='/reference/inventory#material_matchers'>단일 재료 패턴</a>을 사용할 수 있습니다.
        </td>
        <td></td>
      </tr>
      <tr>
        <th colspan='3'>엔티티 필터</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<spawn>spawn reason</spawn>' | escape_once}}</code>
          </span>
        </td>
        <td>
          스폰 이벤트 사유를 매칭합니다. <a href='/modules/mobs'>이곳</a>을 참고하세요.
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<mob>mob name</mob>' | escape_once}}</code>
          </span>
        </td>
        <td>
          이름으로 몹을 매칭합니다. <a href='/modules/mobs'>이곳</a>을 참고하세요.
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<entity>entity name</entity>' | escape_once}}</code>
          </span>
        </td>
        <td>엔티티를 매칭합니다. (예: 발사체, 보트, 떨어뜨린 아이템 등)</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='3'>경쟁자 필터 (팀 또는 FFA 플레이어에게 적용)</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<score> </score>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#rank_score'><i class="fa fa-chevron-down"></i></a>
          플레이어 또는 팀의 점수가 지정된 범위 내에 있으면 매칭합니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<carrying-flag>flag_id</carrying-flag>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#flagFilter'><i class="fa fa-chevron-down"></i></a>
          지정된 깃발을 들고 있는 팀 / 플레이어를 매칭합니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <th colspan='3'>플레이어 필터</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<team>team</team>' | escape_once}}</code>
          </span>
        </td>
        <td>ID로 팀을 매칭합니다.</td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight xml'>
            <code>{{'<class>class name</class>' | escape_once}}</code>
          </span>
        </td>
        <td>
          지정된 클래스와 플레이어를 매칭합니다.
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<kill-streak/>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#killStreakFilter'><i class="fa fa-chevron-down"></i></a>
          특정 범위 또는 킬 수로 플레이어를 매칭합니다.
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<crouching/>' | escape_once}}</code>
          </span>
        </td>
        <td>
          플레이어가 웅크리고 있는 경우 매칭합니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<walking/>' | escape_once}}</code>
          </span>
        </td>
        <td>
          플레이어가 걷고 있는 경우 매칭합니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<sprinting/>' | escape_once}}</code>
          </span>
        </td>
        <td>
          플레이어가 달리고 있는 경우 매칭합니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<flying/>' | escape_once}}</code>
          </span>
        </td>
        <td>
          플레이어가 날고 있는 경우 매칭합니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<can-fly/>' | escape_once}}</code>
          </span>
        </td>
        <td>
          플레이어가 날 수 있는지 매칭합니다.
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<grounded/>' | escape_once}}</code>
          </span>
        </td>
        <td>
          플레이어가 땅 위에 있는 경우 매칭합니다.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<carrying><item material=""/></carrying>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#itemFilters'><i class="fa fa-chevron-down"></i></a>
          플레이어가 아이템을 운반하고 있는 경우 매칭합니다.
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<holding><item material=""/></holding>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#itemFilters'><i class="fa fa-chevron-down"></i></a>
          플레이어가 아이템을 들고 있는 경우 매칭합니다.
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<wearing><item material=""/></wearing>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#itemFilters'><i class="fa fa-chevron-down"></i></a>
          플레이어가 아이템을 입고 있는 경우 매칭합니다.
        </td>
        <td></td>
      </tr>
      <tr>
        <th colspan='3'>이벤트 필터 (일시적인 이벤트에 적용)</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<cause>cause</cause>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#causeFilters'><i class="fa fa-chevron-down"></i></a>
          이벤트의 발생 원인을 필터링합니다.
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<random>십진수 또는 범위</random>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#randomFilter'><i class="fa fa-chevron-down"></i></a>
          랜덤 매처입니다.
        </td>
        <td></td>
      </tr>
      <tr>
        <th colspan='3'>데미지 필터 (데미지 / 전투 이벤트 적용)</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<relation>relation</relation>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#relationFilters'><i class="fa fa-chevron-down"></i></a>
          플레이어와 이벤트의 관계를 필터링합니다.
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>
<br/>

### 한정자 요소 {#filterModifiers}

필터 한정자는 다른 필터의 의미를 변경하고 더 복잡한 조건으로 결합하는 데 사용됩니다.
이러한 요소는 하위 요소로 단일 필터 또는 필터 목록을 포함해야 합니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 85px;'>이름</th>
        <th>설명</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th colspan='3'>논리 - 다른 필터 결합</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<not>' | escape_once}}</code>
          </span>
        </td>
        <td>필터 결과를 반전합니다. 하위 필터가 거부하면 허용하고 만약 허용하면 거부합니다. 그렇지 않으면 기권합니다.</td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<one>' | escape_once}}</code>
          </span>
        </td>
        <td>만약 하위 필터 중 <i>하나만</i> 허용하는 경우 허용하고, <i>하나 이상</i> 혹은 <i>어떤 것도 허용하지 않으며 적어도 하나가 거부</i>하는 경우 거부하고, 그렇지 않으면 기권합니다.</td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<all>' | escape_once}}</code>
          </span>
        </td>
        <td><i>모든</i> 하위 필터가 허용하면 허용하고, <i>하나 이상이 거부</i>하면 거부하고, 그렇지 않으면 기권합니다.</td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<any>' | escape_once}}</code>
          </span>
        </td>
        <td>Allow if <i>one</i> of the child filters allows, deny if <i>none allow and at least one denies</i>, otherwise abstain.</td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <th colspan='3'>Abstention - force filters to abstain</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<allow>' | escape_once}}</code>
          </span>
        </td>
        <td>Allow if the child filter allows, otherwise abstain (transform deny to abstain).</td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<deny>' | escape_once}}</code>
          </span>
        </td>
        <td>Deny if the child filter allows, otherwise abstain.</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='3'>Query modifiers - change the question</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<same-team>' | escape_once}}</code>
          </span>
        </td>
        <td>
          Change a player question to a team question.<br/>
          For example, "do they have the flag?" becomes "does their team have the flag?".
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<victim>' | escape_once}}</code>
          </span>
        </td>
        <td>
          Make a damage question specifically about the victim.<br/>
          For example, "do they have the flag?" becomes "does the victim have the flag?"
          <br/>
          Commonly used with the
          <a href='/modules/damage'>damage</a>
          module.
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<attacker>' | escape_once}}</code>
          </span>
        </td>
        <td>
          Make a damage question specifically about the attacker.<br/>
          For example, "do they have the flag?" becomes "does the attacker have the flag?"
          <br/>
          Commonly used in the
          <a href='/modules/damage'>damage</a>
          module.
        </td>
        <td></td>
      </tr>
      <tr>
        <th colspan='3'>Mechanisms - apply complex mechanics to other filters</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<players>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#players'><i class="fa fa-chevron-down"></i></a>
          Count the number of players that match the inner filter.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<countdown>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#countdown'><i class="fa fa-chevron-down"></i></a>
          Countdown from the moment that the inner filter matched.
        </td>
        <td>
          <span class='label label-primary'>동적</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>

Examples

    <filters>
        <not id="deny-yellow-explosions">
            <all>
                <team>yellow</team>
                <cause>explosion</cause>
            </all>
        </not>
    </filters>

````
<filters>
    <deny id="no-tnt"><material>TNT</material></deny>
</filters>
````

The player wants to place a TNT block, the filter gets asked; "Is this block place-able?". The filter checks the `<material>` matcher, it matches and returns `ALLOW`. The material matcher is contained in a `<deny>` modifier so the `ALLOW` gets turned into a `DENY`.

<br/>

#### Kill-Streak Filter {#killStreakFilter}

The kill-streak filter is a matcher that matches players who have a specified number of kills.
The kill counter can be set to count from the start of the match or from the last time the player died.
This filter is commonly used in [kill rewards](/modules/killreward) but can also be used to restrict access to certain locations, etc.


#####  Kill-Streak Filter Attributes

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Attribute</th>
        <th>Description</th>
        <th>Value</th>
        <th>Default</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>min</code>
        </td>
        <td>Match players with at-least this many kills.</td>
        <td>
          <span class='label label-primary'>Number</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>max</code>
        </td>
        <td>Match players with a maximum of this many kills.</td>
        <td>
          <span class='label label-primary'>Number</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>count</code>
        </td>
        <td>
          Match players with exactly this many kills.
          <br/>
          <i>Can not be mixed with the <code>min</code> & <code>max</code> attributes.</i>
        </td>
        <td>
          <span class='label label-primary'>Number</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>repeat</code>
        </td>
        <td>Repeat the filter range</td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
      <tr>
        <td>
          <code>persistent</code>
        </td>
        <td>Do not reset a players kill count when they die.</td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
    </tbody>
  </table>
</div>

Examples

    <kill-streak min="3"/>      <!-- matches players with at least 3 kills -->
    <kill-streak max="5"/>      <!-- matches players with at most 5 kills -->
    <kill-streak count="4"/>    <!-- matches players with exactly 4 kills -->

    <kill-streak id="10th-kill-filter" repeat="true" count="10"/>    <!-- match for every 10th kill -->


<br/>

#### Random Filter {#randomFilter}

This filter will randomly `ALLOW` or `DENY` when evaluated in the context of an event.
Its value is a decimal fraction between 0 and 1, representing the probability of `ALLOW`.

The value can also be an interval, in the form `[0, 1)`.
When the filter is evaluated, a random number is chosen, and the filter passes if the number falls within the filter's interval.
Multiple filters applied to the same object at the same instant will use the same random number.
So, if their intervals do not overlap, the filters will never both pass at the same time.
Using intervals in this way, any number of filters can be made mutually exclusive, or their relationships can be controlled in more complex ways.

A random filter can only be applied to instantaneous events, and not to conditions that persist over some span of time.
Specifically, they can be used in the following contexts:

* Regional block change rules
* Block drop rules
* Damage rules
* Mob spawning rules

In other contexts, random filters will `ABSTAIN`.

Examples

    <!-- 50% chance that it will return either ALLOW or DENY -->
    <random>0.5</random>

    <!-- Also a 50% chance -->
    <!-- Any number from 0.25 to 0.75 including 0.25 but excluding 0.75 -->
    <random>[0.25, 0.75)</random>



<br/>

#### Rank & Score Filters {#rank_score}

The rank and score filters match if the team's or player's rank or score is a equal to a single value or within a range of values.<br/>
The value can be an exact amount or a interval specifying a range. Only whole numbers are valid.

Examples

    <!-- Match if the team (or player in ffa) rank is 3 -->
    <rank>3</rank>

    <!-- Match if team (or player in ffa) has a score from 5 to 10. -->
    <score>[5-10]</score>



<br/>

#### Player Count Filter {#players}

This filter counts the number of players matching a single child filter,
and matches if that count is within a specified range.

The child filter can be omitted, in which case all players in the match will be counted.


#####  Player Count Filter Attributes

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Attribute</th>
        <th>Description</th>
        <th>Value</th>
        <th>Default</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>min</code>
        </td>
        <td>Minimum player count</td>
        <td>
          <span class='label label-primary'>Number</span>
        </td>
        <td>1</td>
      </tr>
      <tr>
        <td>
          <code>max</code>
        </td>
        <td>Maximum player count</td>
        <td>
          <span class='label label-primary'>Number</span>
        </td>
        <td>oo (unlimited)</td>
      </tr>
      <tr>
        <td>
          <code>participants</code>
        </td>
        <td>Include participants (players actually playing) in the count.</td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>true</td>
      </tr>
      <tr>
        <td>
          <code>observers</code>
        </td>
        <td>Include observers in the count.</td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
    </tbody>
  </table>
</div>

Examples

    <!-- Match if there are at least 4 players participating -->
    <players min="4"/>

    <!-- Match if there are 1 to 3 players sneaking in region X -->
    <players min="1" max="3">
        <all>
            <sneaking/>
            <region id="X"/>
        </all>
    </players>

<br/>

#### Countdown Filter {#countdown}

This filter matches for up to the specified amount of time after the child filter starts matching.
It never matches when the child filter doesn't match.


#####  Countdown Filter Attributes

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Attribute</th>
        <th>Description</th>
        <th>Value</th>
        <th>Default</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>duration</code>
        </td>
        <td>Length of time to match for</td>
        <td>
          <span class='label label-primary'>Time Period</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>message</code>
        </td>
        <td>
          Optional timer message to display while counting down.
          Only players who match the filter can see the timer.
          If the message contains a placeholder, it will be replaced with the remaining time.
        </td>
        <td>
          <span class='label label-primary'>Message Template</span>
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>

Examples

    <!-- Countdown 30s from the moment any player picks up the flag -->
    <!-- (you could then use the countdown filter to kill them, teleport them, etc) -->
    <countdown duration="30s" message="You have {0} to capture the flag">
        <carrying-flag>blue-flag</carrying-flag>
    </countdown>



<br/>

#### Objective Filters {#objectiveFilter}

There are two filter types that test the state of an objective: `<completed>` and `<captured>`.
Both types require the ID of an objective as the content of the tag.

The `<completed>` filter matches when the specified objective is completed or captured by anybody e.g.
when a [destroyable](/modules/gamemode_dtm) is destroyed, a [core](/modules/gamemode_dtc) is leaked, or a [hill](/modules/control_points) is captured by anyone.
This filter is not affected by the context in which it is applied, and never abstains.

The `<captured>` filter matches players or teams who currently control the specified objective.
This filter is useful for objectives that can change ownership, such as [hills](/modules/control_points) and [flags](/modules/gamemode_ctf).
For other objective types, it will match players/teams who are *allowed* to complete the objective, if the objective is completed, which is generally not useful.
This filter will abstain if used in a context that does not involve a specific player or team.

Alternately, `<captured>` can have a team specified with the `team` attribute.
Then it will always test that team's control of the objective, regardless of the filtering context, and will never abstain.



#####  Capture Filter Attributes

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Attribute</th>
        <th>Description</th>
        <th>Value</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>team</code>
        </td>
        <td>Match only if the objective is captured/completed by this team.</td>
        <td>
          <a href='/modules/teams'>Team ID</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>

Examples

    <!-- Match if red-core has been leaked -->
    <completed>red-core</completed>

    <!-- Match if south-hill is owned by anyone -->
    <completed>south-hill</completed>

    <!-- Match players/teams who own north-hill -->
    <captured>north-hill</captured>

    <!-- Match if blue-team owns central-hill -->
    <captured team="blue-team">central-hill</captured>



<br/>

#### Flag Filters {#flagFilter}

The flag filters allow filtering of a specific flags current state or for the player that is carrying the flag. One important use of these filters is to implement the standard rule that a team can only capture an enemy flag when their own flag is returned. This can be implemented easily using a `<flag-returned>` as the capture-filter of a flag. This can also be done with the nets return attribute. However, using the return attribute will return dropped flags, while using a filter will not.

The flag carried, dropped, captured and returned filters have an optional `post` attribute to only match if the flag was last returned to that post.

    <!-- The blue flag is currently being carried by a player -->
    <flag-carried>blue-flag</flag-carried>

    <!-- The blue flag has been carried away & dropped from the red-post -->
    <flag-dropped post="red-post">blue-flag</flag-dropped>

    <!-- The yellow flag is standing at one of its posts -->
    <flag-returned>yellow-flag</flag-returned>

    <!-- The yellow flag is standing at the green-post -->
    <flag-returned post="green-post">yellow-flag</flag-returned>

    <!-- The cyan flag has been captured but not yet returned -->
    <flag-captured>cyan-flag</flag-captured>

    <!-- The player currently carrying the purple flag -->
    <carrying-flag>purple-flag</carrying-flag>



<br/>

#### Item Filters {#itemFilters}

These filters can be used to filter for players with specific items in their inventory. They accept a single [item](/modules/items) element. Only the item's type, durability/damage and meta data are compared. A item's meta data includes the item's name, enchantments, etc.

    <!-- Player has a stick named 'Blue Door Key' in their inventory -->
    <carrying><item name="Blue Door Key" material="stick"/></carrying>

    <!-- Player is holding a clock -->
    <holding><item material="clock"/></holding>

    <!-- Player is wearing a chainmail chestplate -->
    <wearing><item material="chainmail chestplate"/></wearing>



<br/>

#### Event Cause Filters {#causeFilters}

Cause filters are used to filter an event or action according to its cause.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Element</th>
        <th>Description</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<cause> </cause>' | escape_once}}</code>
          </span>
        </td>
        <td>Filter an event's cause.</td>
      </tr>
      <tr>
        <th colspan='2'>Cause: Actor Type</th>
      </tr>
      <tr>
        <td>
          <code>WORLD</code>
        </td>
        <td>World events such as ice melting, etc.</td>
      </tr>
      <tr>
        <td>
          <code>LIVING</code>
        </td>
        <td>Events caused by a living entity.</td>
      </tr>
      <tr>
        <td>
          <code>MOB</code>
        </td>
        <td>Events caused by a mob.</td>
      </tr>
      <tr>
        <td>
          <code>PLAYER</code>
        </td>
        <td>Events caused by a player.</td>
      </tr>
      <tr>
        <th colspan='2'>Cause: Block Action</th>
      </tr>
      <tr>
        <td>
          <code>PUNCH</code>
        </td>
        <td>Events where a block is punched.</td>
      </tr>
      <tr>
        <td>
          <code>TRAMPLE</code>
        </td>
        <td>Events where a block is trampled.</td>
      </tr>
      <tr>
        <td>
          <code>MINE</code>
        </td>
        <td>Events where a block is mined.</td>
      </tr>
      <tr>
        <th colspan='2'>Cause: Damage Type</th>
      </tr>
      <tr>
        <td>
          <code>MELEE</code>
        </td>
        <td>
          <code>PROJECTILE</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>POTION</code>
        </td>
        <td>
          <code>EXPLOSION</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>COMBUSTION</code>
        </td>
        <td>
          <code>FALL</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>GRAVITY</code>
          Fall and void damage.
        </td>
        <td>
          <code>VOID</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>SQUASH</code>
        </td>
        <td>
          <code>SUFFOCATION</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>DROWNING</code>
        </td>
        <td>
          <code>STARVATION</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>LIGHTNING</code>
        </td>
        <td>
          <code>CACTUS</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>THORNS</code>
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>
<br/>

#### Player Relation Filters {#relationFilters}

The relation filter is used when a player is damaged to check the relation between them and the damage cause.
This filter is only used in damage related contexts i.e., [damage filters](/modules/damage), and [kill rewards](/modules/killreward)

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Element</th>
        <th>Description</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<relation> </relation>' | escape_once}}</code>
          </span>
        </td>
        <td>The relation between the player and their damage cause.</td>
      </tr>
      <tr>
        <th colspan='2'>Values</th>
      </tr>
      <tr>
        <td>
          <code>NEUTRAL</code>
        </td>
        <td>Event has no attacker, e.g. world damage.</td>
      </tr>
      <tr>
        <td>
          <code>SELF</code>
        </td>
        <td>Events caused by the player. (Same player same team)</td>
      </tr>
      <tr>
        <td>
          <code>ALLY</code>
        </td>
        <td>Events caused by a player on the same team. (Different player same team)</td>
      </tr>
      <tr>
        <td>
          <code>ENEMY</code>
        </td>
        <td>Events caused by an enemy player. (Different team)</td>
      </tr>
    </tbody>
  </table>
</div>
<br/>

#### Structural Load Filters {#structuralLoadFilters}
The structural load filter checks the number of gravity blocks that are attached to the queried block.
It returns `ALLOW` as long as the structural load is greater than or equal to the specified value and `DENY` otherwise.

<span class="label label-warning">Warning</span> This filter is very computationally expensive to apply, XML authors should ensure that it is only run when absolutely necessary, e.g. by placing other filters above it. They should also not apply it to events that modify large amounts of blocks, such as explosions.

This filter requires the falling blocks module to be loaded otherwise it will default to abstain.

Example

    <!--  Deny breaking structures longer than 3 blocks  -->
    <not>
        <all>
            <cause>player</cause>
            <filter name="structure-blocks"/>
            <structural-load>3</structural-load>
        </all>
    </not>



<br/>

#### Void Filter {#voidFilter}

If your map is especially complex shaped you may have to use the `<void/>` tag to shape your filtered region.
The `<void/>` tag checks the specified regions for blocks on the bottom layer of the world. It then creates an outline of those blocks and the specified filter is only active inside or outside that outline. Bridges are usually not detected because they are not at `y=0`. This can be fixed by creating a invisible silhouette of the bridge with block 36 at `y=0`.

Example

    <filters>
        <not id="no-void">
            <void/>
        </not>
    </filters>
    <regions>
        <apply block="no-void" message="You may not modify the void area!">
            <region>
                <rectangle id="main-area" min="65,860" max="290,980"/>
            </region>
        </apply>
    </regions>
