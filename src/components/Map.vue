mounted() {
  // initialize the map
  const map = L.map("map").setView([51.505, -0.09], 13);

  // add a tile layer
  L.tileLayer("https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png", {
    attribution: "Map data © OpenStreetMap contributors",
  }).addTo(map);

  // add the GeoJSON polygons
  const geojson = {
    type: "FeatureCollection",
    features: [
      {
        type: "Feature",
        properties: {},
        geometry: {
          type: "Polygon",
          coordinates: [
            [
              [-0.105438232421875, 51.51853866882627],
              [-0.11608123779296875, 51.509865566482324],
              [-0.09189605712890625, 51.50932260369934],
              [-0.105438232421875, 51.51853866882627],
            ],
          ],
        },
      },
      {
        type: "Feature",
        properties: {},
        geometry: {
          type: "Polygon",
          coordinates: [
            [
              [-0.07617950439453124, 51.51235523438118],
              [-0.0641632080078125, 51.50868349125443],
              [-0.05832672119140625, 51.51441809300063],
              [-0.0696563720703125, 51.51686931451862],
              [-0.07617950439453124, 51.51235523438118],
            ],
          ],
        },
      },
    ],
  };

  L.geoJSON(geojson).addTo(map);
}
