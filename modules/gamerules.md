---
layout: page

category: "모듈"
title:  "게임 규칙"

---

마인크래프트에 내장된 게임 규칙 (gamerule) 은 `<gamerules>` 모듈을 사용하여 설정할 수 있습니다. 모두 가능한 것은 아니고, 밑의 표에 열겨된 것들 중에서만 사용 가능합니다.

일광 주기 (daylight cycle)를 고정하고 싶을 때, `<doDaylightCycle>` 게임 규칙이나, [timelock](/modules/other_settings#timelock) 요소를 사용해야 합니다. 한 구문이 나머지 한 구문을 덮어 쓸 수 있으니, 설정하는 데 있어 일관성 있게 작성해야 합니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>요소</th>
        <th>설명</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<gamerules> </gamerules>' | escape_once}}</code>
          </span>
        </td>
        <td>게임 규칙 정의에 관한 내용을 포함하는 노드</td>
      </tr>
    </tbody>
  </table>
</div>
<h5>지원되는 게임 규칙의 하위 요소</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>요소</th>
        <th>설명</th>
        <th>깂</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<doFireTick>' | escape_once}}</code>
          </span>
        </td>
        <td>불이 번지는 현상이 일어나는지를 토글합니다.</td>
        <td>
          <span class='label label-primary'>참 / 거짓</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<doTileDrops>' | escape_once}}</code>
          </span>
        </td>
        <td>타일 엔티티가 드랍되는지를 토글합니다.</td>
        <td>
          <span class='label label-primary'>참 / 거짓</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<doMobLoot>' | escape_once}}</code>
          </span>
        </td>
        <td>몬스터를 죽이고 얻는 보상 아이템이 드랍되는지를 토글합니다.</td>
        <td>
          <span class='label label-primary'>참 / 거짓</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<mobGriefing>' | escape_once}}</code>
          </span>
        </td>
        <td>크리퍼가 폭발하거나 엔더맨이 블록을 빼가는 등의 몹들로 인해 환경에 피해를 줄 수 있는지를 토글합니다.</td>
        <td>
          <span class='label label-primary'>참 / 거짓</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<naturalRegeneration>' | escape_once}}</code>
          </span>
        </td>
        <td>플레이어들이 자연적으로 체력을 회복 가능한지를 토글합니다.</td>
        <td>
          <span class='label label-primary'>참 / 거짓</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<doDaylightCycle>' | escape_once}}</code>
          </span>
        </td>
        <td>월드의 시간이 흐르는지를 토글합니다.</td>
        <td>
          <span class='label label-primary'>참 / 거짓</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>

예시)

    <gamerules>
        <doDaylightCycle>false</doDaylightCycle>
        <naturalRegeneration>false</naturalRegeneration>
    </gamerules>


<br/>

#### 지원되지 않는 게임 규칙

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>규칙</th>
        <th>이유</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>doMobSpawning</code>
        </td>
        <td>
          <a href='/modules/mobs'>mobs</a>
          모듈 설정을 더 용이하게 하기 위해 지원되지 않습니다.
        </td>
      </tr>
      <tr>
        <td>
          <code>keepInventory</code>
        </td>
        <td>PGM 플러그인이 키트 기능으로 이미 해결이 가능하므로 지원되지 않습니다.</td>
      </tr>
      <tr>
        <td>
          <code>commandBlockOutput</code>
        </td>
        <td>커맨드 블럭이 PGM 플러그인에 의해 기능하지 않으므로 지원되지 않습니다.</td>
      </tr>
      <tr>
        <td>
          <code>logAdminCommands</code>
        </td>
        <td>맵이 기능하는데 굳이 필요하지 않으므로 지원되지 않습니다.</td>
      </tr>
      <tr>
        <td>
          <code>randomTickSpeed</code>
        </td>
        <td>맵이 기능하는데 굳이 필요하지 않으므로 지원되지 않습니다.</td>
      </tr>
      <tr>
        <td>
          <code>reducedDebugInfo</code>
        </td>
        <td>맵이 기능하는데 굳이 필요하지 않으므로 지원되지 않습니다.</td>
      </tr>
      <tr>
        <td>
          <code>sendCommandFeedback</code>
        </td>
        <td>맵이 기능하는데 굳이 필요하지 않으므로 지원되지 않습니다.</td>
      </tr>
      <tr>
        <td>
          <code>showDeathMessages</code>
        </td>
        <td>맵이 기능하는데 굳이 필요하지 않으므로 지원되지 않습니다.</td>
      </tr>
    </tbody>
  </table>
</div>
