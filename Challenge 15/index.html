// Lay the topographical map tile
let topoLayer = L.tileLayer(
  "https://{s}.tile.opentopomap.org/{z}/{x}/{y}.png'",
  {
    attribution:
      'Map data: &copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors, <a href="http://viewfinderpanoramas.org">SRTM</a> | Map style: &copy; <a href="https://opentopomap.org">OpenTopoMap</a> (<a href="https://creativecommons.org/licenses/by-sa/3.0/">CC-BY-SA</a>)',
  });

// Create the map object and add topoLayer to it
let earthquakeMap = L.map("map", {
  center: [
    40.7, -94.5
  ],
  zoom: 3
});

topoLayer.addTo(earthquakeMap);

// Get and process geojson data 
d3.json("https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/all_week.geojson").then(function (earthquakeData) {

  // Function to set style for each earthquake marker
  function defineStyle(feature) {
    return {
      opacity: 1,
      fillOpacity: 1,
      fillColor: determineColor(feature.geometry.coordinates[2]),
      color: "#000000",
      radius: calculateRadius(feature.properties.mag),
      stroke: true,
      weight: 0.5
    };
  }

  // Determine marker color based on depth
  function determineColor(depth) {
    switch (true) {
      case depth > 90:
        return "#ea2c2c";
      case depth > 70:
        return "#ea822c";
      case depth > 50:
        return "#ee9c00";
      case depth > 30:
        return "#eecc00";
      case depth > 10:
        return "#d4ee00";
      default:
        return "#98ee00";
    }
  }

  // Calculate radius based on magnitude
  function calculateRadius(magnitude) {
    if (magnitude === 0) {
      return 1;
    }
    return magnitude * 4;
  }

  // Process geojson data
  L.geoJson(earthquakeData, {
    // Convert each feature into a marker
    pointToLayer: function (feature, latlng) {
      return L.circleMarker(latlng);
    },
    // Apply style using defineStyle function
    style: defineStyle,
    // Create popups for each marker displaying magnitude and location
    onEachFeature: function (feature, layer) {
      layer.bindPopup(
        "Magnitude: "
        + feature.properties.mag
        + "<br>Depth: "
        + feature.geometry.coordinates[2]
        + "<br>Location: "
        + feature.properties.place
      );
    }
  }).addTo(earthquakeMap);

  // Create a legend control object
  let mapLegend = L.control({
    position: "bottomright"
  });

  // Add details for the legend, setting colors for depth ranges
  mapLegend.onAdd = function () {
    let div = L.DomUtil.create("div", "info legend");

    let depthRanges = [-10, 10, 30, 50, 70, 90];
    let depthColors = [
      "#98ee00",
      "#d4ee00",
      "#eecc00",
      "#ee9c00",
      "#ea822c",
      "#ea2c2c"
    ];

    // Loop through to generate a label with a colored box for each interval
    for (let i = 0; i < depthRanges.length; i++) {
      div.innerHTML += "<i style='background: " + depthColors[i] + "'></i> "
        + depthRanges[i] + (depthRanges[i + 1] ? "&ndash;" + depthRanges[i + 1] + "<br>" : "+");
    }
    return div;
  };

  // Add legend to the map
  mapLegend.addTo(earthquakeMap);
});
