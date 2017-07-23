---
layout: page

category: "가이드"
category_lead:  "배포를 위한 맵 패키징"
title:  "월드 폴더 정리하기"

---

Minecraft는 월드를 생성할 때 당신의 월드 폴더에 많은 파일들을 생성할 것입니다. 이러한 파일의 대부분은 필요하지 않으며 삭제하면 파일의 크기를 줄일 수 있습니다.

다음은 파일이 필요한지 여부와 파일이 필요한지 여부와는 상관없이 생성할 수 있는 모든 파일을 표시하는 테이블입니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 230px;'>파일 이름</th>
        <th>필요합니까?</th>
        <th>설명</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>level.dat</code>
        </td>
        <td>
          <span class='label label-success'>필요합니다</span>
        </td>
        <td>이름 및 생성 유형과 같은 전체적인 정보를 저장합니다</td>
      </tr>
      <tr>
        <td>
          <code>region/</code>
        </td>
        <td>
          <span class='label label-success'>필요합니다</span>
        </td>
        <td>해당 월드의 모든 지역파일이 포함되어 있습니다</td>
      </tr>
      <tr>
        <td>
          <code>data/map_[#].dat</code>
        </td>
        <td>
          <span class='label label-warning'>경우에 따라 다릅니다</span>
        </td>
        <td>커스텀 아이템을 사용하지 않는 경우에는 필요하지 않습니다</td>
      </tr>
      <tr>
        <td>
          <code>level.dat_mcr</code>
        </td>
        <td>
          <span class='label label-danger'>필요하지 않습니다</span>
        </td>
        <td>월드가 MCRegion에서 Anvil로 변환되기 전까지 level.dat의 백업파일</td>
      </tr>
      <tr>
        <td>
          <code>level.dat_old</code>
        </td>
        <td>
          <span class='label label-danger'>필요하지 않습니다</span>
        </td>
        <td>level.dat의 백업파일</td>
      </tr>
      <tr>
        <td>
          <code>session.lock</code>
        </td>
        <td>
          <span class='label label-danger'>필요하지 않습니다</span>
        </td>
        <td>월드가 마지막으로 액세스된 시간을 저장합니다</td>
      </tr>
      <tr>
        <td>
          <code>playerdata/</code>
          or
          <code>players/</code>
        </td>
        <td>
          <span class='label label-danger'>필요하지 않습니다</span>
        </td>
        <td>각 플레이어의 개별 정보를 저장합니다</td>
      </tr>
      <tr>
        <td>
          <code>data/villages.dat</code>
        </td>
        <td>
          <span class='label label-danger'>필요하지 않습니다</span>
        </td>
        <td>월드의 마을에 대한 정보를 저장합니다</td>
      </tr>
      <tr>
        <td>
          <code>DIM-1/ & DIM1/</code>
        </td>
        <td>
          <span class='label label-danger'>필요하지 않습니다</span>
        </td>
        <td>네더및 엔더월드에 대한 모든 파일이 포함되어있습니다</td>
      </tr>
      <tr>
        <td>
          <code>stats/</code>
        </td>
        <td>
          <span class='label label-danger'>필요하지 않습니다</span>
        </td>
        <td>업적 및 다른 스탯들을 포함하고 있습니다</td>
      </tr>
      <tr>
        <td>
          <code>##MCEDIT.TEMP##/</code>
        </td>
        <td>
          <span class='label label-danger'>필요하지 않습니다</span>
        </td>
        <td>MCEdit에 의해서 생성된 파일입니다</td>
      </tr>
      <tr>
        <td>
          <code>forcedchunks.dat</code>
        </td>
        <td>
          <span class='label label-danger'>필요하지 않습니다</span>
        </td>
        <td>강제로 생성된 청크입니다</td>
      </tr>
      <tr>
        <td>
          <code>customnpcs</code>
        </td>
        <td>
          <span class='label label-danger'>필요하지 않습니다</span>
        </td>
        <td>MCEdit이나 NBTEdit에 의해서 생성된 파일입니다</td>
      </tr>
      <tr>
        <td>
          <code>NEI</code>
        </td>
        <td>
          <span class='label label-danger'>필요하지 않습니다</span>
        </td>
        <td>Not Enough Items에 의해서 생성된 파일입니다</td>
      </tr>
      <tr>
        <td>
          <code>spc</code>
        </td>
        <td>
          <span class='label label-danger'>필요하지 않습니다</span>
        </td>
        <td>Single Player Commands에 의해서 생성된 파일입니다</td>
      </tr>
    </tbody>
  </table>
</div>
