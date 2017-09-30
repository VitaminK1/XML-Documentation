---
layout: page

category: "모듈"
title:  "다른 게임 모드"
nav_content:
  - path: "#rage"
    name: "Rage"
  - path: "#tdm"
    name: "팀 데스매치"
  - path: "#ffa"
    name: "개인전 (Free-For-All)"

---

### Rage {#rage}
_~~원샷원킬~~_ 한방(Rage) 게임 모드를 활성화합니다.

한방킬은 레벨 1 이상의 날카로움 인첸트가 적용된 아이템에만 적용됩니다. 활 역시 레벨 1 이상의 힘 인첸트가 적용된 아이템만 한방킬이 가능합니다.

`참고:` 이 모듈은 독립적으로 사용할 수 없으며 반드시 다른 게임 모드와 함께 사용해야 합니다.

    <rage/>

    <time>8m</time>
    <score>
        <limit>15</limit>
    </score>


<br/>

### 팀 데스매치 {#tdm}
이 게임모드는 [점수](/modules/scoring) 모듈을 사용하여 지정된 시간 동안 게임이 시작되고 가장 높은 점수를 얻은 팀이 승리하는 게임입니다. 팀은 다른 팀의 플레이어를 죽이거나 [스코어 박스](/modules/scoring#score_box)를 통해서 득점할 수 있습니다.

`참고:` 킬과 죽음에 대한 점수를 얻기 위해서는 `<kills>` 과 `<deaths>` 요소가 필요합니다.

    <score>
        <kills>1</kills>    <!-- 매 킬마다 1점을 부여합니다. -->
        <deaths>1</deaths>  <!-- 매 죽음마다 1점을 삭감합니다. -->
    </score>

    <!-- 경기 시간을 설정합니다 (10분) -->
    <time>600</time>


<br/>

### 개인전 (Free-For-All) {#ffa}
개인전 게임 모드는 [팀](/modules/teams) 모듈 대신 [플레이어](/modules/players) 모듈을 사용하여 팀이 없는 경기를 만듭니다.
사용된 모듈에 따라 플레이어는 점수나 제한 시간에 도달하거나 목표를 완료할 때 까지 다른 플레이어를 죽임으로써 점수를 올릴 수 있습니다.

`참고:` 킬과 죽음에 대한 점수를 얻기 위해서는 `<kills>` 과 `<deaths>` 요소가 필요합니다.

    <players max="16" max-overfill="20"/>
    <time>8m</time>

    <score>
        <kills>1</kills>
        <deaths>1</deaths>
    </score>
