---
layout: page

category: "모듈"
title:  "직업"

---

직업 시스템(Classes)은 플레이어가 매치가 시작될 때, 하나의 직업를 고름으로써 각자의 특수한 플레이가 가능하도록 해줍니다. 직업들은 밸런스가 적절하게 짜여졌다면, 어떠한 맵이든지 사용이 가능합니다. 플레이어들은 게임 내에서 매치 도중 `/class` 명령어로 직업를 바꿀 수 있습니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 300px;'>직업 요소</th>
        <th>설명</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<classes> </classes>' | escape_once}}</code>
          </span>
        </td>
        <td>단일 혹은 여러개의 직업에 대한 내용이 담긴 노드</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위모듈</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<class> </class>' | escape_once}}</code>
          </span>
        </td>
        <td>
          단일 플레이어의 직업
        </td>
        <td>
          <span class='label label-default'>직업의 하위 요소</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>직업의 요소</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>요소</th>
        <th>설명</th>
        <th>값</th>
        <th>기본값</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>name</code>
        </td>
        <td>
          <span class='label label-danger'>필수</span>
          직업의 이름으로, 반드시 다른 이름들과 구별이 가능해야 합니다.
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>description</code>
        </td>
        <td>
          <code>/classes</code>
          명령어에 표시되는 설명입니다.
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>longdescription</code>
        </td>
        <td>
          직업 선택 메뉴에 표시되는 설명입니다.
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>icon</code>
        </td>
        <td>
          직업 선택 메뉴에 표시되는 아이콘입니다.
        </td>
        <td>
          <a href='/reference/inventory#material_matchers'>단일 재료 패턴</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>family</code>
        </td>
        <td>
          <span class='label label-danger'>필수</span>
          직업들의 "그룹"입니다. (ghost squadron 의 경우엔 "ghost")
        </td>
        <td>
          <a href='/modules/classes'>직업 Family의 이름</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>sticky</code>
        </td>
        <td>
          만약
          <code>true</code>
          로 설정하면, 플레이어들은 다시 참가지 않고는 도중에 직업를 교체할 수 없습니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      <tr>
        <td>
          <code>default</code>
        </td>
        <td>
          해당 직업가 기본 직업인지 여부를 규정합니다.
          <br/>
          <i>하나의 직업를 반드시 기본 직업로 규정해야 합니다.</i>
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      <tr>
        <td>
          <code>restrict</code>
        </td>
        <td>
          만약
          <code>true</code>
          로 설정하면, OP만 이 직업를 이용할 수 있습니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
    </tbody>
  </table>
</div>
<h5>직업의 하위 요소</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>요소</th>
        <th>설명</th>
        <th>유형</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<kit>' | escape_once}}</code>
          </span>
        </td>
        <td>
          이 직업를 이용하는 플레이어에게 제공되는 키트
        </td>
        <td>
          <a href='/modules/kits'>키트</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>

예시)

    <classes family="ghost" sticky="true">
        <class name="Demon" default="true" description="Smoke and Fire!" icon="fireball">
            <kit>
                <potion duration="oo" amplifier="2" ambient="true">damage resistance</potion>
                <potion duration="oo" amplifier="1" ambient="true">speed</potion>
                <item slot="8" amount="16" material="cooked beef"/>
                <item slot="1" amount="5" name="`3Grenade" grenade="true" material="ender pearl"/>
            </kit>
        </class>
    </classes>
