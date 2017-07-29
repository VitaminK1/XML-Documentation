---
layout: page

category: "모듈"
title:  "알림과 팁"

---

`broadcast` 모듈을 사용하면 특정 시점에 모든 플레이어에게 메시지를 방송할 수 있습니다.
broadcast 태그 안에 `after=""` 속성이 있는 `<alert>` 또는 `<tip>` 메시지 태그를 지정할 수 있습니다. 이 속성은 필수이며 경기가 시작된 후 방송이 표시되는 시간을 지정합니다. <br/>
broadcast의 텍스트는 [텍스트 포맷](/reference/formatting) 코드를 사용하여 형식을 지정할 수 있습니다.

<span class="label label-warning">참고</span>
이 모듈은 맵에 **고유**하고 **중요**한 정보를 표시하는 데에만 사용하야 합니다.
이것은 일반 Avis Network관련 메시지로는 사용할 수 없습니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>브로드캐스트 요소</th>
        <th>설명</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<broadcasts> </broadcasts>' | escape_once}}</code>
          </span>
        </td>
        <td>정의된 모든 브로드캐스트 메시지를 포함하고 있는 요소입니다.</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<tip> </tip>' | escape_once}}</code>
          </span>
        </td>
        <td>
          [Tip] <code>메시지</code>형태로 표시합니다.
        </td>
        <td>
          <span class='label label-primary'>텍스트 포맷</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<alert> </alert>' | escape_once}}</code>
          </span>
        </td>
        <td>
          [Alert] <code>메시지</code> 형태로 표시합니다.
        </td>
        <td>
          <span class='label label-primary'>텍스트 포맷</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>메시지 태그 속성</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>속성</th>
        <th>설명</th>
        <th>값</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>after</code>
        </td>
        <td>
          <span class='label label-danger'>필수</span>
          경기가 시작된 후 메시지가 표시되기까지의 시간입니다.
        </td>
        <td>
          <a href='/reference/time_periods'>시간 단위</a>
        </td>
      </tr>
      <tr>
        <td>
          <code>every</code>
        </td>
        <td>
          메시지가 표시된 후 메시지 간의 반복되는 시간을 설정합니다.
        </td>
        <td>
          <a href='/reference/time_periods'>시간 단위</a>
        </td>
      </tr>
      <tr>
        <td>
          <code>count</code>
        </td>
        <td>
          메시지가 반복되는 횟수입니다.<br/>
          <i>무한 반복은 <code>oo</code>를 사용하여 지정할 수 있습니다.</i>
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
      </tr>
      <tr>
        <td>
          <code>filter</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          지속 시간이 경과한 후 또는 생략된 경우 방송 메시지가 전송된 경우 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>메시지 태그 하위 요소</h5>
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
            <code>{{'<filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          지속 시간이 경과한 후 또는 생략된 경우 방송 메시지가 전송된 경우 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>

예시

    <broadcasts>
        <tip after="30s">[Tip]은 경기가 시작한 다음 30초가 지난 시점에 방송됩니다.</tip>
        <alert after="5m">[Alert]는 경기가 시작한 다음 5분이 지난 시점에 방송됩니다.</alert>
        <tip after="10m" count="3">[Tip]을 10분 20분 30분마다 반복합니다.</tip>
        <tip after="99s" count="oo">99초마다 무한으로 반복합니다.</tip>
        <tip after="20m" every="1m">경기가 시작한 다음 20분 후에 처음 표시되고 그 후 매 분마다 표시됩니다.</tip>
        <tip after="30m" every="10m" count="3">경기가 시작한 다음 30분 40분 50분 후에 팁이 표시됩니다.</tip>
    </broadcasts>
