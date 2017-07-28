---
layout: page

category: "모듈"
title:  "맵 튜토리얼"

---

튜토리얼 모듈은 맵에 대한 튜토리얼을 만드는 데 사용됩니다. 튜토리얼은 메시지와 텔레포트 위치가 있는 단계로 나뉩니다.

튜토리얼은 플레이 경험이 없는 플레이어를 대상으로 하므로 약자 또는 약어 없이 최대한 간단하게 작성해야 합니다. 만약 약어가 사용되는 경우 설명을 추가로 작성하는 것이 좋습니다. (예: `양털 쟁탈 게임 (CTW)`)

`tutorial.xml`은 튜토리얼의 시작과 끝에서 보내질 기본 메시지를 정의합니다.

`참고` 이 파일은 **무조건** 맵 XML에 포함되어야 합니다.

    <include src="tutorial.xml"/>

<br/>
튜토리얼 단계에는 여러 줄의 메시지와 텔레포트가 포함되어 있습니다. 단계 제목은 튜토리얼 항목의 도구 설명에 표시되어야 하기 때문에 너무 길지 않아야 합니다.
메시지 요소는 여러 줄을 포함할 수 있으며, 색상 및 [텍스트 포맷 코드](/reference/formatting)를 멋진 텍스트를 만들기 위해 사용할 수 있습니다. 메시지 줄은 강제 줄바꿈을 위해 사용되며 모든 텍스트를 단일 `<line>`에 넣을 수도 있습니다. 그러나 줄바꿈이 시작되는 위치를 제어할 수는 없습니다.

텔레포트는 선택 사항입니다. 정의되지 않은 경우 메시지가 표시됩니다. 텔레포트는 [지역](/modules/regions) 혹은 [지점 제공자](/modules/regions#pointProviders)를 포함할 수 있으므로 플레이어가 스폰되는 위치를 정확하게 제어하기 위해 지점 제공자를 사용하는 것이 좋습니다. 만약 어떤 지점이 막히면 플레이어는 텔레포트하지 않습니다. 그러나 단계 메시지는 계속 표시됩니다.

단계는 XML에서 정의된 순서대로 표시됩니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>튜토리얼 요소</th>
        <th>설명</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<tutorial> </tutorial>' | escape_once}}</code>
          </span>
        </td>
        <td>정의된 튜토리얼 단계가 모두 포함된 노드입니다.</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<stage> </stage>' | escape_once}}</code>
          </span>
        </td>
        <td>
          단일 튜토리얼 단계입니다.
        </td>
        <td>
          <span class='label label-default'>단계 하위 요소</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>튜토리얼 단계 속성</h5>
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
          <code>title</code>
        </td>
        <td>
          <span class='label label-danger'>필수</span>
          이 단계의 간단한 제목입니다.
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>튜토리얼 단계 하위 요소</h5>
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
            <code>{{'<message>' | escape_once}}</code>
          </span>
        </td>
        <td>튜토리얼 메시지 줄의 컨테이너입니다.</td>
        <td>
          <code>{{'<line>' | escape_once}}</code>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<line>' | escape_once}}</code>
          </span>
        </td>
        <td>
          이 단계의 메시지 줄입니다.
          <code>{{'<message>' | escape_once}}</code>
          에 사용됩니다.
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<teleport>' | escape_once}}</code>
          </span>
        </td>
        <td>이 단계의 보기 위치입니다.</td>
        <td>
          <a href='/modules/regions'>지역</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
    <tutorial>
        <stage title="양털 쟁탈 게임">
            <message>
                <line>`r이 맵은 `a`l양털 쟁탈 게임 `r(CTW) 맵입니다</line>
                <line>목표는 상대팀의 양털을 기지로 가져오는 것입니다.</line>
            </message>
            <teleport>
                <point yaw="90" pitch="50">44,60,0</point>
            </teleport>
        </stage>
        <!-- 다음 단계 -->
    </tutorial>
