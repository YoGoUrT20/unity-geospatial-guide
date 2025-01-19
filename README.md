# AR Geospatial Project Setup Guide

This guide follows the official [Google AR Geospatial Creator documentation](https://developers.google.com/ar/geospatialcreator/unity/quickstart).

## Prerequisites

- Unity 6000.0.15f1 and higher
- Required packages:
  - [Cesium for Unity](https://github.com/CesiumGS/cesium-unity/releases/) (.tgz file)
  - [ARCore Extensions](https://github.com/google-ar/arcore-unity-extensions/releases/tag/1.47.0) (arf6.tgz file)

## Setup Instructions


### 1. Project Creation and Package Installation
1. Create a new Unity 3D Mobile project
2. Close it and open the project using android editor version
3. In Package Manager:
   - Click the '+' button in the top left
   - Select "Install package from tarball"
   - Install both Cesium Unity and ARCore Extensions packages

### 2. Import Geospatial Sample
1. In Package Manager, navigate to ARCore Extensions
2. Click "Samples"
3. Import the Geospatial sample
4. Open the scene: `/Geospatial Sample/Scenes/GeospatialArf6.unity`

### 3. Build Settings
1. Go to File -> Build Profiles
2. Select Android platform
3. In Scene list:
   - Add the open Geospatial scene
   - Deselect `Scenes/SampleScene`

### 4. Android Settings Configuration
   - Under Adaptive Performance:
      - Enable Android Provider
   - In project settings -> Player -> Android tab:
     - Under Other Settings:
       - Change Color Space from Linear to Gamma
       - Disable Auto Graphics API
       - Remove Vulkan from Graphics API
     - Under Identification:
       - Set Minimum API Level to 28

### 5. Google Cloud Setup
1. Visit the [Google Cloud Console](https://console.cloud.google.com/apis/dashboard)
2. Enable required APIs:
   - [Talis API](https://console.cloud.google.com/marketplace/product/google/tile.googleapis.com)
   - [ARCore API](https://console.cloud.google.com/marketplace/product/google/arcore)
3. Generate API Key:
   - Navigate to API & Services -> Credentials
   - Create new API key

### 6. Unity AR Configuration
1. In project settings:
   - Go to XR Plug-in Management
   - Enable Google ARCore
   - Under ARCore Extensions:
     - Set Android Authentication Strategy to API Key
     - Paste your API key
     - Enable Geospatial and Geospatial Creator features

### 7. Scene Setup
1. In Hierarchy window:
   - Right-click on Scene -> XR -> AR Geospatial Creator Origin
   - Select the created object
   - In Inspector, add Cesium Georeference component
   - Paste in the API key
2. In Scene view:
   - Open Layers (third tab from right)
   - Disable UI
### 8. Camera fix
1. In Assets:
   - Go to `Settings` folder
   - CLick on `Mobile_Rendering`
   - Add rendering feature:
     - `AR Background Renderer feature`
### 9. Build and Run
1. Head to File -> Build Profiles
2. Build 
