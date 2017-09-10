---
layout: page

category: "모듈"
title:  "Include 파일"
nav_content:
  - path: "#includes"
    name: "XML Include 파일"

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
          <a href='/includes/tutorial.xml'>tutorial.xml</a>
        </td>
        <td>튜토리얼의 시작 단계와 끝 단계를 포함하고 있습니다.</td>
      </tr>
      <!--
      <tr>
        <td>
          <a href='/includes/continuity-tnt.xml'>continuity-tnt.xml</a>
        </td>
        <td>BoomBox와 같은 맵에서 사용되는 사전 설계된 TNT인벤토리를 포함하고 있습니다.</td>
      </tr>
      <tr>
        <td>
          <a href='/includes/blasternauts.xml'>blasternauts.xml</a>
        </td>
        <td>'blasternauts'라는 아케이드 게임의 기본 XML을 포함하고 있습니다.</td>
      </tr>
      -->
      <tr>
        <td>
          <a href='/includes/Blitz/blitz-global.xml'>blitz-global.xml</a>
        </td>
        <td>Blitz 맵들을 위한 자동 리스폰 기능을 포함하고 있습니다.</td>
      </tr>
      <!--
      <tr>
        <td>
          <a href='/includes/Blitz/GS/gs.xml'>gs.xml</a>
        </td>
        <td>Ghost Squadron 게임 모드를 위해 미리 만들어진 클래스를 포함하고 있습니다.</td>
      </tr>
      <tr>
        <td>
          <a href='/includes/Blitz/GS/gs-ffa.xml'>gs-ffa.xml</a>
        </td>
        <td>Ghost Squadron FFA 게임 모드를 위해 미리 만들어진 팀을 포함하고 있습니다.</td>
      </tr>
      <tr>
        <td>
          <a href='/includes/Arcade/skywars.xml'>skywars.xml</a>
        </td>
        <td>SkyWars의 기본 XML을 포함하고 있습니다.</td>
      </tr>
      <tr>
        <td>
          <a href='/includes/Arcade/block-runner.xml'>block-runner.xml</a>
        </td>
        <td>'block runner'라는 아케이드 게임의 기본 XML을 포함하고 있습니다.</td>
      </tr>
      <tr>
        <td>
          <a href='/includes/disable-boat-crafting.xml'>disable-boat-crafting.xml</a>
        </td>
        <td>모든 종류의 보트를 만들 수 없게 하는 XML을 포함하고 있습니다.</td>
      </tr>
      -->
      <tr>
        <td>
          <a href='/includes/Arcade/infection-tag.xml'>infection-tag.xml</a>
        </td>
        <td>Infection Tag의 기본 XML을 포함하고 있습니다.</td>
      </tr>
      <tr>
        <td>
          <a href='/includes/Arcade/missilewars.xml'>missilewars.xml</a>
        </td>
        <td>Missile Wars의 기본 XML을 포함하고 있습니다.</td>
      </tr>
      <tr>
        <td>
          <a href='/includes/Arcade/survival-games.xml'>survival-games.xml</a>
        </td>
        <td>Survival Games의 기본 XML을 포함하고 있습니다.</td>
      </tr>
    </tbody>
  </table>
</div>
