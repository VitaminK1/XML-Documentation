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
        <th colspan='2'>Sub-Elements</th>
        <th>Value/Children</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<tip> </tip>' | escape_once}}</code>
          </span>
        </td>
        <td>
          This will display a [Tip] message
        </td>
        <td>
          <span class='label label-primary'>Formatted Text</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<alert> </alert>' | escape_once}}</code>
          </span>
        </td>
        <td>
          This will display an [Alert] message
        </td>
        <td>
          <span class='label label-primary'>Formatted Text</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>Message Tag Attributes</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Attribute</th>
        <th>Description</th>
        <th>Value</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>after</code>
        </td>
        <td>
          <span class='label label-danger'>Required</span>
          Duration to wait after the match starts to show the message.
        </td>
        <td>
          <a href='/reference/time_periods'>Time Period</a>
        </td>
      </tr>
      <tr>
        <td>
          <code>every</code>
        </td>
        <td>
          After the message is shown repeat it with this duration between messages.
        </td>
        <td>
          <a href='/reference/time_periods'>Time Period</a>
        </td>
      </tr>
      <tr>
        <td>
          <code>count</code>
        </td>
        <td>
          Amount of times the message is repeated.<br/>
          <i>Infinite repetition can be specified by using <code>oo</code> as the duration.</i>
        </td>
        <td>
          <span class='label label-primary'>Number</span>
        </td>
      </tr>
      <tr>
        <td>
          <code>filter</code>
        </td>
        <td>
          <span class='label label-default' title='Can be either this attribute or a sub-element.'>Property</span>
          Filter if the broadcast message is sent after the duration has passed, or if it's skipped.
        </td>
        <td>
          <a href='/modules/filters'>Filter</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>Message Tag Sub-elements</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Element</th>
        <th>Description</th>
        <th>Value</th>
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
          <span class='label label-default' title='Can be this sub-element or an attribute.'>Property</span>
          Filter if the broadcast message is sent after the duration has passed, or if it's skipped.
        </td>
        <td>
          <a href='/modules/filters'>Filters</a>
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
