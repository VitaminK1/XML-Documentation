---
layout: page

category: "모듈"
title:  "블럭 드롭"

---


이 모듈은 블럭이 부서졌을 때 무엇을 드롭하는지, 부셔진 블럭이 무엇을 대체하는지 원하는 대로 사용할 수 있습니다. 그 모듈은 심지어 플레이어가 어드벤처 모드에서 펀치했을 때 드롭을 원하는 대로 설정하거나, 플레이어가 해당 블럭을 밟을 때에 블럭을 변화시킬 때에 사용할 수도 있습니다. 모든 하위 요소들은 선택적이고, 만약 모든 블럭에 요소가 없을 때 아무것도 드롭하지 않습니다.

사용자 지정 드롭은 심지어 블럭이 TNT에 의해 폭발할 때에도 적용됩니다. 사용자 지정 드롭은 기존의 폭발과 같이 70% 감소되지만, 원하는 대로 [TNT 모듈](/modules/tnt) 설정이 가능합니다. 블럭을 캐거나 폭발 이외의 방법으로 부서진 블록은 현재 사용자 정의 드롭를 야기하지 않습니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>요소</th>
        <th>설명</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<block-drops> </block-drops>' | escape_once}}</code>
          </span>
        </td>
        <td>설정된 블록 드롭 규칙이 모두 포함된 노드입니다.</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<rule>' | escape_once}}</code>
          </span>
        </td>
        <td>개별적인 블록 드롭 규칙입니다.</td>
        <td>
          <span class='label label-default'>하위 요소 규칙</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>규칙 속성</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>속성</th>
        <th>설명</th>
        <th>값</th>
        <td>기본값</td>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>filter</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 이 규칙에 의해 블럭이 수정될 수 있습니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>region</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 이 규칙에 해당하는 지역을 말합니다.
        </td>
        <td>
          <a href='/modules/regions'>지역</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>kit</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 이 규칙이 적용되면 플레이어에게 키트를 제공합니다.
        </td>
        <td>
          <a href='/modules/kits'>키트 ID</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>experience</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 경험치가 드롭되는 양을 설정합니다.
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>replacement</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 파괴한 블럭을 대체할 대상을 설정합니다.
        </td>
        <td>
          <a href='/reference/inventory#material_matchers'>단일 재료 패턴</a>
        </td>
        <td>
          <span class='label label-default'>공기</span>
        </td>
      </tr>
      <tr>
        <td>
          <code>wrongtool</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 블럭을 부수는 도구에 상관없이 아이템을 드롭할 수 있게 합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      <tr>
        <td>
          <code>punch</code>
        </td>
        <td>
          블럭을 펀치했을때 이 규칙을 확인하는
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> Check this rule when a block is punched.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      <tr>
        <td>
          <code>trample</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> Check this rule when a block is walked on.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
    </tbody>
  </table>
</div>
<h5>하위요소 규칙</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 125px;'>요소</th>
        <th>설명</th>
        <th>값/하위</th>
        <th>기존 설정</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          이 규칙에 의해 무슨 블럭이 수정되어야 하는지에 대한
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<region>' | escape_once}}</code>
          </span>
        </td>
        <td>
          이 규칙이 적용되는 지역을 정하는
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>.
        </td>
        <td>
          <a href='/modules/regions'>지역</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<kit>' | escape_once}}</code>
          </span>
        </td>
        <td>
          이 규칙이 적용되면 플레이어에게 키트를 주는
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>.
        </td>
        <td>
          <a href='/modules/kits'>키트</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<drops>' | escape_once}}</code>
          </span>
        </td>
        <td>일치하는 블럭이 파괴되었을 때 어느 아이템을 드롭해야 하는지에 대한 속성.</td>
        <td>
          <a href='/modules/items'>아이템</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<experience>' | escape_once}}</code>
          </span>
        </td>
        <td>
          드롭되는 경험치 수량에 대한
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>.
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<replacement>' | escape_once}}</code>
          </span>
        </td>
        <td>
          파괴된 블럭을 무엇으로 대체할지에 대한
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>.
        </td>
        <td>
          <a href='/reference/inventory#material_matchers'>단일 재료 패턴</a>
        </td>
        <td>
          <span class='label label-default'>공기</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<wrongtool>' | escape_once}}</code>
          </span>
        </td>
        <td>
          블럭을 부수는데 무슨 도구를 사용하는지에 대해 관계 없이 아이템을 드롭하는
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<punch>' | escape_once}}</code>
          </span>
        </td>
        <td>
          플레이어가 어드벤쳐 모드에서 블럭을 펀치했을 때 규칙을 확인하는
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<trample>' | escape_once}}</code>
          </span>
        </td>
        <td>
          플레이어가 블럭을 걸어다녔을 때 규칙을 확인하는
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<fall-chance>' | escape_once}}</code>
          </span>
        </td>
        <td>
          폭발할 때, 블럭이 떨어지는 블럭으로 바뀔 확률에 대한
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>.
        </td>
        <td>
          <span class='label label-primary'>0 - 1.0</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<land-chance>' | escape_once}}</code>
          </span>
        </td>
        <td>
          떨어지는 블럭이 바닥에 닿으면 다시 원래 블럭으로 바뀔 확률에 대한
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>.
        </td>
        <td>
          <span class='label label-primary'>0 - 1.0</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<fall-speed>' | escape_once}}</code>
          </span>
        </td>
        <td>
          블럭이 폭발해서 뛰어나간 블럭의 속도에 대한 승수에 관한
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>.
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
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
        <th>블럭 드롭 아이템 속성</th>
        <th>설명</th>
        <th>값</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>chance</code>
        </td>
        <td>
          아이템이 실제로 드롭될 가능성입니다.
        </td>
        <td>
          <span class='label label-primary'>0 - 1.0</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>

`<filter>` 요소는 특정한 블럭의 규칙을 제한하도록 사용됩니다. 만약 여러 필터가 사용되면, 그것 중에 무언가 일치하면 규칙이 적용될 것입니다. 이 필터는 대부분 오직 무엇의 블럭이 규칙에 적용되는지에 사용됩니다. 만약 필터가 `<team>`과 같은게 사용되면 일치하지 않는 플레이어가 블럭을 부셨을 때 아이템이나 경험치를 받을 수 없으나, 규칙 `<replacement>` 재료가 효과가 있을 것입니다.

`<drops>` 요소에서 정해진 아이템은 사용자 지정 이름, 인챈트, 속성과 같은 아무 아이템의 속성을 가질 수 있습니다. 그것들은 명시된 아이템이 드롭될 확률에 따라 특별한 `확률`을 가질 수 있습니다. 이 값은 0에서 1까지, 0.5의 값은 한 번 부술때마다 50%의 확률로 아이템을 가질 수 있다는 뜻입니다.
기본적으로, "잘못된" 도구를 가지고 블럭을 부셨을 부셨을 때, 사용자 지정 드롭이 나타나지 않을 것입니다. 예시: 돌 삽으로 돌을 캤을 때.
만약 `wrongtool`이 참으로 설정되었을때, 무슨 도구를 썼을 때와 상관없이 사용자 지정 드롭이 나타날 것입니다.

예시

    <block-drops>
        <rule wrong-tool="false">
            <region>
                <cuboid min="1,2,3" max="4,5,6"/>
            </region>
            <!-- Make iron blocks and ore drop iron ingots, and 1 XP -->
            <filter>
                <any>
                    <material>iron ore</material>
                    <material>iron block</material>
                </any>
            </filter>
            <drops>
                <item material="iron ingot"/>
            </drops>
            <experience>1</experience>
            <!-- Replace mined iron blocks and ore with stone -->
            <replacement>stone</replacement>
        </rule>
    </block-drops>
<p>
  <a class='btn btn-primary btn-xs btn-more collapsed' data-target='#collapse-simple-example' data-toggle='collapse'>예시</a>
</p>
<div class='collapse' id='collapse-simple-example' markdown='1'>

    <block-drops>
        <!-- Emerald ore blocks drop ore instead of emerald items, -->
        <!-- with a 50% chance of also dropping a stone block. -->
        <rule>
            <filter>
                <material>emerald ore</material>
            </filter>
            <drops>
                <item material="emerald ore"/>
                <item chance="0.5" material="stone"/>
            </drops>
        </rule>
    </block-drops>

    <block-drops>
        <!-- When a chest is broken give the player the 'chest-kit'. -->
        <rule kit="chest-kit">
            <filter>
                <material>chest</material>
            </filter>
        </rule>
    </block-drops>

</div>
<br/>

#### 블럭 펀치
`punch` 속성이나 하위 요소가 만약 플레이어가 어드벤처 모드에서 블럭을 펀치해서 규칙이 확인되었을 때 명시됩니다. 만약 블럭이 부셔졌을 때 펀치 속성이참으로 설정되었을 때에 규칙이 적용될 것입니다. 만약 이 행동을 바꾸고 싶다면 `<cause>punch<cause>` 아니면 `<cause>mine<cause>` 필터가 사용될 수 있습니다.

    <block-drops>
        <!-- 10% chance that a leaf block will drop a stick when it's punched or broken -->
        <rule punch="true">
            <filter>
                <material>leaves</material>
            </filter>
            <drops>
                <item chance="0.1" material="stick"/>
            </drops>
        </rule>
    </block-drops>

<br/>

#### 블럭 트램플린

`trample` 속성이 설정되었을 때 아니면 하위 요소가 참으로 설정되었을 때 플레이어가 해당 블럭을 걸었을때 일어나는 일을 설정할 수 있도록 허용해 줍니다.
이것은 플레이어가 잔디를 걸었을 때 흙으로 바뀌게 하거나, 해당 블럭을 걸었을 때 아이템을 드롭할 수 있게 허용해 줍니다.

만약 플레이어가 특정한 블럭을 부술 때 트램플 설정이 허용된 상태로 유지됩니다. `<cause>trample</cause>` 필터가 이 행동을 비활성화시킬 수 있습니다.

추가로, 무작위 필터 조합에 사용된 `<sprinting/>`, `<walking/>` & `<crouching/>` 필터가 트램플 규칙에 적용된 확률을 수정할 수 있게 사용할 수 있습니다.
    <block-drops>
        <rule trample="true">
            <filter>
                <all>
                    <material>grass</material>
                    <cause>trample</cause>
                    <any>
                        <all>
                            <sprinting/>
                            <random>0.3</random>
                        </all>
                        <all>
                            <walking/>
                            <random>0.1</random>
                        </all>
                        <all>
                            <crouching/>
                            <random>0.05</random>
                        </all>
                    </any>
                </all>
            </filter>
            <replacement>dirt</replacement>
        </rule>
    </block-drops>

<br/>

#### 폭발 행동

폭발에 의해서 공중에 있는 블럭은 다른 모든 드롭 규칙들에 더하여 수정될 수 있습니다.


##### 하위 요소 규칙

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Element</th>
        <th>Description</th>
        <th>Value/Children</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<fall-chance>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          The percentage of blocks that will change to falling blocks when exploded.
        </td>
        <td>
          <span class='label label-primary'>0 - 1.0</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<land-chance>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          The percentage of falling blocks that will change back to real blocks when they land.
        </td>
        <td>
          <span class='label label-primary'>0 - 1.0</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<fall-speed>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          A multiplier for the velocity of the blocks flying out from a explosion.
        </td>
        <td>
          <span class='label label-primary'>Number</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>



    <block-drops>
        <rule>
            <!-- 50% of blocks broken by an explosion get turned into falling/flying blocks -->
            <fall-chance>0.5</fall-chance>
            <!-- 80% of the falling blocks will be placed when they land -->
            <land-chance>0.8</land-chance>
       </rule>

        <!-- Increase the speed of flying blocks by 50% in the central region -->
        <rule fall-speed="1.5">
            <region>
                <region id="central-region"/>
            </region>
       </rule>
    </block-drops>
