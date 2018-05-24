---
layout: page

category: "모듈"
title:  "처치 보상"

---

`<kill-rewards>` 모듈은 플레이어가 다른 플레이어를 처치할 경우 설정된 아이템 혹은 킷을 얻을 수 있게 하기 위해 사용합니다.
처치 보상은 별개의 아이템, 키트, 키트에 대한 참조를 포함할 수 있습니다.
처치 보상에서의 '보상'은 특정 플레이어들만 받을 수 있게 한다던지, 특정 장소 혹은 시간에만 받을 수 있게 한다던지를 설정할 수 있게 필터링을 할 수 있습니다.
예로 들어, 처치 보상으로 금괴를 주어서, 그 금괴들을 모아 갑옷을 제작할 수 있게 하고 싶을 때 이 모듈을 사용할 수 있습니다.
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>처치 보상 요소</th>
        <th>설명</th>
        <th>값/하위 모듈</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<kill-rewards> </kill-rewards>' | escape_once}}</code>
          </span>
        </td>
        <td>모든 처치 보상을 정의한 내용을 포함하는 노드</td>
        <td>
          <span class='label label-default'>처치 보상 요소</span>
        </td>
      </tr>
      <tr>
        <th colspan='3'>처치 보상 하위 요소</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<kill-reward> </kill-reward>' | escape_once}}</code>
          </span>
        </td>
        <td>
          단수의 처치 보상
        </td>
        <td>
          <span class='label label-default'>처치 보상 하위 요소</span>
        </td>
      </tr>
      <tr>
        <th colspan='3'>처치 보상 속성</th>
      </tr>
      <tr>
        <td>
          <code>filter</code>
        </td>
        <td>
          <span class='label label-default' data-toggle='tooltip' title='이는 속성 또는 하위요소일 수 있습니다.'>속성</span>
          누가, 언제 이 보상을 받을 수 있는지를 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
      </tr>
      <tr>
        <td>
          <code>kit</code>
        </td>
        <td>
          <span class='label label-default' data-toggle='tooltip' title='이는 속성 또는 하위요소일 수 있습니다.'>속성</span>
          처치 보상으로 플레이어에게 주는 키트입니다.
        </td>
        <td>
          <a href='/modules/kits'>키트 ID</a>
        </td>
      </tr>
      <tr>
        <th colspan='3'>처치 보상 하위 요소</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<item>' | escape_once}}</code>
          </span>
        </td>
        <td>
          처치 보상으로 주는 개별적인 아이템들입니다.
        </td>
        <td>
          <a href='/modules/items'>아이템</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' data-toggle='tooltip' title='이는 하위 요소 또는 속성일 수 있습니다.'>속성</span>
          누가, 언제 이 보상을 받을 수 있는지를 필터링합니다.
        </td>
        <td>
          <a href='/modules/filters'>필터</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<kit>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' data-toggle='tooltip' title='이는 하위 요소 또는 속성일 수 있습니다.'>속성</span>
          처치 보상으로 받는 키트입니다.
        </td>
        <td>
          <a href='/modules/kits'>Kits</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<br/>
예시)

    <kill-rewards>
        <!-- 모든 킬에 대해 2개의 에메랄드를 지급 -->
        <kill-reward>
            <item amount="2" material="emerald"/>
        </kill-reward>

        <!-- 레드팀에 있는 플레이어가 3연킬을 하였을때 선인장을 지급 -->
        <kill-reward>
            <filter>
                <all>
                    <team>red</team>
                    <kill-streak count="3"/>
                </all>
            </filter>
            <item material="cactus"/>
        </kill-reward>
    </kill-rewards>

키트로 처치 보상을 지급하기

    <kill-rewards>
        <kill-reward>
            <kit>
                <item slot="0" material="iron sword"/>
                <helmet material="iron helmet"/>
                <potion amplifier="2">speed</potion>
            </kit>
        </kill-reward>

        <!-- 플레이어가 8번째 킬을 할때마다 "reward-kit" 를 처치 보상으로 지급 -->
        <kill-reward>
            <filter>
                <kill-streak count="8" repeat="true"/>
            </filter>
            <kit id="reward-kit"/>
        </kill-reward>
    </kill-rewards>
