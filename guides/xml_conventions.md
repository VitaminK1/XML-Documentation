---
layout: page

category: "가이드"
category_lead:  "XML 포인터"
title:  "XML 규약"

---

### 1: 들여쓰기

##### 1.1 맵 들여쓰기
모듈은 반드시 열 하나에 기초해야 합니다. 즉, `<map>`태그 아래에 있는 모든 하위 태그들은 `<map>`태그에 따라 정렬되어야 합니다.

    <?xml version="1.0"?>
    <map proto="1.4.0">
    <name>Blocks DTC</name>
    <version>1.3.4</version>
    <objective>적의 코어를 파괴하세요</objective>
    </map>

##### 1.2 하위 요소 들여쓰기
`<author>`태그와 같은 하위 요소가 있는 모듈은 상위 요소 아래에 4개의 공간을 가지고 있어야 합니다.

    <?xml version="1.0"?>
    <map proto=”1.4.0">
    <authors>
        <author uuid="060baa18-2852-40d8-afcb-e61607c04be3"/> <!-- PepsiDog -->
    </authors>
    </map>

##### 1.3 모듈 사이의 공간
모듈 사이에는 공백이 없어야 합니다. 즉, 하나의 모듈의 끝난 부분에서 바로 다음 열이 시작되어야 합니다.

    <!-- 올바르게 작성한 경우 -->
    <?xml version="1.0"?>
    <map proto="1.4.0">
    <name>Blocks DTC</name>
    <version>1.3.4</version>
    <objective>적의 코어를 파괴하세요</objective>
    </map>
^

    <!-- 올바르지않게 작성한 경우 -->
    <?xml version="1.0"?>

    <map proto="1.4.0">

    <name>Blocks DTC</name>

    <version>1.3.4</version>

    <objective>적의 코어를 파괴하세요</objective>

    </map>

##### 1.4 닫는 태그
하나의 모듈의 닫는 태그는 다음 모듈의 시작 태그 바로 위에 있어야 합니다.

##### 1.5 행 끝마치기
XML파일은 빈 줄로 끝나야 합니다. 예를 들어, 끝나는 `<map>`태그가 52행에 있으면 XML 파일의 마지막 줄을 53행이 됩니다.



<br/>

### 2: 레이아웃

##### 2.1 주요 맵 정의
맵 정의를 구성하는 6개의 모듈이 있습니다. 그것들은 모두 `map`, `name`, `version`, `objective`, `authors` 와 `contributors`순서대로 위치해야 합니다.

참고: 기여자는 선택 사항이지만 여전히 문서 상단에 위치해야 합니다.

    <?xml version="1.0"?>
    <map proto="1.4.0">
    <name>Blocks DTC</name>
    <version>1.3.4</version>
    <objective>적의 코어를 파괴하세요</objective>
    <authors>
        <author uuid="260004f0-996b-4539-ba21-df4ee6336b63"/> <!-- Elliott_ -->
    </authors>
    <contributors>
        <contributor contribution="A 기여">aHelper</contributor>
    </contributors>
    </map>

##### 2.2 프로토콜
저장소에 추가되는 모든 맵은 최신 프로토콜을 사용해야 합니다.

##### 2.3 제작자와 기여자
맵 제작자를 나타낼 때 UUID를 사용하는 경우 제작자의 IGN을 나타내는 주석이 있어야 합니다.

    <authors>
        <author uuid="260004f0-996b-4539-ba21-df4ee6336b63"/> <!-- Elliott_ -->
    </authors>

##### 2.4 필터 및 지역
필터 정의는 지역 정의보다 먼저 정의되어야 합니다.



<br/>

### 3: 이름 규약

##### 3.1 맵 이름
이름에는 특수 문자나 기호가 없어야 합니다. 여기에는 유니코드 및 악센트 문자가 포함됩니다.

##### 3.2 버전
Semantic Versioning Schema를 따릅니다. 예를 들면 다음과 같습니다: `1.2.3`

첫자리는 주요 게임 플레이 변경 사항이 생겼을 때 변경될 수 있습니다. (새 맵의 경우도 포함합니다)
두번째 자리는 게임 플레이에 영향을 미치는 변경 사항이 추가되었지만 그렇게 큰 변동이 없을 경우 변경될 수 있습니다.
세번째 자리는 버그 또는 고의가 아닌 기능을 수정하기 위해 약간의 변경을 하였을때 변경될 수 있습니다.
참고: 맵을 수정할 때 마다 이 버전을 업데이트 하십시오

##### 3.3 목표
목표에 대한 설명은 간략해야 하며 경기에서 이기려면 무엇을 해야하는지 플레이어에게 알리는 내용을 포함하고 있어야 합니다.

    <objective>상대 팀을 죽여 경기에서 승리하세요!</objective>

##### 3.4 식별 이름 지정
`id`를 요구하는 모듈은 모두 소문자로 작성되어야 하며 `-`를 사용하여 공백을 나타냅니다.

    <team id="only-blue">파란팀</team>

##### 3.5 열거 이름 지정
Bukkit에서 열거된 이름은 소문자로 구분되어야 하며 `_`로 대체된 이름은 공백으로 대체되어야 합니다. 즉, `PROTECTION_ENVIRONMENTAL`은 `protection environmental`이 되어야 합니다.

##### 3.6 재료 정의
재료 유형을 정의하는 경우 ID대신 Bukkit에서 제공하는 이름을 사용합니다. 이를 사용하면 디버깅하는것이 훨씬 쉬워집니다.

##### 3.7 필터

##### 3.7.1 팀 필터
팀 필터는 식별 이름(3.4)을 준수하고 `only-`뒤에 팀 이름을 붙여야 합니다.

`only-blue` `only-elves`
