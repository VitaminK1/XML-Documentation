---
layout: page

category: "모듈"
title:  "사용자 정의 투사체"

---

사용자가 정의한 투사체들은 [키트](/modules/kits) 내의 아이템에 정의되고 적용될 수 있습니다.
이렇게 만들 아이템들은 사용자 정의 투사체를 쏠 수 있는 무기가 될 수도, 던져질 투사체 그 자체가 될 수 있습니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>투사체 요소</th>
        <th>설명</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<projectiles> </projectiles>' | escape_once}}</code>
          </span>
        </td>
        <td>사용자 정의 투사체를 정의하는 내용을 포함한 노드입니다.</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위 모듈</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<projectile> </projectile>' | escape_once}}</code>
          </span>
        </td>
        <td>
          사용자 정의 투사체의 정의입니다.
        </td>
        <td>
          <span class='label label-default'>투사체 하위 요소</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>투사체의 속성</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 150px;'>속성</th>
        <th>설명</th>
        <th style='min-width: 100px;'>값</th>
        <th style='min-width: 100px;'>기본값</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>id</code>
        </td>
        <td>XML 내 다른 곳에서 이 투사체를 참조하는 데 이용하는 고유의 식별자 입니다.</td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>name</code>
        </td>
        <td>이 투사체가 표시될때 보여지는 이름입니다. 데스메세지에서 "~에 의해 죽었습니다."에서 사용되곤 합니다. </td>
        <td>
          <span class='label label-primary'>String</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>throwable</code>
        </td>
        <td>
          수류탄의 경우처럼, 어떤 아이템으로 투사체를 발사하고 난 뒤 그 아이템이 소모되는지를 설정합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>참</td>
      </tr>
      <tr>
        <td>
          <code>projectile</code>
        </td>
        <td>이 투사체가 어떤 엔티티로써 물질화 될지 설정합니다.</td>
        <td>
          <a href='/reference/entity_types'>엔티티 종류</a>
        </td>
        <td>
          <span class='label label-default'>화살</span>
        </td>
      </tr>
      <tr>
        <td>
          <code>damage</code>
        </td>
        <td>이 투사체가 입히는 데미지의 양입니다.</td>
        <td>
          <span class='label label-primary'>체력</span>
        </td>
        <td>0.0</td>
      </tr>
      <tr>
        <td>
          <code>velocity</code>
        </td>
        <td>투사체가 움직이는 속도입니다.</td>
        <td>
          <span class='label label-primary'>미터/틱</span>
        </td>
        <td>1.0</td>
      </tr>
      <tr>
        <td>
          <code>click</code>
        </td>
        <td>
          투사체를 발사할때 눌러야 하는 클릭 동작입니다.
          <br/>
          <code>right</code>, <code>left</code> 혹은 <code>both</code>가 가능합니다.
        </td>
        <td>
          <span class='label label-primary'>클릭 동작</span>
        </td>
        <td>
          <code>both</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>effects</code>
        </td>
        <td>이 투사체에 의해 맞은 플레이어에게 적용되는 포션효과 입니다.</td>
        <td>
          <a href='/modules/potions'>포션 효과</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>destroy-filter</code>
        </td>
        <td>
          <span class='label label-default' data-toggle='tooltip' title='이것은 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          이 투사체에 무슨 블럭이 맞았을 때 파괴하는지, 그리고 그 여부를 설정합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
        <td>
          <code>deny-all</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>cooldown</code>
        </td>
        <td>투사체를 발사 할 때 필요한 최소한의 시간 간격(쿨타임)입니다.</td>
        <td>
          <a href='/reference/time_periods'>시간</a>
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>
<h5>투사체 하위 요소</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>요소</th>
        <th>설명</th>
        <th>값/하위 모듈</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<destroy-filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' data-toggle='tooltip' title='이것은 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          이 투사체로 무슨 블럭이 맞았을 때 파괴하는지, 그리고 그 여부를 설정합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<effect>' | escape_once}}</code>
          </span>
        </td>
        <td>이 투사체에 맞은 플레이어에게 적용되는 포션 효과입니다.</td>
        <td>
          <a href='/modules/potions'>포션 효과</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
    <!-- 투사체의 서식(template)을 만듭니다. -->
    <projectiles>
        <projectile
            id="lazer"
            name="lazer"
            projectile="Snowball"
            velocity="3.5"
            damage="50"
            throwable="false"
            cooldown="5s"/>
    </projectiles>

    <!-- 투사체를 아이템에 적용합니다. -->
    <kits>
        <kit name="lazer-kit">
            <item projectile="lazer" name="`alazer gun" material="stick"/>
        </kit>
    </kits>


<br/>

### 활이 발사하는 투사체를 수정하기

활은 사용자가 정의한 속도로 다른 투사체가 발사 될 수 있도록 수정 될 수 있습니다. PGM 플러그인은 마인크래프트 게임이 화살에 적용할 때와 같은 공식을 사용해서 투사체가 입히는 데미지를 계산합니다. 이는 마크 내부의 데미지 공식이 속도를 고려할 수 있다는 의미이며, 속도 40으로 날아가는 물고기를 맞을 경우 거의 즉사할 수 있습니다. 또한, 투사체는 사용자가 정의한 대로의 [포션 효과](/modules/potions)를 타겟이 맞았을때 그 타겟에게 적용 시킬 수 있습니다.

`참고:` 이 수정사항은 모든 활의 투사체에 적용되기 때문에, 한 활이 사용자가 정의한 방식과 기존의 방식을 둘다 가질 수 없습니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>투사체 요소</th>
        <th>설명</th>
        <th>값/하위 모듈</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<modifybowprojectile> </...>' | escape_once}}</code>
          </span>
        </td>
        <td>활의 투사체를 수정한 설정에 관한 내용이 담긴 노드</td>
        <td>
          <span class='label label-default'>활 투사체 하위 요소</span>
        </td>
      </tr>
      <tr>
        <td colspan='3'>
          <b>하위 요소</b>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<projectile> </projectile>' | escape_once}}</code>
          </span>
        </td>
        <td>
          활의 투사체로써 사용되는 엔티티입니다.
        </td>
        <td>
          <a href='/reference/entity_types'>엔티티 종류</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<velocityMod> </velocityMod>' | escape_once}}</code>
          </span>
        </td>
        <td>
          활의 투사체에 대한 속도 수정자입니다.
        </td>
        <td>
          <span class='label label-primary'>숫지</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<effect> </effect>' | escape_once}}</code>
          </span>
        </td>
        <td>
          활의 투사체로 맞은 플레이어에게 적용되는 포션 효과입니다.
        </td>
        <td>
          <a href='/modules/potions'>포션 효과</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>

예시)

    <modifybowprojectile>
        <projectile>EnderPearl</projectile>
        <velocityMod>2.5</velocityMod>

        <!-- 투사체의 포션 효과 -->
        <effect duration="5" amplifier="1">poison</effect>
    </modifybowprojectile>

    <modifybowprojectile>
        <effect duration="8" amplifier="1">wither</effect>
    </modifybowprojectile>


다음에 열거되는 모든 투사체들은 작동합니다. 테스트를 거친 엔티티의 목록을 보고 싶다면 [mrapple/Bukkit Entity Spawning.md](https://gist.github.com/4617111)을 참고하세요.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>지원되는 엔티티 종류</th>
        <th></th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>Arrow</code>
        </td>
        <td>
          <code>Egg</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>EnderPearl</code>
        </td>
        <td>
          <code>Fireball</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>LargeFireball</code>
        </td>
        <td>
          <code>SmallFireball</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>Snowball</code>
        </td>
        <td>
          <code>ThrownExpBottle</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>WitherSkull</code>
        </td>
        <td>
          <code>TNTPrimed</code>
        </td>
      </tr>
    </tbody>
  </table>
</div>
