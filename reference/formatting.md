---
layout: page

category: "참고 자료"
title:  "텍스트 포맷"

---

텍스트 포맷 코드는 화려한 색 문자를 만들기 위해 사용되는데, 그것들을 사용하기 위해서는 <code>`</code>접두사가 필요합니다. 만약 <code>`o</code> (기울임꼴) 과 같은 포맷 코드를 사용한 후에는 재설정이 필요합니다, 그렇지않으면 텍스트의 끝부분까지 계속 이어지게 됩니다.

<div class="alert alert-info alert-small">일부 오래된 맵들은 화려한 색 문자를 만들기 위해 더이상 사용되지 않는 § 기호가 사용된 경우가 있습니다. 이 기호는 더이상 사용되선 안됩니다.</div>

예시

    <item name="`i얼음 `r물" material="snowball"/>

    <line>이것은 `9Blue Team`r'의 승리 모뉴먼트중 일부입니다</line>

    <item name="`1Blue `4Red `rNone" material="book"/>

<br/>

##### 채팅 색상 {#chatColors}
![Minecraft Colors .png](/img/colors.png)

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='width: 40px;'>ID</th>
        <th>색 이름</th>
        <th style='width: 40px;'>ID</th>
        <th>색 이름</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>0</code>
        </td>
        <td>검은색</td>
        <td>
          <code>8</code>
        </td>
        <td>진한 회색</td>
      </tr>
      <tr>
        <td>
          <code>1</code>
        </td>
        <td>진한 파란색</td>
        <td>
          <code>9</code>
        </td>
        <td>파란색</td>
      </tr>
      <tr>
        <td>
          <code>2</code>
        </td>
        <td>진한 초록색</td>
        <td>
          <code>a</code>
        </td>
        <td>초록색</td>
      </tr>
      <tr>
        <td>
          <code>3</code>
        </td>
        <td>진한 하늘색</td>
        <td>
          <code>b</code>
        </td>
        <td>하늘색</td>
      </tr>
      <tr>
        <td>
          <code>4</code>
        </td>
        <td>진한 빨간색</td>
        <td>
          <code>c</code>
        </td>
        <td>빨간색</td>
      </tr>
      <tr>
        <td>
          <code>5</code>
        </td>
        <td>진한 보라색</td>
        <td>
          <code>d</code>
        </td>
        <td>밝은 보라색</td>
      </tr>
      <tr>
        <td>
          <code>6</code>
        </td>
        <td>황금색</td>
        <td>
          <code>e</code>
        </td>
        <td>노란색</td>
      </tr>
      <tr>
        <td>
          <code>7</code>
        </td>
        <td>회색</td>
        <td>
          <code>f</code>
        </td>
        <td>흰색</td>
      </tr>
    </tbody>
  </table>
</div>
<h5>텍스트</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='width: 40px;'>ID</th>
        <th>기능</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>k</code>
        </td>
        <td>랜덤</td>
      </tr>
      <tr>
        <td>
          <code>l</code>
        </td>
        <td>볼드체</td>
      </tr>
      <tr>
        <td>
          <code>m</code>
        </td>
        <td>취소선</td>
      </tr>
      <tr>
        <td>
          <code>n</code>
        </td>
        <td>밑줄</td>
      </tr>
      <tr>
        <td>
          <code>o</code>
        </td>
        <td>기울임꼴</td>
      </tr>
      <tr>
        <td>
          <code>r</code>
        </td>
        <td>초기화</td>
      </tr>
    </tbody>
  </table>
</div>

랜덤 포맷은 모든 문자를 섞어 나타냅니다

`참고:` 초기화 포맷은 모든 색과 텍스트 스타일을 초기화합니다

모든 텍스트가 기울임꼴이면서 한 단어를 빨간색으로 표시하려면 다음과 같아야합니다

    <!-- 모든 것은 기울임꼴이고 "italic"이라는 단어 역시 빨간색이다 -->
    <line>`o이것은 `r`o빨간색`c단어로 된 기울임꼴 `r`o텍스트이다</line>

[bukkit docs - Chat Color](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/ChatColor.html)에서 복사되었습니다
