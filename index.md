---
layout: default
---

<div class="jumbotron banner">
<div class="container">
<h1>아비스 네트워크 XML 문서</h1>
<p class="lead">서버에 추가될 각 맵에 필요한 XML에 대한 가이드</p>
<a href="/modules/main" class="btn btn-primary btn-lg"><i class="fa fa-play" aria-hidden="true"></i> 시작하기</a>
<a href="https://github.com/ChemistryX/XML-Documentation" class="btn btn-warning btn-lg"><i class="fa fa-github-alt" aria-hidden="true"></i> 기여하기</a>
</div>
</div>
<div class="container">
<section>
<div class="page-header">
<h1>환영합니다!</h1>
</div>
<div class="row">
<div class="col-sm-6" markdown="1">
### XML파일들은 무슨 일을 하나요?
XML파일들은 경기가 진행되는 동안 Game 플러그인이 경기를 제어하는데 필요합니다. 아비스 네트워크에 배포된 모든 맵에는 XML파일이 필요합니다. XML은 스폰 지점, 팀, 키트 들과 같은것들을 정의합니다. 각 파일은 맵마다 다르지만 구성 요소 및 모듈은 일반적으로 여러가지 맵에 사용됩니다.


### XML파일 작성하기
거의 모든 텍스트 에디터는 XML파일을 생성하고 편집할 수 있지만, XML을 위해 만들어진 에디터는 자동으로 코드를 수정해주는 기능이 있어 실수를 줄이는데 도움이 될 수 있습니다.

[Sublime Text](http://www.sublimetext.com)를 사용하여 XML파일을 생성하고 편집하는 것이 좋습니다.

XML을 파일을 보다 깔끔하고 가독성있게 유지하려면 4개의 공백을 사용하여 줄을 구성하고 사용하려는 요소나 속성만을 지정해야합니다.

### 맵 릴리즈하기
테스트를 위한 맵을 배포하기 전에 맵을 압축해야합니다 [이 가이드라인](/guides/packaging/cleaning_files)을 통해 맵을 테스트할 수 있는 시간을 단축할 수 있습니다.

</div>
<div class="col-sm-6" markdown="1">
### 이 문서를 사용하며
이 문서는 현재 사용가능한 모든 XML모듈, 속성 및 하위 요소를 나열하고, 모듈이 어떻게 작동하는지와 상호작용하는 방법을 설명하기 위한 문서입니다. 또한 이 문서는 XML이 유효하고 의도대로 작동하는지 확인하기 위해 참조할 수 있도록 설계되었습니다.

요소 또는 모듈에 대한 모든 속성 또는 하위 요소는 표에 명시되어있으며 필요한 속성 또는 하위 요소는 빨간색으로 표시됩니다. 예를 들어 `color`속성은 필수이지만 `id`는 그렇지 않습니다. 속성 또는 요소 기본 값 또한 하나의 항목이 있는 경우 나열됩니다.

##### 테이블 예시
<div class="table-responsive">
  <table class="table table-striped table-condensed">
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
          <code>id</code>
        </td>
        <td>이 요소를 참고하는 데 사용되는 고유 식별자입니다.</td>
        <td>
          <span class="label label-primary">문자열</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>color</code>
        </td>
        <td>
          <span class="label label-danger">필수</span>
          색깔의 예시입니다.
        </td>
        <td>
          <a href="/reference/colors"> 염료 색 이름</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>cow</code>
        </td>
        <td>이 예시에는 동물 소가 있습니다.</td>
        <td>
          <span class="label label-primary">참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
    </tbody>
  </table>
</div>
</div>
</div>
</section>
