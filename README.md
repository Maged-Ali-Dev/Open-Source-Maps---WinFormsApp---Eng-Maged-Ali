 Open Source Maps - WinForms Application

This project is a simple Windows Forms application that integrates OpenStreetMap using the WebView2 control and Leaflet.js for interactive map rendering. The app displays a map view of a specified location, allowing users to load OpenStreetMap tiles inside a WinForms interface.

Project Overview

The project utilizes the following key components:
1. C# Windows Forms - A graphical user interface framework for creating desktop applications on Windows.
2. WebView2 Control - Embeds web content (HTML, CSS, JavaScript) within a Windows Forms application.
3. Leaflet.js - A lightweight, open-source JavaScript library used for rendering interactive maps.
4. OpenStreetMap Tiles - Free, open-source map tiles provided by the OpenStreetMap community.

How It Works

1. Form Initialization:
   When the application starts, the `Form1` constructor is called, which initializes the form and invokes the `InitializeWebView2` method to set up the WebView2 control.

2. WebView2 Setup:
   The `InitializeWebView2` method:
   - Ensures that the WebView2 control is properly initialized.
   - Loads the required HTML, CSS, and JavaScript code that integrates Leaflet.js and OpenStreetMap tiles.
   - Injects this HTML content directly into the WebView2 control using `NavigateToString`, which renders the map inside the application window.

3. HTML and Leaflet.js:
   The HTML code defines a simple webpage structure:
   - Leaflet.js and its corresponding styles are imported via CDN.
   - A `div` element with an `id="map"` is created to hold the map.
   - JavaScript initializes the map using `L.map()`, setting the initial view to specified coordinates (for example, New York City). It uses OpenStreetMap tiles by calling `L.tileLayer()`, which pulls map data from the OpenStreetMap servers.
   - The map view is fully customizable by changing the coordinates and zoom level passed to the `setView` method.

4. Interactive Map:
   Once the map is rendered, users can interact with it:
   - Zoom in and out.
   - Pan the map to different locations.
   - View OpenStreetMap tiles with attributions.

Code Explanation

- C# Form1 Class: Handles form creation and WebView2 initialization.
- Leaflet.js: Renders the map inside the WebView2 control using the OpenStreetMap tile layer.
- WebView2 Control: Provides an embedded web view to display the interactive map.

How to Change Map Coordinates

To change the map’s initial location, update the coordinates in the JavaScript section of the HTML string:
```javascript
var map = L.map('map').setView([LATITUDE, LONGITUDE], ZOOM_LEVEL);
```
For example, to set the view to New York City:
```javascript
var map = L.map('map').setView([40.712776, -74.005974], 12);
```

Requirements

- .NET Framework or .NET Core
- Microsoft Edge WebView2 Runtime
- NuGet Package: Microsoft.Web.WebView2

How to Run the Project

1. Clone the repository.
2. Open the project in Visual Studio.
3. Build and run the solution.
4. The application will launch with an interactive map view powered by OpenStreetMap.

Customization

You can customize the map by:
- Changing the initial coordinates for different locations.
- Adding markers or layers using Leaflet.js.
- Integrating additional data or interactive features.

 
