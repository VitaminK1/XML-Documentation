---
layout: page

category: "모듈"
title:  "점수"

---

점수 모듈은 경기에 점수 제한을 두고 매번 죽거나 죽일 때마다 점수에 추가되는 포인트의 수를 수정하는 데 사용될 수 있습니다. 또한 플레이어나 팀에게 점수를 부여할 때 일정 점수를 주는 스코어 박스를 만드는 데에도 사용할 수 있습니다.
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>점수 요소</th>
        <th>설명</th>
        <th></th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<score> </score>' | escape_once}}</code>
          </span>
        </td>
        <td colspan='3'>점수 설정 및 스코어 박스가 포함 된 노드입니다.</td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위</th>
        <th>기본값</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<limit>' | escape_once}}</code>
          </span>
        </td>
        <td>
          경기가 끝나기 전에 도달할 수 있는 최대 점수를 설정합니다.
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td>
          제한 없음
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<kills>' | escape_once}}</code>
          </span>
        </td>
        <td>
          적 팀 플레이어를 죽인 후 주어지는 <strong>점수</strong>를 설정합니다.
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td>
          0
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<deaths>' | escape_once}}</code>
          </span>
        </td>
        <td>
          팀원이 <strong>실수로</strong> 사망했을 때 팀에게서 <strong>가져갈</strong> 점수를 설정합니다.
        </td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td>
          0
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<box>' | escape_once}}</code>
          </span>
        </td>
        <td>
          단일 스코어 박스 입니다.
        </td>
        <td>
          <a href='#score_box'>스코어 박스</a>
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>

예시

    <score>
        <!-- 먼저 100점에 도달하는 팀이 경기를 승리합니다. -->
        <limit>100</limit>

        <kills>3</kills> <!-- 상대를 제거할 때마다 3점을 줍니다. -->
        <deaths>2</deaths> <!-- 실수로 죽을 때마다 2점을 차감합니다. -->
    </score>


<br/>

#### 스코어 박스 {#score_box}
스코어 박스는 스코어 박스 지역에서 교환할 수 있는 아이템을 가져오거나 스코어 박스에 들어가면 점수를 부여합니다. 다중 득점을 방지하기 위해 [포탈](/modules/portals)을 설정하여 스코어 박스 부근에서 플레이어를 제거해야 합니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>스코어 박스 요소</th>
        <th>설명</th>
        <th>값/하위</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<box>' | escape_once}}</code>
          </span>
        </td>
        <td>
          단일 스코어 박스 입니다.
        </td>
        <td>
          <span class='label label-default'>스코어 박스 하위 요소</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>스코어 박스 속성</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>속성</th>
        <th>설명</th>
        <th>종류</th>
        <th>기본값</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>points</code>
        </td>
        <td>스코어 박스에 들어감으로써 얻는 점수를 나타냅니다.</td>
        <td>
          <span class='label label-primary'>숫자</span>
        </td>
        <td>0</td>
      </tr>
      <tr>
        <td>
          <code>silent</code>
        </td>
        <td>이 스코어 박스에서 점수를 얻었을 때 플레이어들에게 알리지 않습니다.</td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      <tr>
        <td>
          <code>region</code>
        </td>
        <td>
          <span class='label label-default' data-toggle='tooltip' title='이는 속성 또는 하위요소일 수 있습니다.'>속성</span>
          <span class='label label-danger'>필수</span>
          스코어 박스의 위치와 크기를 지정합니다.
        </td>
        <td>
          <a href='/modules/regions'>지역</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>filter</code>
        </td>
        <td>
          <span class='label label-default' data-toggle='tooltip' title='이는 속성 또는 하위요소일 수 있습니다.'>속성</span>
          누가 이 스코어 박스에서 득점할 수 있는지 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
        <td>
          <span class='label label-default'>필터 없음</span>
        </td>
      </tr>
      <tr>
        <td>
          <code>trigger</code>
        </td>
        <td>
          <span class='label label-default' data-toggle='tooltip' title='이는 속성 또는 하위요소일 수 있습니다.'>속성</span>
          이 스코어 박스에 적용된 동적 조건을 설정합니다.
        </td>
        <td>
          <a href='/modules/filters'>동적 필터</a>
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>
<h5>스코어 박스 하위 요소</h5>
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
            <code>{{'<redeemables>' | escape_once}}</code>
          </span>
        </td>
        <td>
          특정 아이템을 들고 스코어 박스에 들어갔을 때 주어지는 점수를 설정합니다.
        </td>
        <td>
          <code>{{'<item points="1">' | escape_once}}</code>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<region>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' data-toggle='tooltip' title='이는 하위 요소 또는 속성일 수 있습니다.'>속성</span>
          <span class='label label-danger'>필수</span>
          스코어 박스가 위치하는 지역을 나타냅니다.
        </td>
        <td>
          <a href='/modules/regions'>지역</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' data-toggle='tooltip' title='이는 하위 요소 또는 속성일 수 있습니다.'>속성</span>
          누가 이 스코어 박스에서 득점할 수 있는지 필터링합니다.
        </td>
        <td>
          <a href='/modules/regions'>필터</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<trigger>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' data-toggle='tooltip' title='이는 하위 요소 또는 속성일 수 있습니다.'>속성</span>
          이 스코어 박스에 적용된 동적 조건을 설정합니다.
        </td>
        <td>
          <a href='/modules/filters'>동적 필터</a>
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>

예시

    <score>
        <!-- 레드 팀만 스코어 박스를 이용할 수 있게하고, 2점을 부여합니다. -->
        <box points="2" filter="only-red">
            <region>
                <cylinder base="21,8,63" radius="1" height="2"/>
            </region>
        </box>
    </score>

    <score>
        <box value="8" filter="cyan" region="cyan-scorebox"/>
    </score>

<br/>

#### 교환 가능 항목
스코어 박스는 플레이어가 스코어 박스에 들어갈 때 플레이어가 들고 있는 특정 아이템과 교환하여 점수를 추가로 제공하게 할 수 있습니다. 이 항목들은 `<redeemables>` 스코어 박스 하위 요소 안에 있는 `<item>` 태그로 정의됩니다.
각 항목에는 [재료 이름](/reference/inventory#material_finder)과 선택 사항인 `points="..."` 속성이 포함되어 각 항목에 대해 부여된 점수를 지정합니다.

예시

    <score>
        <box filter="only-red" region="red-depot">
            <redeemables>
                <item points="5">diamond</item>
                <item points="3">emerald</item>
                <item points="1">gold nugget</item>
            </redeemables>
        </box>
    </score>


<br/>

### 제한 시간 {#timeLimit}
경기 시간을 제한하면 결과(result) 속성은 시간이 다 되었을 때 승리한 팀 또는 플레이어가 계산되는 방식을 결정합니다.
결과는 팀 이름이거나 특수한 값 중 하나일 수 있습니다. 승자가 없는 경우 `tie`, 또는 더 많은 목표를 달성한 팀의 경우 `objectives`로 지정할 수 있습니다. 제한 시간은 [시간 단위](/reference/time_periods) 형식으로 지정하여 분 단위로 지정할 수 있습니다.

`참고!` 이 태그는 점수 모듈 태그 안에 위치하지 **않습니다**, 대신 `<map>` 요소 안에 위치합니다.

    <time result="objectives">5m</time>


##### 시간 속성

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>속성</th>
        <th>설명</th>
        <th>유형</th>
        <th>기본값</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>result</code>
        </td>
        <td>
          승리한 팀 또는 플레이어가 계산되는 방식을 변경합니다.
          <br/>
          <code>default</code>, <code>tie</code>, <code>objectives</code> 또는 팀 ID를 사용할 수 있습니다.
        </td>
        <td>
          <span class='label label-primary'>승리 조건</span>
          |
          <span class='label label-primary'>팀 ID</span>
        </td>
        <td>default</td>
      </tr>
      <tr>
        <td>
          <code>show</code>
        </td>
        <td>채팅 및 보스바에 남은 시간을 표시합니다.</td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>참</td>
      </tr>
    </tbody>
  </table>
</div>
