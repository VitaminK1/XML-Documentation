---
layout: page

category: "참고 자료"
title:  "아이템 속성"

---

이 속성을 지닌 아이템을 가지고 있거나 착용하고 있는 플레이어나 몹은 효과가 자신에게 적용됩니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>이름</th>
        <th>설명</th>
        <th style="min-width: 60px;">기본값</th>
        <th style="min-width: 60px;">최소값</th>
        <th style='min-width: 60px;'>최대값</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>generic.maxHealth</code>
        </td>
        <td>몹의 최대 체력량을 결정합니다.</td>
        <td>20.0</td>
        <td>0.0</td>
        <td>1.7x10<sup>308</sup></td>
      </tr>
      <!-- %tr -->
      <!-- %td -->
      <!-- %code generic.followRange -->
      <!-- %td The range in blocks within which a mob with this attribute will target players or other mobs to track. Exiting this range will cause the mob to cease following the player/mob. Actual value used by most mobs is 16; for Zombies it is 40. -->
      <!-- %td 32.0 -->
      <!-- %td 0.0 -->
      <!-- %td 2048.0 -->
      <tr>
        <td>
          <code>generic.knockbackResistance</code>
        </td>
        <td>
          공격, 폭발, 투사체에 의한 넉백을 줄여줍니다.
          <br/>
          <i>1.0으로 설정하면 절대 밀려나지 않습니다</i>
        </td>
        <td>0.0</td>
        <td>0.0</td>
        <td>1.0</td>
      </tr>
      <tr>
        <td>
          <code>generic.movementSpeed</code>
        </td>
        <td>물체의 이동 속도를 나타냅니다. 몹의 최대 속도는 초당 블럭 수의 43배가 넘지만 다양한 조건에 의해 값이 달라질 수 있습니다.</td>
        <td>0.7</td>
        <td>0.0</td>
        <td>1.7x10<sup>308</sup></td>
      </tr>
      <tr>
        <td>
          <code>generic.attackDamage</code>
        </td>
        <td>하트 반칸에 의한 피해량을 나타냅니다.</td>
        <td>2.0</td>
        <td>0.0</td>
        <td>1.7x10<sup>308</sup></td>
      </tr>
      <tr>
        <td>
          <code>generic.armor</code>
        </td>
        <td>갑옷의 방어도를 나타냅니다.</td>
        <td>0.0</td>
        <td>0.0</td>
        <td>30.0</td>
      </tr>
    </tbody>
  </table>
</div>

[Minecraft Wiki Attributes](http://minecraft.gamepedia.com/Attribute)에서 복사되었습니다
