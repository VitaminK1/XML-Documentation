---
layout: page

category: "모듈"
title:  "플레이어"

---

플레이어 모듈은 FFA, UHC 또는 헝거 게임 스타일 경기와 같이 팀이 없는 모든 게임 모드의 기초입니다.
이 모듈은 전투에 중점을 둔 경기에만 한정되지 않으며, 플레이어가 특정 아이템을 수집해야하는 전투없는 게임 모드에서도 사용할 수 있습니다.
승리 조건은 점수 및 시간 제한 모듈을 사용하여 설정됩니다.

`참고` 이 게임모드는 팀 모듈과 호환되지 않습니다.

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
            <code>{{'<players/>' | escape_once}}</code>
          </span>
        </td>
        <td>플레이어 설정을 포함하는 플레이어 노드입니다.</td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>
<h5>플레이어 속성</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 130px;'>속성</th>
        <th>설명</th>
        <th>값</th>
        <th>기본값</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>min</code>
        </td>
        <td>
          필요한 최소 플레이어의 수를 나타냅니다.
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>max</code>
        </td>
        <td>
          플레이어 제한 - 일반 플레이어는 이 크기에 도달하면 경기에 참가할 수 없습니다.
          <br/>
          <i>프리미엄 플레이어는 <code>max-overfill</code>에 도달할 때 까지 이 제한을 초과할 수 있습니다.</i>
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>max-overfill</code>
        </td>
        <td>
          플레이어 overfill -- 프리미엄 플레이어는 이 크기에 도달하면 경기에 참가할 수 없습니다.
          <br/>
          <i>앞에서 정의한 <code>max</code>값보다 커야 합니다.</i>
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>show-name-tags</code>
        </td>
        <td>
          플레이어의 이름 태그를 볼 수 있는 사용자를 지정합니다.
          <br/>
          사용 가능한 값:
          <code>true</code>, <code>false</code>, <code>allies</code> 혹은 <code>enemies</code>
        </td>
        <td>
          <span class='label label-primary'>열거형</span>
        </td>
        <td>참</td>
      </tr>
      <tr>
        <td>
          <code>colors</code>
        </td>
        <td>
          자동으로 각 플레이어에게 고유한 색을 지정하고 최대 10명까지 적용한 다음 다시 반복합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
    </tbody>
  </table>
</div>

예시

    <players max="16" max-overfill="20"/>
    <time>8m</time>

    <score>
       <kills>1</kills>
       <deaths>1</deaths>
    </score>
