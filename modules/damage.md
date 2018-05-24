---
layout: page

category: "모듈"
title:  "데미지와 데미지 비활성화"

---

### Friendly Fire (팀원 피해 허용)
팀원끼리 서로에게 데미지를 입히는 것을 허용할 것인가를 설정하는 모듈입니다.
만약 화살로 팀원을 맞추었다면, 그 화살은 그대로 흡수되어 회수 할 수 없습니다.

    <friendlyfire>on</friendlyfire> <!-- 기본값 : off -->

무한 인첸트가 없는 활로 쏜 화살이 팀원을 맞춰서 회수가 안될때, <friendlyfirerefund>를 on으로 설정하면 쏜 사람에게 그 화살이 반환됩니다.

    <friendlyfirerefund>off</friendlyfirerefund> <!-- 기본값 : on -->

<br/>

### Difficulty (게임 내 난이도)
게임 내 난이도를 설정하는 모듈입니다.
난이도는 `peaceful`, `easy`, `normal`, 혹은 `hard`로 설정 될 수 있습니다. 기본값은 `hard` 입니다.

    <difficulty>easy</difficulty> <!-- 기본값 : hard -->

<br/>

### Hunger (허기)
플레이어가 허기가 부족해 죽을 수 있는 지 여부를 규정할 때 쓰이는 모듈입니다.
주로 난이도 설정(Difficulty)과 함께 쓰입니다.<br/>
`naturalRegeneration` [게임 규칙](/modules/gamerules) 과 같이 동반되기도 합니다.

    <hunger>
        <depletion>off</depletion>
    </hunger>

<br/>

### Damage Filtering (데미지 필터링) {#filter}

This module is used to filter when or if damage is applied to entities.
그 안에 적을 내용은 하나의 필터가 될 수도 있고, 필터들의 조합으로 이루어질 수도 있습니다.
하위 요소들 중에서도 `<allow>` and `<deny>` 를 가장 높은 수준의 요소로 적는 것이 좋습니다. 필수는 아니지만, 대부분의 맵이 그렇게 적도록 요구할 것입니다.
지역(Regions)도 한 장소를 필터링하는 필터들로써 사용이 가능합니다.

예시)

    <damage>
        <deny>
            <cause>explosion</cause>
        </deny>
    </damage>

    <!-- 공격자가 레드팀에 있을때 데미지 발생을 허락 하지 않습니다. -->
    <damage>
        <deny>
            <attacker>
                <team>red</team>
            </attacker>
        </deny>
    </damage>

<br/>

### Disable Damage (데미지 비활성화) {#disable}
특정한 원인으로 발생한 데미지를 비활성화할때 사용하는 모듈입니다.

거의 모든 형태의 데미지를 안전하게 비활성화할 수 있지만, `VOID` 데미지는 비활성화 할 경우 정상적인 플레이에 **치명적일 수 있습니다.**  

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>데미지 비활성화 요소</th>
        <th>설명</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<disabledamage> </disabledamage>' | escape_once}}</code>
          </span>
        </td>
        <td>비활성화된 데미지 유형에 관한 내용을 포함하는 노드입니다.</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위 모듈</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<damage> </damage>' | escape_once}}</code>
          </span>
        </td>
        <td>
          비활성화되는 데미지의 종류를 설정합니다.
        </td>
        <td>
          <a href='#causes'>데미지 원인</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>

예시)

    <disabledamage>
        <!-- 착지 데미지 비활성화 -->
        <damage>fall</damage>
    </disabledamage>


<br/>

#### Block Explosion Attributes (블럭으로 인한 폭발 데미지 방지 속성) {#block_explosion}

 블럭으로 인한 폭발 데미지(the `BLOCK_EXPLOSION` damage)의 원인은 누가/무엇이 피해를 입었는지를 커스터마이징하기 위해 더 넓은 범위의 속성들을 가지고 있게 하였습니다. 모든 속성의 기본값은 `true` 이기 때문에 `false`를 값으로 가지게할 속성들만 명확하게 정의하면 될 것입니다.

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
          <code>ally</code>
        </td>
        <td>폭발을 일으킨 사람과 같은 팀에 속한 플레이어들이 입는 데미지를 방지 </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>참</td>
      </tr>
      <tr>
        <td>
          <code>self</code>
        </td>
        <td>폭발을 일으킨 사람 스스로가 입는 데미지를 방지</td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>참</td>
      </tr>
      <tr>
        <td>
          <code>enemy</code>
        </td>
        <td>폭발을 일으킨 사람과 다른 팀에 속한 플레이어들이 입는 데미지를 방지</td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>참</td>
      </tr>
      <tr>
        <td>
          <code>other</code>
        </td>
        <td>위에 언급된 데미지 외에 폭발로 인한 다른 데미지를 방지</td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>참</td>
      </tr>
    </tbody>
  </table>
</div>

예시)

    <disabledamage>
        <!-- TNT가 적과 자신에게는 피해를 주지만, 팀원에게는 주지 않습니다. -->
        <damage ally="true" self="false" enemy="false" other="false">block explosion</damage>
    </disabledamage>


<br/>

#### Damage Causes (데미지 원인) {#causes}
다음의 열거된 데미지 원인들이 데미지 비활성화 모듈에서 이용이 가능합니다.
이러한 원인들은 굳이 전부 대문자로 적거나 밑줄로 띄어쓰기를 표시할 필요는 없습니다. 예를 들어, `FIRE_TICK` 와 `fire tick`는 둘 다 동일하게 작동할 것입니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>이름</th>
        <th>설명</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>CONTACT</code>
        </td>
        <td>
          선인장에 찔리는 것 처럼, 특정 블럭과의 접촉으로 발생하는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>ENTITY_ATTACK</code>
        </td>
        <td>
          한 엔티티가 다른 엔티티를 공격함으로서 발생하는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>PROJECTILE</code>
        </td>
        <td>
          발사체를 맞아서 발생하는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>SUFFOCATION</code>
        </td>
        <td>
          블럭 안에 갇혀서 발생하는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>FALL</code>
        </td>
        <td>
          한 엔티티가 4블럭 이상 떨어져서 발생하는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>FIRE</code>
        </td>
        <td>
          불과 직접적으로 접촉해서 발생하는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>FIRE_TICK</code>
        </td>
        <td>
          플레이어가 화상을 입어 발생하는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>MELTING</code>
        </td>
        <td>
          녹는 눈사람이 받는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>LAVA</code>
        </td>
        <td>
          용암과 직접적으로 접촉해서 발생하는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>DROWNING</code>
        </td>
        <td>
          물 속에 있을 때 공기가 부족해서 발생하는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>BLOCK_EXPLOSION</code>
        </td>
        <td>
          블럭이 폭발 할 때 그 근처에 있을 경우 받는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>ENTITY_EXPLOSION</code>
        </td>
        <td>
          크리퍼 같은 엔티티가 폭발할 때 그 근처에 있을 경우 받는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>VOID</code>
        </td>
        <td>
          보이드로 떨어져서 받는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>LIGHTNING</code>
        </td>
        <td>
          번개에 맞아서 받는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>SUICIDE</code>
        </td>
        <td>
          "/kill" 명령어를 사용 했을때 스스로에게 주는 죽을 만큼의 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>STARVATION</code>
        </td>
        <td>
          허기가 다 떨어져서 받는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>POISON</code>
        </td>
        <td>
          지속되는 독 효과에 의해 발생하는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>MAGIC</code>
        </td>
        <td>
          즉시 피해 포션 혹은 마법(spell)에 맞아서 발생하는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>WITHER</code>
        </td>
        <td>
          위더 효과에 의해 발생하는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>FALLING_BLOCK</code>
        </td>
        <td>
          모루 등의 떨어질때 맞으면 피해를 주는 블럭으로 받은 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>THORNS</code>
        </td>
        <td>
          가시 인첸트에 의해 다른 공격에 대한 반발로 발생하는 데미지
        </td>
      </tr>
      <tr>
        <td>
          <code>CUSTOM</code>
        </td>
        <td>
          사용자가 정의한 유형의 데미지
        </td>
      </tr>
    </tbody>
  </table>
</div>

출처 : [bukkit docs - Damage Cause](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/entity/EntityDamageEvent.DamageCause.html)
