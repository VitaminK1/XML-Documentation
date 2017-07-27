---
layout: page

category: "모듈"
title:  "사용자 정의 투사체"

---

Custom projectile types can be defined and applied to items in [kits](/modules/kits).
These items effectively become either weapons that shoot the custom projectile,
or the item form of the custom projectile itself.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Projectiles Element</th>
        <th>Description</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<projectiles> </projectiles>' | escape_once}}</code>
          </span>
        </td>
        <td>Node containing the custom projectile definitions.</td>
        <td></td>
      </tr>
      <tr>
        <th colspan='2'>Sub-elements</th>
        <th>Value/Children</th>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<projectile> </projectile>' | escape_once}}</code>
          </span>
        </td>
        <td>
          A custom projectile definition.
        </td>
        <td>
          <span class='label label-default'>Projectile Sub-elements</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<h5>Projectile Attributes</h5>
<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th style='min-width: 150px;'>Attribute</th>
        <th>Description</th>
        <th style='min-width: 100px;'>Value</th>
        <th style='min-width: 100px;'>Default</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>id</code>
        </td>
        <td>Unique identifier used to reference this projectile from other places in the XML.</td>
        <td>
          <span class='label label-primary'>String</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>name</code>
        </td>
        <td>The display name of this projectile, used in "shot by" messages, etc.</td>
        <td>
          <span class='label label-primary'>String</span>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>throwable</code>
        </td>
        <td>
          Items are consumed when using them to shoot this projectile
          (making them more like grenades than guns).
        </td>
        <td>
          <span class='label label-primary'>true/false</span>
        </td>
        <td>true</td>
      </tr>
      <tr>
        <td>
          <code>projectile</code>
        </td>
        <td>The entity this projectile is materialized as.</td>
        <td>
          <a href='/reference/entity_types'>Entity Type</a>
        </td>
        <td>
          <span class='label label-default'>Arrow</span>
        </td>
      </tr>
      <tr>
        <td>
          <code>damage</code>
        </td>
        <td>The amount of damage this projectile deals.</td>
        <td>
          <span class='label label-primary'>Half-hearts</span>
        </td>
        <td>0.0</td>
      </tr>
      <tr>
        <td>
          <code>velocity</code>
        </td>
        <td>The speed at which the projectile moves.</td>
        <td>
          <span class='label label-primary'>Meters/tick</span>
        </td>
        <td>1.0</td>
      </tr>
      <tr>
        <td>
          <code>click</code>
        </td>
        <td>
          The click action that fires the projectile.
          <br/>
          Accepts <code>right</code>, <code>left</code> or <code>both</code>.
        </td>
        <td>
          <span class='label label-primary'>Click Action</span>
        </td>
        <td>
          <code>both</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>effects</code>
        </td>
        <td>The potion effects to apply to players hit by this projectile.</td>
        <td>
          <a href='/modules/potions'>Potion Effect</a>
        </td>
        <td></td>
      </tr>
      <tr>
        <td>
          <code>destroy-filter</code>
        </td>
        <td>
          <span class='label label-default' title='Can be this attribute or a sub-element.'>Property</span>
          Filter if/what blocks get destroyed when hit with this projectile.
        </td>
        <td>
          <a href='/modules/filters'>Filter</a>
        </td>
        <td>
          <code>deny-all</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>cooldown</code>
        </td>
        <td>Minimum time between each firing of this projectile.</td>
        <td>
          <a href='/reference/time_periods'>Time Period</a>
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>
<h5>Projectile Sub-elements</h5>
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
            <code>{{'<destroy-filter>' | escape_once}}</code>
          </span>
        </td>
        <td>
          <span class='label label-default' title='Can be this sub-element or an attribute.'>Property</span>
          Filter if/what blocks get destroyed when hit with this projectile.
        </td>
        <td>
          <a href='/modules/filters'>Filters</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<effect>' | escape_once}}</code>
          </span>
        </td>
        <td>A potion effect to apply to players hit by this projectile.</td>
        <td>
          <a href='/modules/potions'>Potion Effect</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
    <!-- Create the projectile "template" -->
    <projectiles>
        <projectile
            id="lazer"
            name="lazer"
            projectile="Snowball"
            velocity="3.5"
            damage="50"
            throwable="false"
            cooldown="5s"/>
    </projectiles>

    <!-- Apply the projectile to an item -->
    <kits>
        <kit name="lazer-kit">
            <item projectile="lazer" name="`alazer gun" material="stick"/>
        </kit>
    </kits>


<br/>

### Modifying Bow Projectiles

Bows can be modified to shoot a different projectile at a custom speed. The PGM plugin will calculate the damage the projectile does using the same formula as minecraft does for arrows. This means that a flying fish with a velocity of 40 will almost certainly kill you. Projectiles can also have custom [potion effects](/modules/potions) which are applied to the target when it is hit.

`NOTE:` You can currently only modify all bow projectiles, this means no normal and custom bow at the same time.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Projectiles Element</th>
        <th>Description</th>
        <th>Value/Children</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<modifybowprojectile> </...>' | escape_once}}</code>
          </span>
        </td>
        <td>Node containing the modify bow projectile settings.</td>
        <td>
          <span class='label label-default'>Bow Projectile Sub-elements</span>
        </td>
      </tr>
      <tr>
        <td colspan='3'>
          <b>Sub-elements</b>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<projectile> </projectile>' | escape_once}}</code>
          </span>
        </td>
        <td>
          The entity to use as the bows projectile.
        </td>
        <td>
          <a href='/reference/entity_types'>Entity Type</a>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<velocityMod> </velocityMod>' | escape_once}}</code>
          </span>
        </td>
        <td>
          The velocity modifier of the bows projectile.
        </td>
        <td>
          <span class='label label-primary'>Number</span>
        </td>
      </tr>
      <tr>
        <td>
          <span class='highlight'>
            <code>{{'<effect> </effect>' | escape_once}}</code>
          </span>
        </td>
        <td>
          A potion effect to apply to players hit by the bow projectile.
        </td>
        <td>
          <a href='/modules/potions'>Potion Effect</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>

Examples

    <modifybowprojectile>
        <projectile>EnderPearl</projectile>
        <velocityMod>2.5</velocityMod>

        <!-- Projectile potion effect -->
        <effect duration="5" amplifier="1">poison</effect>
    </modifybowprojectile>

    <modifybowprojectile>
        <effect duration="8" amplifier="1">wither</effect>
    </modifybowprojectile>


All the following projectiles are guaranteed to work. See [mrapple/Bukkit Entity Spawning.md](https://gist.github.com/4617111) for a list of tested entities.

<div class='table-responsive'>
  <table class='table table-striped table-condensed'>
    <thead>
      <tr>
        <th>Supported Entity Types</th>
        <th></th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>Arrow</code>
        </td>
        <td>
          <code>Egg</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>EnderPearl</code>
        </td>
        <td>
          <code>Fireball</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>LargeFireball</code>
        </td>
        <td>
          <code>SmallFireball</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>Snowball</code>
        </td>
        <td>
          <code>ThrownExpBottle</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>WitherSkull</code>
        </td>
        <td>
          <code>TNTPrimed</code>
        </td>
      </tr>
    </tbody>
  </table>
</div>
