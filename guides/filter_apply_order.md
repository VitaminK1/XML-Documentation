---
layout: page

category: "가이드"
category_lead:  "XML 포인터"
title:  "필터 적용하기"

---

프로토콜 버전이 `1.3.3`이상이면, 지역에 [적용](/modules/regions#applying)되는 필터가 순서의 영향을 받습니다.
여기 예시가 있습니다.

먼저 TNT를 **제외**하고 모든 것들을 **거부**하는 가장 기본적인 필터를 만들어 봅시다.

    <filter name="only-tnt">
        <block>tnt</block>
    </filter>

이제 이 필터를 `Region A`에 적용하고 모든 블럭을 거부하는 필터를 `Region B`에 적용하겠습니다.

    <apply block="only-tnt" region="region-a"/>

    <apply block="never" region="region-b"/>

그러나 약간의 문제가 발생했어요, 만약 `Region B`가 `Region A`안에 있다면 어떻게 해야할까요?
그러면 어떤 필터가 다른 필터를 덮어씌워야할까요? 여기 적용 순서를 볼 수 있는곳이 있습니다.

![Apply Order .png](/img/apply_order.png)

`<apply>`를 어디에 쓰는지에 따라 무언가가 필터링 되는 결과가 바뀔 수 있습니다.
앞의 예시를 보면 `only-tnt`필터는 `never`필터보다 앞에 위치하고 있기 때문에 항상 덮어씌워집니다.
`Region B`에 대한 적용은 `Region A`와 완전히 중복되지 않으므로 Region A에 적용되지 않습니다.

만약 우리가 필터의 순서를 바꾼다면 어떻게 될까요

    <apply block="never" region="region-b"/>

    <apply block="only-tnt" region="region-a"/>

이제 `Region B`안에서는 블럭을 놓을 수 없습니다. 하지만 `Region A`밖에서는 TNT블럭만을 놓을 수 있습니다.

비록 이것이 Blitz나 TDM과 같은 맵에서는 필요하지 않더라도 `<void/>`필터를 사용하는 많은 DTM/DTC/CTW 맵에서는 아주 중요합니다.
일반적으로 `<void/>`필터는 XML파일 가장 아래(가장 낮은 우선 순위)에 두는 것이 가장 좋습니다.

맵 개발자는 이 과정을 통해 맵의 지역과 필터가 올바르게 작동하는지 확인하는데 도움을 줄 수 있습니다.
