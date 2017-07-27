---
layout: page

category: "Modules"
title:  "월드 보더"

---

월드 보더는 기본 마인크래프트 보더를 사용하고 크기, 위치, 행동을 조정할 수 있게 해 줍니다. 한번에 하나의 월드 보더 정의만 활성화할 수 있습니다.

여러 월드 보더에 대한 속성은 `<world-borders>` 요소 루트에 지정하여 모든 보더에 적용할 수 있습니다.

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
            <code>{{'<world-borders> </world-borders>' | escape_once}}</code>
          </span>
        </td>
        <td>
          설정된 월드 보더가 들어있는 노드입니다.
       </td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/Children</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<world-border>' | escape_once}}</code>
          </span>
        </td>
        <td>
          하나의 월드 보더입니다.
        </td>
        <td>
          <span class='label label-default'>월드 보더 하위 요소</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>월드 보더 성질</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 150px;'>성질</th>
        <th>설명</th>
        <th>값</th>
        <th>기존 설정</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>center</code>
        </td>
        <td>
          <span class='label label-danger'>필요함</span>
          월드 보더의 중심입니다.
        </td>
        <td>
          <span class='label label-primary'>X,Z</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>size</code>
        </td>
        <td>
          <span class='label label-danger'>필요함</span>
          월드 보더, 보더의 지름은 항상 직각입니다.
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>언제</code>
        </td>
        <td>
          월드 보더가 효과가 있을때 필터링됩니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>after</code>
        </td>
        <td>
           보더가 효과를 가질 때의 시간입니다.
          <br/>
          <i><code>when</code> 설정과 호환되지 않습니다.</i>
        </td>
        <td>
          <a href='/reference/time_periods'>기간</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>duration</code>
        </td>
        <td>
          이전 상태에서 이 상태로 전환하는 데 걸리는 시간입니다.
        </td>
        <td>
          <a href='/reference/time_periods'>기간</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>damage</code>
        </td>
        <td>
          플레이어가 보더 밖에 있을 때의 거리에 따라 가하는 데미지를 설정합니다.
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td>
          0.2
        </td>
      </tr>
      <tr>
        <td>
          <code>buffer</code>
        </td>
        <td>플레이어가 데미지를 입을 보더에서 끝까지의 거리입니다.</td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td>
          5
        </td>
      </tr>
      <tr>
        <td>
          <code>warning-distance</code>
        </td>
        <td>플레이어가 보더와 가까울 때 빨간 효과를 주는 거리입니다.</td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td>
          5
        </td>
      </tr>
      <tr>
        <td>
          <code>warning-time</code>
        </td>
        <td>보더가 움직여서 플레이어에게 도달할 때 빨간 효과를 주는 시간입니다.</td>
        <td>
          <a href='/reference/time_periods'>기간</a>
        </td>
        <td>
          15s
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>월드 보더 하위 요소</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>요소</th>
        <th>설명</th>
        <th>값/Children</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<when>' | escape_once}}</code>
          </span>
        </td>
        <td>
          월드 보더가 효과가 있을 때 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>

Examples

    <world-borders center="6.5, -36.5">
        <!-- Typical time-based shrinking border. Starts at 200 meters when the match loads. -->
        <!-- After 5 minutes, it starts shrinking, until it is 20 meters wide at 15 minutes. -->
        <world-border size="200"/>
        <world-border size="20" after="5m" duration="10m"/>
    </world-borders>

    <!-- Borders can be controlled with filters (and will update dynamically). This is -->
    <!-- roughly how you would move a deadly border depending on which team controls a hill -->
    <world-borders size="50" damage="20">
        <world-border center="30, 0">
            <when>
                <objective team="red-team">control-point</objective>
            </when>
        </world-border>
        <world-border center="-30, 0">
            <when>
                <objective team="blue-team">control-point</objective>
            </when>
        </world-border>
    </world-borders>
