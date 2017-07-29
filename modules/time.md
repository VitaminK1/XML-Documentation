---
layout: page

category: "모듈"
title:  "시간과 차원"
nav_content:
  - path: "#time"
    name: "시간"
  - path: "#dimension"
    name: "차원"

---

### 시간 {#time}
맵이 저장된 시점에 대한 시간을 잠급니다. 예를 들어 시간을 자정으로 변경하고 저장한 다음 이 속성을 사용하면 게임 내내 시간이 변하지 않습니다. 이것은 `doDaylightCycle` [게임 규칙](/modules/gamerules)으로도 수행할 수 있습니다.

    <timelock>on</timelock>  <!-- 기본값은 off입니다. -->

<br/>

### 차원 {#dimension}
맵이 플레이되는 차원을 `nether`, `normal` 혹은 `the end`로 변경합니다. 기본값은 `normal`입니다.
만약 이것이 활성화되면 주로 하늘의 색상과 몹의 스폰에 영향을 미칩니다.

    <dimension>nether</dimension>
