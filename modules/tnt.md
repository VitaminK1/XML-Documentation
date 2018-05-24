---
layout: page

category: "모듈"
title:  "TNT"

---

이 모듈은 당신이 TNT 폭발과 설치 행위에 대한 것을 수정할 수 있게 해줍니다. 예로 들어서, blockdamage 요소로 지형이 파괴되는 것을 쉽게 막을 수 있습니다. If it is set to `거짓` the yield element will have no effect since there won't be any block drops. TNT로 인한 피해는 [데미지 비활성화 모듈](/modules/disabledamage#block_explosion)로 더 자세히 제한할 수 있습니다.

기본값으로 설정되었을 때는, TNT가 넣어져 있는 디스펜서들은 폭발했을때 디스펜서 내부의 TNT도 점화하도록 할 것입니다. 이러한 특성(behavior)은 `<dispenser-tnt-limit>` 와 `<dispenser-tnt-multiplier>` 요소들을 사용하여 커스터마이징 할 수 있고, 그 두 요소 중 하나라도 0을 값으로 한다면 그 특성을 비활성화 할 것입니다.

만약 라이센싱(licensing)이 참으로 설정되면, 오직 TNT 자격증을 가진 플레이어들만이 TNT를 사용할 수 있습니다. 이 자격증은 자신의 팀원을 너무 많이 죽였을 경우 다시 취소될 수 있습니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>요소</th>
        <th>설명</th>
        <th></th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<tnt> </tnt>' | escape_once}}</code>
          </span>
        </td>
        <td colspan='3'>사용자 정의 TNT 설정에 관한 내용이 담긴 노드입니다.</td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값</th>
        <th>기본값</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<instantignite>' | escape_once}}</code>
          </span>
        </td>
        <td>TNT를 설치 했을 때 즉시 점화합니다.</td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>거짓</td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<blockdamage>' | escape_once}}</code>
          </span>
        </td>
        <td>TNT가 지형을 파괴할 수 있는지를 규정합니다.</td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>참</td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<yield>' | escape_once}}</code>
          </span>
        </td>
        <td>
          퍼센트 단위로 폭발에 의해 드랍되는 아이템의 수량을 조정합니다.<br/>
          <i><code>blockdamage</code>가 거짓으로 설정되면 유효하지 않습니다.</i>
        </td>
        <td>
          <span class='label label-primary'>0 - 1.0</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<power>' | escape_once}}</code>
          </span>
        </td>
        <td>
          폭발의 범위를 조정합니다.
        </td>
        <td>
          <span class='label label-primary'>0 - 20.0</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<fuse>' | escape_once}}</code>
          </span>
        </td>
        <td>
          TNT가 점화된 후 폭발하기 까지 걸리는 시간입니다.
        </td>
        <td>
          <a href='/reference/time_periods'>시간의 단위</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<dispenser-tnt-limit>' | escape_once}}</code>
          </span>
        </td>
        <td>
          디스펜서가 폭발할때 점화하는 내부 TNT의 최대 갯수입니다.
        </td>
        <td>
          <span class='label label-primary'>0 - 64</span>
        </td>
        <td>16</td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<dispenser-tnt-multiplier>' | escape_once}}</code>
          </span>
        </td>
        <td>
          디스펜서가 폭발할때 점화하는 내부 TNT의 갯수에 곱해지는 배율입니다.
        </td>
        <td>
          <span class='label label-primary'>0 - 2.0</span>
        </td>
        <td>0.25</td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<licensing>' | escape_once}}</code>
          </span>
        </td>
        <td>
          TNT 자격증을 가진 플레이어들만 TNT를 사용하게 합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>참</td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<friendly-defuse>' | escape_once}}</code>
          </span>
        </td>
        <td>
          플레이어들이 같은 팀원에 의해 설치된 TNT를 해체할 수 있게 합니다.
        </td>
        <td>
          <span class='label label-primary'>참/거짓</span>
        </td>
        <td>참</td>
      </tr>
    </tbody>
  </table>
</div>

예시)

    <tnt>
        <instantignite>on</instantignite>
        <fuse>2s</fuse>
    </tnt>

    <tnt>
        <dispenser-tnt-limit>8</dispenser-tnt-limit>
        <dispenser-tnt-multiplier>1</dispenser-tnt-multiplier>
    </tnt>
