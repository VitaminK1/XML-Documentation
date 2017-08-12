---
layout: page

category: "모듈"
title:  "Blitz"

---

게임은 지정된 시간 동안만 실행되며 플레이어는 적 플레이어를 찾아서 제거해야 합니다. 각 플레이어는 제한된 목숨을 가지고 있으며 제한된 목숨을 전부 소진한 경우 관전자 팀으로 이동됩니다. 지정된 시간이 지나거나 다른 한 팀이 제거되면 경기가 종료됩니다. 팀이 제거되기 전에 경기 타이머가 끝나면 남은 플레이어가 가장 많은 팀이 승리합니다.

Blitz 모듈은 [Ghost Squadron](/modules/gamemode_other#gs) 게임모드와 함께 사용되며 [Rage](/modules/gamemode_other#rage) 모듈과 함께 사용될 수 있습니다.

Blitz 맵은 [global blitz XML](/includes/Blitz/blitz-global.xml) 파일을 포함해야 합니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Blitz 요소</th>
        <th>설명</th>
        <th></th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<blitz> </blitz>' | escape_once}}</code>
          </span>
        </td>
        <td colspan='3'>Blitz 게임모드 설정이 포함된 노드입니다.</td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위</th>
        <th>기본값</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<lives>' | escape_once}}</code>
          </span>
        </td>
        <td>
          각 플레이어들이 경기에서 탈락하기 전에 가진 목숨의 양입니다.
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td>1</td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<broadcastLives>' | escape_once}}</code>
          </span>
        </td>
        <td>
          플레이어에게 남은 목숨의 양을 알려줍니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>참</td>
      </tr>
    </tbody>
  </table>
</div>

예시:

    <blitz>
        <lives>1</lives>
        <broadcastLives>false</broadcastLives>
    </blitz>

    <!-- 경기가 끝나기까지 걸리는 시간 -->
    <time>10m</time>

    <include src="blitz-global.xml"/>

````
<blitz/>    <!-- 기본 Blitz 설정을 사용합니다. -->
````
