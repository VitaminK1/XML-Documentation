---
layout: page

category: "모듈"
title:  "기본 맵 요소"

---

모든 맵 XML파일에는 기본이 되는 `<map>` 모듈이 포함되어야 합니다. 여기에는 맵 이름, 버전, 객관적, 저자, 기여자 및 기타 모든 지도 설정을 지정하는 모듈이 포함되어 있습니다. 목표물은 참가자들이 경기에 참여할 때 보여지는 텍스트입니다, 그래서 이것이 매우 명확하고 간결하게 작성되는것이 중요합니다.

`proto=""`속성은 XML파일이 생성한 Game버전을 저장합니다. 이 값이 실행 중인 Game의 버전보다 높으면 맵이 로드되지 않습니다. 더 낮은 경우 맵이 로드되지만 XML은 오래된 방식으로 해석될 수 있습니다. 맵 제작자들은 항상 최신 버전의 XML을 사용해야 하며, 이는 Avis Network 로테이션에 추가되는 새로운 맵에 필요할 수 있습니다.

맵 버전은 버전 관리 스키마인 `major.minor.patch`를 따라야 합니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>맵 요소</th>
        <th>설명</th>
        <th>값/자식 모듈</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<map> </map>' | escape_once}}</code>
          </span>
        </td>
        <td>
          이 경기에 사용되는 모든 모듈을 포함하는 메인 맵 노드입니다
        </td>
        <td>
          <span class='label label-default'>XML 모듈</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>맵 속성</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>속성</th>
        <th>설명</th>
        <th>값</th>
        <th>기본값</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>proto</code>
        </td>
        <td>
          <span class='label label-danger'>필요합니다</span>
          맵 XML 프로토콜 버전입니다
        </td>
        <td>
          <code>{{site.current_proto}}</code>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>game</code>
        </td>
        <td>이 경기의 게임 모드에 대한 사용자 정의 제목입니다</td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>internal</code>
        </td>
        <td>나침반을 이용해서 Y255보다 높은 곳을 이동하는것을 방지합니다</td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
    </tbody>
  </table>
</div>
<h5>맵 하위요소</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 150px;'>요소</th>
        <th>설명</th>
        <th>값/자식 모듈</th>
        <th>기본값</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<name>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-danger'>필요합니다</span>
          맵의 제목을 나타냅니다
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<version>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-danger'>필요합니다</span>
          맵의
          <a href='http://semver.org'>Semantic version</a>
          문자열
        </td>
        <td>
          <code>1.0.0</code>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<objective>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-danger'>필요합니다</span>
          경기가 시작될 때 보여지는 맵의 목표
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<authors>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-danger'>필요합니다</span>
          맵의 제작자, 적어도 한명 이상의 제작자가 필요합니다
        </td>
        <td>
          <code>{{'<author>' | escape_once}}</code>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<contributors>' | escape_once}}</code>
          </span>
        </td>
        <td>
          맵을 제작하는 데 기여를 한 사람
        </td>
        <td>
          <code>{{'<contributor>' | escape_once}}</code>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<gamemode>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <a class='left-ref-link' href='#gamemode'><i class="fa fa-chevron-down"></i></a>
          맵의 게임 모드, 만약 이 값이 지정되지 않으면 맵이 사용되는 모듈에 대해 게임모드를 설정합니다
        </td>
        <td>
          <span class='label label-primary'>게임모드 ID</span>
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>
    <?xml version="1.0"?>
    <map proto="{{site.current_proto}}">
    <name>맵 이름</name>
    <version>1.0.0</version>
    <objective>맵 목표에 대한 간략한 설명</objective>

    <!-- 맵 제작자와 기여자 -->

    <!-- 맵 모듈 (예: 목표, 지역, 스폰 지점) -->

    </map>



<br/>

#### 제작자와 기여자 {#authors_contributors}
제작자와 기여자 요소는 누가 맵을 만들고 도왔는가에 관한 정보를 제공합니다. 맵에는 다수의 제작자와 기여자가 있을 수 있습니다. 기여자 요소는 맵에 대한 기여도를 지정하는 데 사용해야 합니다.

플레이어 이름은 **절대** 그들의 기여를 표하기 위해서 사용되서는 안됩니다, 대신 UUID를 사용할 수 있습니다. UUID는 사용자 이름을 변경하더라도 플레이어를 추적하는 데 사용되는 고유한 사용자 ID입니다. [mcuuid.net](http://mcuuid.net)에서 플레이어의 UUID를 확인할 수 있습니다. 제작자나 기여자가 UUID없이 정의된 경우, 플레이어는 맵에서 맵 제작자 특권을 얻지 못할 것입니다.
<h5>제작자 또는 기여자 하위 요소</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>요소</th>
        <th>설명</th>
        <th>값/자식 모듈</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<author>' | escape_once}}</code>
          </span>
        </td>
        <td>
          맵의 주요 제작자,
          <code>{{'<authors>' | escape_once}}</code>의 하위 요소로 사용됩니다
          <br/>
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<contributor>' | escape_once}}</code>
          </span>
        </td>
        <td>
          맵의 기여자,
          <code>{{'<contributors>' | escape_once}}</code>의 하위 요소로 사용됩니다
        </td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>제작자 및 기여자 속성</h5>
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
          <code>contribution</code>
        </td>
        <td>맵에 대한 기여 내용을 담고 있습니다</td>
        <td>
          <span class='label label-primary'>String</span>
        </td>
      </tr>
      <tr>
        <td>
          <code>uuid</code>
        </td>
        <td>플레이어를 식별하는 데 사용되는 UUID입니다</td>
        <td>
          <span class='label label-primary'>문자열</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
    <!-- 주요 맵 제작자. -->
    <authors>
        <author>aPerson</author>
        <author uuid="ef4ea031-998f-4ec9-b7b6-1bdd428bcef8" contribution="요소 사용 분류 등"/> <!-- Plastix -->
        <author uuid="260004f0-996b-4539-ba21-df4ee6336b63"/> <!-- Elliott_ -->
    </authors>

    <!-- 맵을 만드는 데 기여한 사람들 -->
    <contributors>
        <!-- Minecraft계정이 없는 사람에게 기여를 표할 때 -->
        <contributor contribution="A contribution">aHelper</contributor>
        <contributor uuid="3fbec7dd-0a5f-40bf-9d11-885a54507112" contribution="약간의 도움"/> <!-- Cubist -->
    </contributors>


<br/>

#### 맵 게임모드 {#gamemode}

게임모드 요소는 맵의 게임모드를 지정하는 데 사용됩니다. 이는 주로 맵이 분류되고 표시되는 방식에 영향을 미칩니다.
만약 `<gamemode>` 태그가 지정되지 않으면 맵이 사용되는 모듈에 대해 게임모드를 설정합니다. 이 말은 지정되지 않은 한 destroyables와 깃발을 사용하는 맵은 "DTM 과 CTF"로 표시될 것입니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>요소</th>
        <th>설명</th>
        <th>값/자식 모듈</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<gamemode> </gamemode>' | escape_once}}</code>
          </span>
        </td>
        <td>
          맵의 게임모드를 나타냅니다
        </td>
        <td>
          <span class='label label-primary'>게임모드 ID</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>게임모드 ID</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>ID</th>
        <th>설명</th>
        <th>ID</th>
        <th>설명</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>tdm</code>
        </td>
        <td>팀 데스매치</td>
        <td>
          <code>ctw</code>
        </td>
        <td>양털 뺏기 게임</td>
      </tr>
      <tr>
        <td>
          <code>ctf</code>
        </td>
        <td>깃발 뺏기 게임</td>
        <td>
          <code>dtc</code>
        </td>
        <td>코어 부수기 게임</td>
      </tr>
      <tr>
        <td>
          <code>dtm</code>
        </td>
        <td>모뉴먼트 부수기 게임</td>
        <td>
          <code>ad</code>
        </td>
        <td>공격/방어</td>
      </tr>
      <tr>
        <td>
          <code>koth</code>
        </td>
        <td>거점 점령 게임</td>
        <td>
          <code>blitz</code>
        </td>
        <td>Blitz게임</td>
      </tr>
      <tr>
        <td>
          <code>rage</code>
        </td>
        <td>Rage게임</td>
        <td>
          <code>scorebox</code>
        </td>
        <td>스코어박스 게임</td>
      </tr>
      <tr>
        <td>
          <code>arcade</code>
        </td>
        <td>아케이드 게임</td>
        <td>
          <code>gs</code>
        </td>
        <td>Ghost Squadron게임</td>
      </tr>
      <tr>
        <td>
          <code>ffa</code>
        </td>
        <td>개인전 게임</td>
        <td>
          <code>mixed</code>
        </td>
        <td>여러가지 게임</td>
      </tr>
    </tbody>
  </table>
</div>

예시

    <!-- 스코어박스가 있는 FFA게임 -->
    <gamemode>ffa</gamemode>
    <gamemode>scorebox</gamemode>
