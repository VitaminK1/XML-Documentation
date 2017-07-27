---
layout: page

category: "모듈"
title:  "클래스"

---

Classes allow the player to pick a specific class at the beginning of the game which gives them special abilities. Classes can be used on any map type, however care must be taken to balance them properly. Players can then change their class ingame with the `/class` command.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 300px;'>Classes Element</th>
        <th>Description</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<classes> </classes>' | escape_once}}</code>
          </span>
        </td>
        <td>A node containing a single class or a group of classes.</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>Sub-elements</th>
        <th>Value/Children</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<class> </class>' | escape_once}}</code>
          </span>
        </td>
        <td>
          A single player class.
        </td>
        <td>
          <span class='label label-default'>Class Sub-elements</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>Class Attributes</h5>
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
          <code>name</code>
        </td>
        <td>
          <span class='label label-danger'>Required</span>
          The classes name, must be a unique.
        </td>
        <td>
          <span class='label label-primary'>String</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>description</code>
        </td>
        <td>
          Description shown in the
          <code>/classes</code>
          command.
        </td>
        <td>
          <span class='label label-primary'>String</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>longdescription</code>
        </td>
        <td>
          Description shown in class picker menu.
        </td>
        <td>
          <span class='label label-primary'>String</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>icon</code>
        </td>
        <td>
          Icon shown in the class picker menu.
        </td>
        <td>
          <a href='/reference/inventory#material_matchers'>Single Material Pattern</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>family</code>
        </td>
        <td>
          <span class='label label-danger'>Required</span>
          "group" of classes (ghost squadron is "ghost").
        </td>
        <td>
          <a href='/modules/classes'>Class Family Name</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>sticky</code>
        </td>
        <td>
          If set to
          <code>true</code>
          players can't change the class mid game, instead they have to rejoin.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
      <tr>
        <td>
          <code>default</code>
        </td>
        <td>
          Specify if the class is the default class for new players.
          <br/>
          <i>One class must be set as the default.</i>
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
      <tr>
        <td>
          <code>restrict</code>
        </td>
        <td>
          If set to
          <code>true</code>
          only OP's can use this class.
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
    </tbody>
  </table>
</div>
<h5>Class Sub-elements</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Element</th>
        <th>Description</th>
        <th>Type</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<kit>' | escape_once}}</code>
          </span>
        </td>
        <td>
          The kit given to players using this class.
        </td>
        <td>
          <a href='/modules/kits'>Kits</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>

Example

    <classes family="ghost" sticky="true">
        <class name="Demon" default="true" description="Smoke and Fire!" icon="fireball">
            <kit>
                <potion duration="oo" amplifier="2" ambient="true">damage resistance</potion>
                <potion duration="oo" amplifier="1" ambient="true">speed</potion>
                <item slot="8" amount="16" material="cooked beef"/>
                <item slot="1" amount="5" name="`3Grenade" grenade="true" material="ender pearl"/>
            </kit>
        </class>
    </classes>
