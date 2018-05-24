---
layout: page

category: "모듈"
title:  "포션 효과"

---

포션 효과를 나타내는 `<effect>` 요소는 플레이어에게 포션 효과를 직접 적용하기 위해 킷 내에서 사용되기도 하고, [potion bottle item](/modules/items#potions) 에 사용자 정의 효과를 주기 위해 사용되기도 합니다.

효과 지속 시간(Duration)은 포션이 얼마나 오래 지속될 것인가를 규정하는 수치이고, 효과 증폭 정도 (amplifier)는 그 포션의 효과가 어느 수준으로 강력한지를 정하는 수치입니다.
포션 효과의 종류는 [Minecraft ID](http://minecraft.gamepedia.com/Data_values#Status_effects) 로 정할 수 있습니다.
포션 효과의 ID는 `minecraft:`를 앞에 접두사로 붙이지 않고 적어야 합니다.
<h5>포션 효과 요소</h5>
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
            <code>{{'<effect> </effect>' | escape_once}}</code>
          </span>
        </td>
        <td>
          포션 효과를 지정하는 요소
        </td>
        <td>
          <a href='http://minecraft.gamepedia.com/Data_values#Status_effects'>상태 효과 ID</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>포션 효과의 속성</h5>
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
          <code>duration</code>
        </td>
        <td>
          포션효과의 지속 시간을 나타낸다.
        </td>
        <td>
          <a href='/reference/time_periods'>시간의 단위</a>
        </td>
        <td>
          oo
          (무한)
        </td>
      </tr>
      <tr>
        <td>
          <code>amplifier</code>
        </td>
        <td>
          포션 효과의 강도를 나타낸다. 이 값은 게임 내에 플레이어에게 표시되는 효과의 레벨과 일치하므로, 레벨 I의 포션효과를 적용하고 싶다면, amplifier를 1로 설정한다.
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td>1</td>
      </tr>
    </tbody>
  </table>
</div>
<h5>예시</h5>
    <effect duration="10" amplifier="4">resistance</effect>
    <effect duration="900" amplifier="1">jump_boost</effect>
