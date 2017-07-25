---
layout: page

category: "가이드"
category_lead:  "XML 포인터"
title:  "필터 적용하기"

---

프로토콜 버전이 `1.3.3`이상이면, 지역에 [적용](/modules/regions#applying)되는 필터가 순서의 영향을 받습니다.
여기 예시가 있습니다.

TNT를 **제외**하고 모든 것들을 **거부**하는 가장 기본적인 필터를 만들어 봅시다. 

    <filter name="only-tnt">
        <block>tnt</block>
    </filter>

Now let's apply this filter to `Region A`, and also apply a filter to `Region B` that denies all blocks.

    <apply block="only-tnt" region="region-a"/>

    <apply block="never" region="region-b"/>

However, there is one slight complication. `Region B` is inside of `Region A`.
So which filter will override the other? This is where the apply order comes in handy.

![Apply Order .png](/img/apply_order.png)

The order that you put the `<apply>`'s can change the outcome when something gets filtered.
In the previous example, the `only-tnt` filter would always override the `never` filter since it is above it.
The apply for `region B` won't get checked since it overlaps completely with `region A` and `region A` never returns abstain.

If we changed the order of the filters:

    <apply block="never" region="region-b"/>

    <apply block="only-tnt" region="region-a"/>

Now you cannot place blocks in `Region B`, but outside of it in `Region A` you can only place TNT blocks.

Although this may not be an issue for many maps such as a Blitz map or a TDM,
this is a crucial concept for many DTC/DTM/CTW maps that use the `<void/>` filter.
Usually it's best to have the `<void/>` filter at the lowest priority (at the bottom of the list).

A map developer will be able to help you through this process to ensure that your map's regions and filters are properly working.
