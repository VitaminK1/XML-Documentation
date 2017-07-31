---
layout: page

category: "예시"
category_lead:  "XML 파일 예시"
title:  "QK: Mine"

---

[<i class="fa fa-share right-ref-link"></i>](/modules/main)
XML파일 버전을 지정한 다음 메인 맵 모듈을 열고 지도 이름, 버전 및 목표를 지정합니다.

<?xml version="1.0"?>
<map proto="1.3.6">
<name>QK: Mine</name>
<version>1.0</version>
<objective>Kill other players and reach first to 26 kills!</objective>
<authors>
    <author contribution="Map Building">andreaci</author>
</authors>
<contributors>
    <contributor contribution="XML Coding">Avis Network</contributor>
</contributors>
<teams>
    <team color="yellow" max="20" max-overfill="25" show-name-tag="false">Players</team>
</teams>
<kits>
    <kit name="player">
 <item slot="0" name="Railgun" unbreakable="true">wood hoe</item>
 <potion duration="oo" amplifier="2">speed</potion>
 <potion duration="oo" amplifier="2">jump</potion>
 <potion duration="3" amplifier="100">damage resistance</potion>
 <potion duration="3">invisibility</potion>
    </kit>
</kits>
<spawns>
    <spawn kit="player" team="players">
        <point>-30.5,11.5,-28.5</point>
        <point>-30.5,20.5,-6.5</point>
        <point>-17.5,10.5,10.5</point>
        <point>7.5,9.5,-31.5</point>
        <point>8.5,20.5,10.5</point>
        <point>14.5,2.5,2.5</point>
        <point>16.5,10.5,18.5</point>
        <point>21.5,9.5,-24.5</point>
    </spawn>
    <default>
 <point>0.5,35,0.5</point>
    </default>
</spawns>
<autorespawn time="2"/>
<itemremove>
    <item>wood hoe</item>
</itemremove>
<friendlyfire>true</friendlyfire>
<regions>
    <apply block="deny-all" use="deny-all">
 <rectangle min="-oo,-oo" max="oo,oo"/>
    </apply>
</regions>
<arcade>
 <quake/>
</arcade>
</map>
