---
layout: page-single

category: "예시"
category_lead:  "XML 파일 예시"
title:  "예시"

---

로테이션에 있는 맵의 XML파일에 주석을 달았습니다. 파일이 개별 모듈로 분할되고 모듈의 기능이 설명됩니다. 각 섹션에는 [<i class="fa fa-share"></i>](#) 처럼 생긴 관련 모듈 페이지에 대한 링크가 포함되어 있습니다.

<div class="alert alert-warning"><strong>참고</strong> XML코드 예제는 오래 되었을 수 있으며 더이상 사용되지 않는 기능들이 사용되었을 수 있습니다.<br/> 항상 관련 모듈 페이지를 확인하여 사용하려는 기능이 여젼히 유효한지 확인하세요</div>

<div class="row">
    {% for map in site.data.maps %}
    <div class="col-sm-6 col-lg-3 center">
        <div id="{{ map.slug }}" class="thumbnail map-thumbnail">
            <div class="map-image" style="background-image:url('../img/examples/{{ map.slug }}.png');">
                <div class="map-banner">
                    <a href="{{ map.slug }}" class="map-name"><strong>{{ map.name }}</strong></a>
                    <span class="map-gamemode">{{ map.gamemode}}</span>
                </div>
            </div>
        </div>
    </div>
    {% endfor %}
</div>
