---
layout: page

category: "모듈"
title:  "몹 스폰"

---

기본적으로 Game 플러그인은 모든 몹 생성을 비활성화 합니다. 몹 모듈은 특정 몹의 생성을 허용하도록 이 동작을 사용자 정의 할 수 있습니다.
이 모듈은 특정 몹만 스폰하도록 허용하기 위해 `<spawn>`, `<mob>` 과 `<entity>` [필터](/modules/filters)를 사용합니다.
몹 스폰은 영역을 포함하여 다른 필터 유형에 대해서도 필터링할 수 있습니다.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>요소</th>
        <th>설명</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<mobs> </mobs>' | escape_once}}</code>
          </span>
        </td>
        <td colspan='3'>사용자 정의 몹 생성 필터가 포함된 노드입니다.</td>
      </tr>
      <tr>
        <th colspan='2'>속성</th>
        <th>값/하위</th>
      </tr>
      <tr>
        <td>
          <code>filter</code>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          <span class='label label-danger'>필수</span>
          언제 어디에서 몹이 생성될 수 있는지 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
      </tr>
      <tr>
        <th colspan='2'>하위 요소</th>
        <th>값/하위</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<filter> </filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='이는 속성 또는 하위 요소일 수 있습니다.'>속성</span>
          <span class='label label-danger'>필수</span>
          언제 어디에서 몹이 생성될 수 있는지 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>Mob Spawning Filter Matchers</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>요소</th>
        <th>설명</th>
        <th>값</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<spawn> </spawn>' | escape_once}}</code>
          </span>
        </td>
        <td>몹이 스폰되는 이유를 필터링합니다.</td>
        <td>
          <a href='/reference/spawn_reason'>스폰 사유</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<mob> </mob>' | escape_once}}</code>
          </span>
        </td>
        <td>필터링할 몹을 설정합니다.</td>
        <td>
          <a href='/reference/entity_types#creatures'>몹 유형</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<entity> </entity>' | escape_once}}</code>
          </span>
        </td>
        <td>필터링할 엔티티를 설정합니다.</td>
        <td>
          <a href='/reference/entity_types'>엔티티 유형</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>

Examples

    <!-- Only allow mobs to spawn from monster spawners. -->
    <mobs>
        <filter>
            <spawn>spawner</spawn>
        </filter>
    </mobs>

    <!-- Only allow cave spiders spawned with spawn eggs -->
    <mobs>
        <filter>
            <all>
                <mob>cave spider</mob>
                <spawn>spawner egg</spawn>
            </all>
        </filter>
    </mobs>
