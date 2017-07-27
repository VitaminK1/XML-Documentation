---
layout: page

category: "모듈"
title:  "모뉴먼트 부수기 게임"

---

Players have to locate and destroy certain objects from the enemy team, such as an obsidian pillar, etc. Teams win after a specified percentage of the enemy teams destroyables are destroyed. Teams can have multiple destroyables and they can be made out of multiple materials.

Completion specifies how much of the material(s) inside of the monument region must be removed for it to count as destroyed. For example, if the monument is obsidian and completion is set to 100% then all the obsidian must be removed in order for the monument to count as destroyed.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Destroyables Element</th>
        <th>Description</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<destroyables> </destroyables>' | escape_once}}</code>
          </span>
        </td>
        <td>Node containing all the defined destroyables.</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>Sub-elements</th>
        <th>Value/Children</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<destroyable> </destroyable>' | escape_once}}</code>
          </span>
        </td>
        <td>
          A single destroyable.
        </td>
        <td>
          <span class='label label-default'>Destroyable Sub-elements</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>Destroyable Attributes</h5>
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
        <td>Unique identifier used to reference monuments from other places in the XML.</td>
        <td>
          <span class='label label-primary'>String</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>name</code>
        </td>
        <td>
          <span class='label label-danger'>Required</span>
          The destroyables name.
        </td>
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
          Region containing the destroyable.
        </td>
        <td>
          <a href='/modules/regions'>Bounded Region</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>materials</code>
        </td>
        <td>
          The destroyables materials, multiple materials are separated with a semicolon
          <code>;</code>
        </td>
        <td>
          <a href='/reference/inventory#material_matchers'>Material Pattern</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>owner</code>
        </td>
        <td>
          <span class='label label-danger'>Required</span>
          The destroyables owner.
        </td>
        <td>
          <a href='/modules/teams'>Team ID</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>completion</code>
        </td>
        <td>Percentage of the destroyable that needs to be destroyed for a win.</td>
        <td>
          <span class='label label-primary'>0 - 100</span>
        </td>
        <td>100%</td>
      </tr>
      <tr>
        <td>
          <code>mode-changes</code>
        </td>
        <td>
          Specify if this destroyable uses custom
          <a href='/modules/monument_modes'>monument modes</a>.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
      <tr>
        <td>
          <code>show-progress</code>
        </td>
        <td>
          Show this destroyables progress in the scoreboard.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
      <tr>
        <td>
          <code>repairable</code>
        </td>
        <td>
          Specify if the destroyable can be repaired.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>true</td>
      </tr>
      <tr>
        <td>
          <code>sparks</code>
        </td>
        <td>
          Spawn fireworks particles for destroyed blocks & play the fireworks sound to all players.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
      <tr>
        <td>
          <code>show</code>
        </td>
        <td>
          Specify if the objective should be hidden from all visible locations to the player. These locations include chat, the boss bar, and the scoreboard.
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
          Metric used to determine proximity to the destroyable.
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
          Only calculate horizontal distance for destroyable proximity.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
    </tbody>
  </table>
</div>
<h5>Destroyable Sub-elements</h5>
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
          Region containing the destroyable.
        </td>
        <td>
          <a href='/modules/regions'>Bounded Regions</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
    <destroyables name="Monument" materials="obsidian" completion="100%">
        <destroyable owner="blue">
           <region><cuboid min="46,16,26" max="45,14,25"/></region>
        </destroyable>
        <destroyable owner="red">
           <region><cuboid min="-44,16,-24" max="-45,14,-25"/></region>
        </destroyable>
    </destroyables>
