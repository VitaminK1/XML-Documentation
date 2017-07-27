---
layout: page

category: "모듈"
title:  "코어 부수기 게임"

---

Players have to locate and break the enemy team's core, usually an obsidian sphere filled with lava. The lava has to leak down a certain distance for the core to be destroyed. Lava should not be available anywhere else on the map, otherwise a core leak could be faked. This can also be avoided by keeping the lava far away enough from the core and not giving players buckets or the ability to craft them.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Cores Element</th>
        <th>Description</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<cores> </cores>' | escape_once}}</code>
          </span>
        </td>
        <td>Node containing all the defined cores.</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>Sub-elements</th>
        <th>Value/Children</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<core> </core>' | escape_once}}</code>
          </span>
        </td>
        <td>
          A single core.
        </td>
        <td>
          <span class='label label-default'>Core Sub-elements</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>Core Attributes</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Attribute</th>
        <th>Description</th>
        <th>Value</th>
        <th>Default</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>id</code>
        </td>
        <td>Unique identifier used to reference cores from other places in the XML.</td>
        <td>
          <span class='label label-primary'>String</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>name</code>
        </td>
        <td>The core's name, used in notification messages.</td>
        <td>
          <span class='label label-primary'>String</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>required</code>
        </td>
        <td>
          Specify if this objective is required to win the match.
          <br/>
          Teams completing all of their required objectives will win regardless of score or blitz configuration.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>
          true
        </td>
      </tr>
      <tr>
        <td>
          <code>region</code>
        </td>
        <td>
          <span class='label label-default' title='Can be either this attribute or a sub-element.'>Property</span>
          <span class='label label-danger'>Required</span>
          A region containing the core.
        </td>
        <td>
          <a href='/modules/regions'>Bounded Region</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>leak</code>
        </td>
        <td>Distance below the bottom of the core <strong>region</strong> that the lava must leak.</td>
        <td>
          <span class='label label-primary'>Number</span>
        </td>
        <td>5</td>
      </tr>
      <tr>
        <td>
          <code>material</code>
        </td>
        <td>The core casing material, used to detect breaks, and for mode changes.</td>
        <td>
          <a href='/reference/inventory#material_matchers'>Single Material Pattern</a>
        </td>
        <td>obsidian</td>
      </tr>
      <tr>
        <td>
          <code>team</code>
        </td>
        <td>
          <span class='label label-danger'>Required</span>
          Team the core belongs to, i.e. its owner.
        </td>
        <td>
          <a href='/modules/teams'>Team ID</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>mode-changes</code>
        </td>
        <td>
          Specify if this core uses
          <a href='/modules/monument_modes'>monument modes</a>.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>show</code>
        </td>
        <td>
          Specify if the core should be hidden from all visible locations to the player. These locations include chat, the boss bar, and the scoreboard.
          <br/>
          <code>NOTE:</code>
          The objective will also not be logged to the Database and the player will not recieve any raindrops upon completion.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>true</td>
      </tr>
      <tr>
        <td>
          <code>proximity-metric</code>
        </td>
        <td>
          Metric used to determine proximity to the core.
          <br/>
          Accepts <code>closest player</code>, <code>closest block</code> or <code>closest kill</code>
        </td>
        <td>
          <span class='label label-primary'>Proximity Metric</span>
        </td>
        <td>
          <code>closest player</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>proximity-horizontal</code>
        </td>
        <td>
          Only calculate horizontal distance for core proximity.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
    </tbody>
  </table>
</div>
<h5>Core Sub-elements</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Element</th>
        <th>Description</th>
        <th>Value</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<region>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          <span class='label label-danger'>Required</span>
          A region containing the core.
        </td>
        <td>
          <a href='/modules/regions'>Bounded Regions</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
    <cores material="obsidian" leak="8">
        <core team="blue">
            <region><cuboid min="10,15,12" max="12,13,16"/></region>
        </core>
    </cores>

    <cores material="obsidian" leak="4">
        <core team="red" region="red-core"/>
    </cores>
