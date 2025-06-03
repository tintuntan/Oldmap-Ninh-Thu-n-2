<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ninh Thuận Map App</title>
    <link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        #map {
            height: 100vh; /* Full height for mobile */
        }
        .popup-content {
            text-align: center;
        }
    </style>
</head>
<body>
    <h1 style="text-align: center;">Ninh Thuận Administrative Map</h1>
    <div id="map"></div>
    <script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
    <script>
        // Initialize the map
        const map = L.map('map').setView([11.588, 108.993], 10); // Center on Ninh Thuận

        // Add OpenStreetMap tiles
        L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
            maxZoom: 19,
        }).addTo(map);

        // Define the wards and communes with their coordinates and information
        const areas = [
            { name: "Phường Kinh Dinh", coords: [11.588, 108.993], info: "Merged from Kinh Dinh, Mỹ Hương, and Tấn Tài." },
            { name: "Phường Phủ Hà", coords: [11.590, 108.995], info: "Merged from Phủ Hà and Thanh Sơn." },
            { name: "Phường Phan Rang 1", coords: [11.591, 108.992], info: "Merged from Kinh Dinh, Phủ Hà, Đài Sơn, and Đạo Long." },
            { name: "Phường Phan Rang 2", coords: [11.592, 108.990], info: "Merged from Mỹ Bình, Mỹ Đông, Mỹ Hải, and part of Đông Hải." },
            { name: "Phường Phan Rang 3", coords: [11.593, 108.988], info: "Merged from Văn Hải and Khánh Hải." },
            { name: "Phường Phan Rang 4", coords: [11.594, 108.986], info: "Merged from Phước Mỹ and Đông Hải." },
            { name: "Phường Phan Rang 5", coords: [11.595, 108.984], info: "Merged from Đô Vinh." },
            { name: "Xã Ninh Sơn 1", coords: [11.596, 108.982], info: "Merged from Tân Sơn and Quảng Sơn." },
            { name: "Xã Ninh Sơn 2", coords: [11.597, 108.980], info: "Merged from Lâm Sơn and Lương Sơn." },
            { name: "Xã Ninh Sơn 3", coords: [11.598, 108.978], info: "Merged from Ma Nới and Hòa Sơn." },
            { name: "Xã Ninh Sơn 4", coords: [11.599, 108.976], info: "Merged from Mỹ Sơn and Phước Trung." },
            { name: "Xã Ninh Phước 1", coords: [11.600, 108.974], info: "Merged from Phước Dân and Phước Thuận." },
            { name: "Xã Ninh Phước 2", coords: [11.601, 108.972], info: "Merged from Phước Hữu and Phước Vinh." },
            { name: "Xã Ninh Phước 3", coords: [11.602, 108.970], info: "Merged from Phước Sơn and Phước Thái." },
            { name: "Xã Bác Ái 1", coords: [11.603, 108.968], info: "Merged from Phước Đại and Phước Tân." },
            { name: "Xã Bác Ái 2", coords: [11.604, 108.966], info: "Merged from Phước Thắng and Phước Bình." },
            { name: "Xã Bác Ái 3", coords: [11.605, 108.964], info: "Merged from Phước Hòa and Phước Thành." },
        ];

        // Add markers for each area
        areas.forEach(area => {
            L.marker(area.coords).addTo(map)
                .bindPopup(`<div class="popup-content"><b>${area.name}</b><br>${area.info}</div>`);
        });
    </script>
</body>
</html>
