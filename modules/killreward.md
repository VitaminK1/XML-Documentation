---
layout: page

category: "모듈"
title:  "처치 보상"

---

The `<kill-rewards>` module allows players to get items or a kit when they kill a player.
A kill reward can contain either individual items, kits or references to kits.
The reward can optionally filter which players are eligible to receive the reward, or when/where the reward is active.

This module can, for example, be used to give upgrades to players by giving them gold ingots.
Then once they have collected enough ingots they can craft armor, etc.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Kill Rewards Element</th>
        <th>Description</th>
        <th>Value/Children</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<kill-rewards> </kill-rewards>' | escape_once}}</code>
          </span>
        </td>
        <td>Node containing all kill reward definitions.</td>
        <td>
          <span class='label label-default'>Kill Reward elements</span>
        </td>
      </tr>
      <tr>
        <th colspan='3'>Kill Rewards Sub-elements</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<kill-reward> </kill-reward>' | escape_once}}</code>
          </span>
        </td>
        <td>
          A single kill reward.
        </td>
        <td>
          <span class='label label-default'>Kill Reward Sub-elements</span>
        </td>
      </tr>
      <tr>
        <th colspan='3'>Kill Reward Attributes</th>
      </tr>
      <tr>
        <td>
          <code>filter</code>
        </td>
        <td>
          <span class='label label-default' data-toggle='tooltip' title='이는 속성 또는 하위요소일 수 있습니다.'>속성</span>
          Filter who can claim this reward and when.
        </td>
        <td>
          <a href='/modules/filters'>Filter</a>
        </td>
      </tr>
      <tr>
        <td>
          <code>kit</code>
        </td>
        <td>
          <span class='label label-default' data-toggle='tooltip' title='이는 속성 또는 하위요소일 수 있습니다.'>속성</span>
          The kit to give players as the kill reward.
        </td>
        <td>
          <a href='/modules/kits'>Kit ID</a>
        </td>
      </tr>
      <tr>
        <th colspan='3'>Kill Reward Sub-elements</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<item>' | escape_once}}</code>
          </span>
        </td>
        <td>
          Individual items given as a kill reward.
        </td>
        <td>
          <a href='/modules/items'>Item</a>
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
          Filter who can claim this reward and when.
        </td>
        <td>
          <a href='/modules/filters'>Filters</a>
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
          The kit to give as the reward.
        </td>
        <td>
          <a href='/modules/kits'>Kits</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<br/>
Examples

    <kill-rewards>
        <!-- Give two emeralds for all kills -->
        <kill-reward>
            <item amount="2" material="emerald"/>
        </kill-reward>

        <!-- Give a cactus to players on the red team for their third kill -->
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

Kill rewards with kits

    <kill-rewards>
        <kill-reward>
            <kit>
                <item slot="0" material="iron sword"/>
                <helmet material="iron helmet"/>
                <potion amplifier="2">speed</potion>
            </kit>
        </kill-reward>

        <!-- Give the "reward-kit" to the player for every 8th kill -->
        <kill-reward>
            <filter>
                <kill-streak count="8" repeat="true"/>
            </filter>
            <kit id="reward-kit"/>
        </kill-reward>
    </kill-rewards>
