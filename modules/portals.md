---
layout: page

category: "모듈"
title:  "포탈"

---

Portals teleport a player that enters the specified region to an exact location, by a certain offset amount or to a random location inside a region.

The position and direction attributes of a portal are relative to the players location and where they are looking. Prefix these values with an at symbol `@` to specify absolute values. Portals can be restricted to certain teams by defining their filter attribute.

Portals respond to any player move event, this allows almost instant teleportation as soon as the player matches the portals filter.

`TIP:` Copy the yaw and pitch from the F3 screen in minecraft (the `Facing: Direction (Axis) (Yaw/Pitch)` line).

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Element</th>
        <th>Description</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<portals> </portals>' | escape_once}}</code>
          </span>
        </td>
        <td colspan='2'>Node containing the portals on this map.</td>
      </tr>
      <tr>
        <th colspan='2'>Sub-elements</th>
        <th>Value/Children</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<portal>' | escape_once}}</code>
          </span>
        </td>
        <td>An individual portal node.</td>
        <td>
          <span class='label label-default'>Portal Sub-elements</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>Portal Attributes</h5>
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
          <code>x</code>
          ,
          <code>y</code>
          ,
          <code>z</code>
        </td>
        <td>Offset the players <code>X,Y,Z</code> position by the amount specified.</td>
        <td>
          <span class='label label-primary'>Number</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>region</code>
        </td>
        <td>
          <span class='label label-default' title='Can be either this attribute or a sub-element.'>Property</span>
          <span class='label label-danger'>Required</span>
          Region where this portals entrance is located.
          <br/>
          <i>Cannot combine an entrance region with <code>forward</code> or <code>transit</code> properties.</i>
        </td>
        <td>
          <a href='/modules/regions'>Region</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>destination</code>
        </td>
        <td>
          <span class='label label-default' title='Can be either this attribute or a sub-element.'>Property</span>
          Destination of the portal, teleports players to a random point inside the region.
          <br/>
          <i>Cannot combine an exit region with <code>reverse</code> or <code>transit</code> properties.</i>
        </td>
        <td>
          <a href='/modules/regions'>Randomize-able Region</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>filter</code>
        </td>
        <td>
          <span class='label label-default' title='Can be either this attribute or a sub-element.'>Property</span>
          Filter portal player access.
        </td>
        <td>
          <a href='/modules/filters'>Filter</a>
        </td>
        <td>
          <code>{{'<always/>' | escape_once}}</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>forward</code>
        </td>
        <td>
          <span class='label label-default' title='Can be either this attribute or a sub-element.'>Property</span>
          Apply forward transform on rising edge
        </td>
        <td>
          <a href='/modules/filters'>Dynamic Filter</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>reverse</code>
        </td>
        <td>
          <span class='label label-default' title='Can be either this attribute or a sub-element.'>Property</span>
          Apply reverse transform on rising edge
        </td>
        <td>
          <a href='/modules/filters'>Dynamic Filter</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>transit</code>
        </td>
        <td>
          <span class='label label-default' title='Can be either this attribute or a sub-element.'>Property</span>
          Apply forward transform on rising edge and reverse transform on falling edge
          <br/>
          <i>Cannot combine <code>transit</code> property with <code>forward</code> or <code>reverse</code> properties.</i>
        </td>
        <td>
          <a href='/modules/filters'>Dynamic Filter</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>observers</code>
        </td>
        <td>
          <span class='label label-default' title='Can be either this attribute or a sub-element.'>Property</span>
          Filter portal observer access.
        </td>
        <td>
          <a href='/modules/filters'>Filter</a>
        </td>
        <td>
          <code>{{'<always/>' | escape_once}}</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>sound</code>
        </td>
        <td>Play the portal sound</td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>true</td>
      </tr>
      <tr>
        <td>
          <code>protect</code>
        </td>
        <td>Protect the portal entrance and exit regions.</td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
      <tr>
        <td>
          <code>bidirectional</code>
        </td>
        <td>Creates a dual-linked portal that goes both ways. This can only be used when all coordinates and directions are relative.</td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
      <tr>
        <td>
          <code>yaw</code>
        </td>
        <td>
          Specify the direction the player is looking horizontally from -180&deg; to 180&deg;.
          <br/>
          <i>South 0, East -90, North 180 and West 90.</i>
        </td>
        <td>
          <span class='label label-primary'>Number</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>smooth</code>
        </td>
        <td>Smoothly teleport players.</td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>false</td>
      </tr>
      <tr>
        <td>
          <code>pitch</code>
        </td>
        <td>
          Specify the direction the player is looking vertically from -90&deg; to 90&deg;.
          <br/>
          <i>-90 is straight up 90 is straight down.</i>
        </td>
        <td>
          <span class='label label-primary'>Number</span>
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>
<h5>Portal Sub-elements</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Element</th>
        <th>Description</th>
        <th>Value/Children</th>
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
          Region where this portals entrance is located.
        </td>
        <td>
          <a href='/modules/regions'>Regions</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<destination>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          Destination of the portal, teleports players to a random point inside the region.
          <br/>
          <i>Region is automatically filtered against block place.</i>
        </td>
        <td>
          <a href='/modules/regions'>Randomize-able Regions</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          Filter portal player access.
        </td>
        <td>
          <a href='/modules/filters'>Filters</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<forward>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          Apply forward transform on rising edge
        </td>
        <td>
          <a href='/modules/filters'>Dynamic Filters</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<reverse>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          Apply reverse transform on rising edge
        </td>
        <td>
          <a href='/modules/filters'>Dynamic Filters</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<transit>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          Apply forward transform on rising edge and reverse transform on falling edge
          <br/>
          <i>Cannot combine <code>transit</code> property with <code>forward</code> or <code>reverse</code> properties.</i>
        </td>
        <td>
          <a href='/modules/filters'>Dynamic Filters</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<observers>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be either this sub-element or an attribute.'>Property</span>
          Filter portal observer access.
        </td>
        <td>
          <a href='/modules/filters'>Filters</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<br/>
Examples

    <!-- Portals from Harb -->
    <portals>
        <!-- Adds 110 to the players X position, Y, Z, pitch & yaw remain unchanged -->
        <portal x="110">
            <region><cuboid min="-56,33,-1" max="-55,35,2"/></region>
        </portal>
        <!-- Subtracts 110 from the players X position, Y, Z, pitch & yaw remain unchanged -->
        <portal x="-110">
            <region><cuboid min="56,33,-1" max="57,35,2"/></region>
        </portal>
    </portals>

    <portal yaw="@0" sound="false">
        <forward>
            <all>
                <filter id="portal-filter"/>
                <region id="portal-region"/>
            </all>
        </forward >
        <destination>
            <region id="portal-destination"/>
        </destination>
    </portal>
<p>
  <a class='btn btn-primary btn-xs btn-more collapsed' data-target='#collapse-portal-example' data-toggle='collapse'>Examples</a>
</p>
<div class='collapse' id='collapse-portal-example' markdown='1'>

    <portals>
        <!-- Moves the player to exactly X:10 Y:8 Z:45, pitch & yaw remain unchanged -->
        <portal x="@10" y="@8" z="@45">
            <region><cuboid min="-56,33,-1" max="-55,35,2"/></region>
        </portal>

        <!-- Adds 12 to the players Z position, turning them to face east and 10° up -->
        <portal z="12" pitch="@10" yaw="@-90">
            <region><cuboid min="-56,33,-1" max="-55,35,2"/></region>
        </portal>

        <!-- Teleport the player from portal-entrance to a random point inside portal-exit -->
        <portal region="portal-entrance">
            <destination><region id="portal-exit"/></destination>
        </portal>
    </portals>

</div>
