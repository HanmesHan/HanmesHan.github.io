---
layout: single
author_profile: true
title: "Shichao Han"
excerpt: "Research, technology, and selected work"
---

## About Me

My name is Shichao Han (韩世超). I am a **PhD student** currently working and learning at the Kapteyn Astronomical Institute, University of Groningen. My research focuses on galaxy formation and evolution, in collaboration with Dr. Lingyu Wang and Prof. Scott Trager, using observations from both ground- and space-based telescopes. Before starting my PhD, I obtained my Master’s degree from the Cosmic Dawn Center at the University of Copenhagen, under the supervision of Prof. Johan Fynbo. I received my Bachelor’s degree from Lanzhou University.

Besides astronomy research, I enjoy photography, climbing, hiking, diving, and badminton. I have lived in three countries and traveled to 31 countries so far.

## My Footprints

<div class="travel-map-card">
  <div id="travel-map"></div>
  <p id="visited-country-list"></p>
</div>

<style>
  .travel-map-card {
    margin: 1.5em 0 2em;
    padding: 1.25em;
    border: 1px solid #e5e7eb;
    border-radius: 12px;
    background: #fff;
  }

  #travel-map {
    width: 100%;
    height: 460px;
  }

  #visited-country-list {
    margin: 0.8em 0 0;
    color: #4b5563;
    font-size: 0.95em;
  }
</style>

<script src="https://cdn.amcharts.com/lib/5/index.js"></script>
<script src="https://cdn.amcharts.com/lib/5/map.js"></script>
<script src="https://cdn.amcharts.com/lib/5/geodata/worldLow.js"></script>

<script>
  // 在这里填写去过的国家：ISO 两位国家代码 + 显示名称
  const visitedCountries = [
  { id: "JP", name: "Japan" },
  { id: "KR", name: "South Korea" },
  { id: "US", name: "United States" },
  { id: "CN", name: "China" },
  { id: "DK", name: "Denmark" },
  { id: "NL", name: "The Netherlands" },
  { id: "FR", name: "France" },
  { id: "DE", name: "Germany" },
  { id: "IT", name: "Italy" },
  { id: "GR", name: "Greece" },
  { id: "BG", name: "Bulgaria" },
  { id: "CZ", name: "Czechia" },
  { id: "PL", name: "Poland" },
  { id: "AE", name: "United Arab Emirates" },
  { id: "ID", name: "Indonesia" },
  { id: "PT", name: "Portugal" },
  { id: "ES", name: "Spain" },
  { id: "FO", name: "Faroe Islands" },
  { id: "SG", name: "Singapore" },
  { id: "MY", name: "Malaysia" },
  { id: "TH", name: "Thailand" },
  { id: "PH", name: "Philippines" },
  { id: "NO", name: "Norway" },
  { id: "IS", name: "Iceland" },
  { id: "TR", name: "Türkiye" },
  { id: "SE", name: "Sweden" },
  { id: "HU", name: "Hungary" },
  { id: "HR", name: "Croatia" },
  { id: "VA", name: "Vatican City" },
  { id: "CH", name: "Switzerland" },
  { id: "LT", name: "Lithuania" },
  { id: "SI", name: "Slovenia" }
];

  const root = am5.Root.new("travel-map");

  const chart = root.container.children.push(
    am5map.MapChart.new(root, {
      panX: "translateX",
      panY: "translateY",
      wheelX: "zoomX",
      wheelY: "zoomY",
      projection: am5map.geoNaturalEarth1()
    })
  );

  const worldSeries = chart.series.push(
    am5map.MapPolygonSeries.new(root, {
      geoJSON: am5geodata_worldLow,
      exclude: ["AQ"]
    })
  );

  worldSeries.mapPolygons.template.setAll({
    fill: am5.color(0xe5e7eb),
    stroke: am5.color(0xffffff),
    strokeWidth: 0.8,
    interactive: true,
    tooltipText: "{name}"
  });

  const visitedSeries = chart.series.push(
    am5map.MapPolygonSeries.new(root, {
      geoJSON: am5geodata_worldLow,
      include: visitedCountries.map(country => country.id)
    })
  );

  visitedSeries.mapPolygons.template.setAll({
    fill: am5.color(0x2563eb),
    stroke: am5.color(0xffffff),
    strokeWidth: 0.8,
    interactive: true,
    tooltipText: "{name}"
  });

  visitedSeries.mapPolygons.template.states.create("hover", {
    fill: am5.color(0x1d4ed8)
  });

</script>


## Contact

### Email: 
[shichao.han@astro.rug.nl](mailto:shan@astro.rug.nl) (Work)  
[shichao.han@rug.nl](mailto:shichao.han@rug.nl) (Work)  
[hanshichao2000@gmail.com](mailto:hanshichao2000@gmail.com) (Other)  

### Phone: 
+31 649812520  
+86 13716063658   

### Location
Kapteyn Astronomical Institute, University of Groningen  
Landleven 12  
9747 AD Groningen  
The Netherlands  
