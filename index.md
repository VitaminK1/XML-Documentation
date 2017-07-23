---
layout: default
---

<div class="container">
<div class="jumbotron">
<h1>아비스 네트워크 XML 문서</h1>
<p class="lead">서버에 추가될 각 맵에 필요한 XML에 대한 가이드</p>
</div>
<section>
<div class="page-header">
<h1>환영합니다!</h1>
</div>
<div class="row">
<div class="col-sm-6" markdown="1">
### XML파일들은 무슨 일을 하나요?
XML파일들은 매치가 진행되는 동안 Game 플러그인이 매치를 제어하는데 필요합니다. 아비스 네트워크에 배포된 모든 맵에는 XML파일이 필요합니다. XML은 스폰 지점, 팀, 키트 들과 같은것들을 정의합니다. 각 파일은 맵마다 다르지만 구성 요소 및 모듈은 일반적으로 여러가지 맵에 사용됩니다.


### XML파일 작성하기
Almost every text editor can create and edit XML files, however editors designed for XML can automatically indent and syntax your code to help spot mistakes.

We recommend that you use [Sublime Text](http://www.sublimetext.com) to create and edit XML files.

To keep your XML file clean & readable you should indent lines using 4 spaces and only specify elements or attributes you intend to use.

### 맵 릴리즈하기
Before releasing your map for testing, you must package your map following [these guidelines](/guides/packaging/cleaning_files).
This will speed up the time it takes to get your map ready for testing.

</div>
<div class="col-sm-6" markdown="1">
### Using These Docs
This documentation is intended to list all currently available XML modules, their attributes & sub-elements; and describe how the modules work and interact with the player. It is designed to be used as a reference when coding the XML files accompanying a map to ensure that the XML is valid and works as intended.

All attributes or sub-elements for a element or module are listed in a table and required attributes or sub-elements are marked in red. In the following example the `color` attribute is required but `id` is not. The attribute or elements default value is also listed if there is one.

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
        <td>Unique identifier used to reference this element.</td>
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
          This examples color.
        </td>
        <td>
          <a href="/reference/colors"> Dye Color Name</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>cow</code>
        </td>
        <td>This example has a pet cow.</td>
        <td>
          <span class="label label-primary">true/false</span>
        </td>
        <td>false</td>
      </tr>
    </tbody>
  </table>
</div>
</div>
</div>
</section>
</div>
