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
        <th>기본값</th>
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
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 이 규칙이 적용되는 영역을 나타냅니다.
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
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 이 규칙이 적용될 때 플레이어에게 키트를 줍니다.
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
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 플레이어가 블럭을 칠 때 이 규칙이 확인됩니다.
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
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 플레이어가 블럭 위를 걸을 때 이 규칙이 확인됩니다.
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
        <th style="min-width: 64px;">기본값</th>
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
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 이 규칙에 의해 수정되는 블럭을 필터링 합니다.
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
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 이 규칙이 적용되는 영역을 나타냅니다.
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
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 이 규칙이 적용될 때 플레이어에게 키트를 줍니다.
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
        <td>일치하는 블럭이 파괴되었을 때 드롭되는 아이템을 설정합니다.</td>
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
        <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 경험치가 드롭되는 양을 설정합니다.
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
          <span class='highlight'>
            <code>{{'<wrongtool>' | escape_once}}</code>
          </span>
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
          <span class='highlight'>
            <code>{{'<punch>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 어드벤처 모드의 플레이어가 블럭을 칠 때 이 규칙이 확인됩니다.
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
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 플레이어가 블럭 위를 걸을 때 이 규칙이 확인됩니다.
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
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 블럭이 폭발할 때 떨어지는 블럭으로 바뀌는 확률을 나타냅니다.
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
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 떨어지는 블럭이 땅에 닿을 경우 실제 블럭으로 바뀌는 확률을 나타냅니다.
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
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 폭발로 인해 날아가는 블럭의 속도를 나타냅니다.
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
          아이템이 실제로 드롭될 가능성을 나타냅니다.
        </td>
        <td>
          <span class='label label-primary'>0 - 1.0</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>

`<filter>` 요소는 특정한 블럭의 규칙을 제한하도록 사용됩니다. 만약 여러개의 필터가 나열된 경우 규칙이 일치하면 규칙이 적용됩니다. 일반적으로 이 필터는 규칙을 적용 할 블럭만 필터링하는 데 사용됩니다. `<team>`과 같은 필터를 사용하면 블럭이 일치하지 않는 플레이어에 의해 파괴된 경우 아이템이나 경험치가 드롭되지 않지만 `<replacement>`규칙은 계속 적용됩니다.

`<drops>` 요소에서 지정된 아이템은 사용자 정의 이름, 인챈트, 속성등과 같은 아무 속성을 가질 수 있습니다. 또한 실제로 떨어질 `확률`을 지정할 수도 있습니다. 이 값의 범위는 0에서 1까지이며 0.5의 값은 한 번 부술때마다 50%의 확률로 아이템을 드롭한다는 것을 의미합니다.  

기본적으로, "잘못된" 도구를 가지고 블럭을 파괴하면 사용자 지정 아이템이 드롭되지 않습니다. `예: 돌 삽으로 돌을 캔 경우`
만약 `wrongtool`이 참으로 설정되면, 어떤 도구를 사용해서 블럭을 파괴한 것과 상관없이 사용자 지정 아이템이 드롭될 것 입니다.

예시

    <block-drops>
        <rule wrong-tool="false">
            <region>
                <cuboid min="1,2,3" max="4,5,6"/>
            </region>
            <!-- 철 블럭과 광석이 철괴와 1 경험치를 드롭하게 만듭니다.  -->
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
            <!-- 파괴된 철 블럭과 광석을 돌로 대체합니다. -->
            <replacement>stone</replacement>
        </rule>
    </block-drops>
<p>
  <a class='btn btn-primary btn-xs btn-more collapsed' data-target='#collapse-simple-example' data-toggle='collapse'></a>
</p>
<div class='collapse' id='collapse-simple-example' markdown='1'>

    <block-drops>
        <!-- 에메랄드 광석을 캘 때 50%의 확률로 돌을 드롭합니다. -->
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
        <!-- 상자가 부서질 경우 플레이어에게 'chest-kit'을 지급합니다. -->
        <rule kit="chest-kit">
            <filter>
                <material>chest</material>
            </filter>
        </rule>
    </block-drops>

</div>
<br/>

#### 블럭을 칠 때
`punch` 속성이나 하위 요소는 어드벤처 모드에 있는 플레이어가 블럭을 칠 때 해당 규칙을 검사할지 여부를 지정합니다. `punch`속성이 참으로 설정된 규칙은 블럭이 파괴되었을 때도 계속 적용되므로 이 행동을 바꾸고 싶다면 `<cause>punch<cause>` 혹은 `<cause>mine<cause>` 필터를 사용해야 합니다.

    <block-drops>
        <!-- 10%의 확률로 잎을 치거나 파괴되었을 때 막대기를 드롭합니다. -->
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

`trample` 속성이나 하위 요소를 참으로 설정하면 플레이거가 블럭위를 걸어갈 때 발생하는 일을 사용자 정의 할 수 있습니다. 이것은 플레이어가 잔디 위를 걸었을 때 흙으로 바뀌게 하거나, 해당 블럭 위를 걸었을 때 아이템을 드롭할 수 있게 해줍니다.

`trample`속성은 플레이어가 그 블럭은 부순 후에도 적용됩니다. `<cause>trample</cause>` 필터를 사용하여 이 동작을 비활성화 할 수 있습니다.

또한, 무작위 필터와 함께 사용되는 `<sprinting/>`, `<walking/>` 및 `<crouching/>` 필터를 사용하여 `trample` 규칙을 적용할 수 있는 확률을 조정할 수 있습니다.

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

폭발에 의해서 공중에 있는 블럭은 다른 모든 드롭 규칙들과 함께 수정할 수 있습니다.


##### 하위 요소 규칙

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>요소</th>
        <th>설명</th>
        <th>값/하위</th>
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
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 블럭이 폭발할 때 떨어지는 블럭으로 바뀌는 확률을 나타냅니다.
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
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 떨어지는 블럭이 땅에 닿을 경우 실제 블럭으로 바뀌는 확률을 나타냅니다.
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
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span> 폭발로 인해 날아가는 블럭의 속도를 나타냅니다.
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>



    <block-drops>
        <rule>
            <!-- 폭발에 의해 부서진 블럭의 50%가 떨어지는 블럭 혹은 날아가는 블럭으로 바뀝니다. -->
            <fall-chance>0.5</fall-chance>
            <!-- 떨어지는 블럭이 땅에 닿을 경우 80%의 확률로 땅에 설치됩니다. -->
            <land-chance>0.8</land-chance>
       </rule>

        <!-- central-region에서 블럭의 날아가는 속도를 50% 증가시킵니다. -->
        <rule fall-speed="1.5">
            <region>
                <region id="central-region"/>
            </region>
       </rule>
    </block-drops>
