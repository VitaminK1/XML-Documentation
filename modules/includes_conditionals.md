---
layout: page

category: "모듈"
title:  "Include 파일과 조건문"
nav_content:
  - path: "#includes"
    name: "XML Include 파일"
  - path: "#conditionals"
    name: "조건문"

---

### XML Include 파일 {#includes}
XML 파일은 여러 파일로 분할한 다음 Include 요소를 사용하여 주 맵 XML에 포함시킬 수 있습니다. 이렇게 하면 키트나 클래스 같은 섹션을 포함하여 메인 파일을 더 체계적으로 보관할 수 있습니다.

    <include src="classes.xml"/>

Game 플러그인은 include에 대한 플러그인 전체 포함경로를 살펴보고, 플러그인이 있는 위치로부터 상대 경로를 찾습니다. 그리고 같은 의미를 가지고 있는 Include체인을 설정할 수 있습니다.

Include된 XML 파일에는 XML 헤더와 기본 맵 컨테이너가 있어야 합니다.

예시

    <?xml version="1.0"?>
    <map proto="{{site.current_proto}}">

    <!-- 키트, 클래스와 같은것들을 이곳에다기 추가합니다. -->

    </map>

마스터 맵 저장소에는 다음과 같이 미리 만들어진 XML 파일이 포함되어 있습니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>파일</th>
        <th>설명</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <a href='https://maps.oc.tc/tutorial.xml'>tutorial.xml</a>
        </td>
        <td>튜토리얼의 시작 단계와 끝 단계를 포함하고 있습니다.</td>
      </tr>
      <tr>
        <td>
          <a href='https://maps.oc.tc/continuity-tnt.xml'>continuity-tnt.xml</a>
        </td>
        <td>BoomBox와 같은 맵에서 사용되는 사전 설계된 TNT인벤토리를 포함하고 있습니다.</td>
      </tr>
      <tr>
        <td>
          <a href='https://maps.oc.tc/blasternauts.xml'>blasternauts.xml</a>
        </td>
        <td>'blasternauts'라는 아케이드 게임의 기본 XML을 포함하고 있습니다.</td>
      </tr>
      <tr>
        <td>
          <a href='https://maps.oc.tc/Blitz/blitz-global.xml'>blitz-global.xml</a>
        </td>
        <td>Blitz 맵들을 위한 자동 리스폰 기능을 포함하고 있습니다.</td>
      </tr>
      <tr>
        <td>
          <a href='https://maps.oc.tc/Blitz/GS/gs.xml'>gs.xml</a>
        </td>
        <td>Ghost Squadron 게임 모드를 위해 미리 만들어진 클래스를 포함하고 있습니다.</td>
      </tr>
      <tr>
        <td>
          <a href='https://maps.oc.tc/Blitz/GS/gs-ffa.xml'>gs-ffa.xml</a>
        </td>
        <td>Ghost Squadron FFA 게임 모드를 위해 미리 만들어진 팀을 포함하고 있습니다.</td>
      </tr>
      <tr>
        <td>
          <a href='https://maps.oc.tc/Include/skywars.xml'>skywars.xml</a>
        </td>
        <td>SkyWars의 기본 XML을 포함하고 있습니다.</td>
      </tr>
      <tr>
        <td>
          <a href='https://maps.oc.tc/Include/block-runner.xml'>block-runner.xml</a>
        </td>
        <td>'block runner'라는 아케이드 게임의 기본 XML을 포함하고 있습니다.</td>
      </tr>
      <tr>
        <td>
          <a href='https://maps.oc.tc/Include/disable-boat-crafting.xml'>disable-boat-crafting.xml</a>
        </td>
        <td>모든 종류의 보트를 만들 수 없게 하는 XML을 포함하고 있습니다.</td>
      </tr>
    </tbody>
  </table>
</div>
<br/>

### 조건문 {#conditionals}

XML 파일에는 간단한 `<if>` 및 `<unless>` [조건문][1]이 포함될 수 있습니다. 이러한 조건은 중복된 맵 파일을 줄이고 여러 변형된 맵을 관리하는 데 사용할 수 있습니다. 예를 들어 여러개의 폴더에 여러개의 변형된 맵이 있는 대신 하나의 깔끔한 위치로 줄어들 수 있습니다. 또한 조건문을 사용하면 맵 변형을 특정 서버 또는 특정 휴일 이벤트 중에 자동으로 로드할 수 있습니다.

조건문은 XML의 어디에서나 사용할 수 있으며 모든 것을 포함할 수 있습니다. Game 플러그인이 XML을 분석할 때 거짓인 조건문은 건너 뜁니다.

현재 조건문에는 두가지 제한 사항이 있습니다:
속성은 오직 참 / 거짓으로만 정의될 수 있으며 조건문은 Game 플러그인 서버 설정에 의해 정의됩니다.


[1]: https://en.wikipedia.org/wiki/Conditional_%28computer_programming%29

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
            <code>{{'<if a="true"> </if>' | escape_once}}</code>
          </span>
        </td>
        <td>
          a가 참이면 이 요소의 내용을 사용합니다.
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<if a="true" b="true"> </if>' | escape_once}}</code>
          </span>
        </td>
        <td>
          만약 a와 b가 둘 다 참일 경우 이 요소의 내용을 사용합니다.
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<unless a="true"> </unless>' | escape_once}}</code>
          </span>
        </td>
        <td>
          만약 a가 거짓일 경우 이 요소의 내용을 사용합니다.
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<unless a="false" b="false"> </unless>' | escape_once}}</code>
          </span>
        </td>
        <td>
          만약 a혹은 b가 거짓이 아니라면 이 요소의 내용을 사용합니다.
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>조건들</h5>
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
          <code>ranked=""</code>
        </td>
        <td>
          맵이 경쟁 모드가 활성화된 서버에서 실행되고 있습니다.
        </td>
      </tr>
      <tr>
        <td>
          <code>halloween=""</code>
        </td>
        <td>
          할로윈 - 10월 1일 자정부터 11월 1일 자정까지
        </td>
      </tr>
      <tr>
        <td>
          <code>christmas=""</code>
        </td>
        <td>
          크리스마스 - 12월 1일 자정부터 12월 26일 자정까지
        </td>
      </tr>
      <tr>
        <td>
          <code>april-fools=""</code>
        </td>
        <td>
          만우절 - 4월 1일 자정부터 4월 2일 자정까지
        </td>
      </tr>
    </tbody>
  </table>
</div>

예시

    <!-- 이 섹션은 경쟁 모드 서버에서만 분석됩니다. -->
    <if ranked="true">
        <time>30m</time>
        <broadcasts>
            <tip after="1m">You guys are pros, keep up the good teamwork!</tip>
        </broadcasts>
    </if>

    <!-- 조건문이 적용된 키트 인벤토리 -->
    <kits>
        <kit id="red-inventory">
            <if ranked="false">
                <item slot="0" material="iron sword"/>
            </if>
            <if ranked="true">
                <item slot="0" material="diamond sword"/>
            </if>
        </kit>
    </kits>

<br/>

#### 지형 조건문
만약 개별 맵 유형이 다른 물리적 월드 파일을 가지고 있는 경우에도 동일한 폴더에 여전히 깔끔하게 정리할 수 있습니다.
[지형](/modules/world#terrain) 태그를 사용하여 맵의 지형 데이터를 포함하는 하위 폴더를 지정할 수 있습니다.
이는 별도의 조건에서 정의할 수 있는 영역과 다른 영역 등이 필요합니다.

    <if ranked="true">
        <terrain world="ranked"/>
        <time result="objectives">30m</time>
    </if>
    <unless ranked="true">
        <terrain world="normal"/>
        <time result="objectives">45m</time>
        <respawn delay="5s" auto="true"/>
    </unless>

<br/>

#### 하지 말아야 하는 것들

조건문을 사용할 때 피해야 할 몇가지 함정이 있습니다.
조건의 바깥 쪽과 안쪽에 있는 요소를 정의하는 것은 바람직하지 않으며, 대신 그 요소는 자신의 조건문 내에서 정의되어야 합니다.
예를 들어 ID가 있는 두 요소는 두 위치에서 동시에 정의된 경우 오류가 발생합니다.
하지만 일부 요소는 그렇지 않으며 대신 해당 요소의 첫번째 또는 마지막으로 정의된 인스턴스가 사용됩니다.

    <!-- 잘못된 예: id 'zombies'가 두번 사용되었기 때문에 오류가 발생합니다. -->
    <teams>
        <team id="zombies" color="red" max="30"/>
        <if ranked="true">
            <team id="zombies" color="dark red" max="10"/>
        </if>
    </teams>

    <!-- 올바른 예 -->
    <teams>
        <if ranked="false">
            <team id="zombies" color="red" max="30"/>
        </if>
        <if ranked="true">
            <team id="zombies" color="dark red" max="10"/>
        </if>
    </teams>
