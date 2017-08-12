---
layout: page

category: "모듈"
title:  "월드 보더"

---

월드 보더 모듈은 기본 마인크래프트 월드 보더를 사용하며 크기, 위치 및 동작을 직접 설정할 수 있습니다. 한번에 하나의 월드 보더 정의만 활성화 될 수 있습니다.

여러 개의 월드 보더에 대한 속성은 `<world-borders>`루트에 지정하여 모든 보더에 적용할 수 있습니다.

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
          정의된 모든 월드 보더가 포함된 노드입니다.
        </td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<world-border>' | escape_once}}</code>
          </span>
        </td>
        <td>
          단일 월드 보더입니다.
        </td>
        <td>
          <span class='label label-default'>월드 보더 하위 요소</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>월드 보더 속성</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 150px;'>속성</th>
        <th>설명</th>
        <th>값</th>
        <th>기본값</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>center</code>
        </td>
        <td>
          <span class='label label-danger'>필수</span>
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
          <span class='label label-danger'>필수</span>
          월드 보더의 지름, 월드 보더는 항상 정사각형입니다.
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>when</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          이 월드 보더가 적용될 때 필터링합니다.
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
          이 월드 보더가 적용되는 데 걸리는 시간입니다.
          <br/>
          <i><code>when</code> 속성과 호환되지 않습니다.</i>
        </td>
        <td>
          <a href='/reference/time_periods'>시간 단위</a>
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
          <a href='/reference/time_periods'>시간 단위</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>damage</code>
        </td>
        <td>
          월드 보더 밖에 있는 플레이어들에게 가할 초당 피해량을 나타냅니다.
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
        <td>플레이어에게 데미지가 들어가기 시작하는 경계선 까지의 거리를 나타냅니다.</td>
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
        <td>이 월드 보더보다 가까운 곳에 빨간색 경고를 보여줍니다.</td>
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
        <td>설정한 시간 동안 월드 보더가 움직이고 플레이어에게 빨간색 경고를 보여줍니다.</td>
        <td>
          <a href='/reference/time_periods'>시간 단위</a>
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
        <th>값/하위</th>
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
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          이 월드 보더가 적용될 때 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>

예시

    <world-borders center="6.5, -36.5">
        <!-- 일반적인 시간 기반 축소 월드 보더. 경기가 시작되면 200미터 부근에서 시작합니다. -->
        <!-- 5분이 지난 후 월드 보더는 15분간 폭이 20미터가 될 때 까지 줄어들기 시작합니다. -->
        <world-border size="200"/>
        <world-border size="20" after="5m" duration="10m"/>
    </world-borders>

    <!-- 월드 보더는 필터로 제어할 수 있으며 (곧 동적으로 업데이트 됨) 이것은 대략 어느 팀이 거점을 통제하는 지에 따라 월드 보더를 이동하는 방법입니다. -->
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
