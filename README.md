# Anamorphic Portrait Generator

A browser-based tool for creating line-based anamorphic sculptures that can be fabricated with laser cutting. These sculptures reveal a portrait/image when viewed from a specific angle.

![Example of an anamorphic sculpture](https://i.imgur.com/example.png)

## Overview

The Anamorphic Portrait Generator converts standard 2D images into anamorphic line patterns that can be laser cut and assembled into a physical sculpture. When viewed from a specific angle (the "sweet spot"), the scattered vertical lines align to reveal the original image.

## Technical Specifications

### Physical Dimensions
- **Default Output Size**: 120mm × 300mm
- **Customizable**: All dimensions can be adjusted using the interface sliders
- **All measurements**: In millimeters (mm)

### Structure
- **Top & Bottom**: Horizontal oval discs that hold the vertical rods
- **Connecting Rods**: Vertical rods of varying thickness that connect the two ovals
- **3D Effect**: Rods are scattered within the 3D space (up to 10mm from edge)
- **Assembly**: Vertical rods fit into slots on the ovals, creating the full structure

### Output Format
- **SVG Export**: Vector graphics optimized for laser cutting
- **DXF Export**: CAD format for manufacturing (implementation placeholder)
- **Curve Quality**: Configurable smoothness for laser cutting optimization

## Features

### Image Processing
- **Upload**: Support for various image formats
- **Paste**: Direct paste from clipboard
- **Crop**: Built-in cropping tool
- **Grayscale Conversion**: Automatic conversion to grayscale

### Customization Options
- **Line Count**: Adjust the number of vertical lines (10-60)
- **Oval Dimensions**: Width and height of the supporting ovals
- **Structure Height**: Overall height of the sculpture
- **Thickness Control**: Min and max thickness of the vertical rods
- **Line Style**: Choose between circles (discrete points) or smooth lines
- **Thickness Style**: Choose between disks (constant) or tapered (smoothly varying)
- **Margins**: Spacing around the structure

### Smoothing Options
- **Image Smoothing**: Controls brightness transition smoothness
- **Laser Path Smoothing**: Optimizes paths for clean laser cutting
- **Curve Quality**: Controls export detail level for manufacturing

### Preview Modes
- **Orthographic View**: Flat representation with orthographic projection
- **Front View**: Front perspective view of the structure
- **3D Preview**: Interactive 3D model with orbit controls
- **Sweet Spot**: Button to view the structure from the optimal viewing angle

### Project Management
- **Save Project**: Export project settings as JSON
- **Load Project**: Restore from saved project file

## Technical Implementation

### Technologies Used
- **Three.js**: 3D rendering in the browser
- **ES Modules**: Modern JavaScript module system
- **CropperJS**: Image cropping functionality
- **Pure JavaScript**: No additional framework dependencies

### Rendering Process
1. **Image Analysis**: Converts uploaded image to grayscale
2. **Sampling**: Samples brightness values along vertical lines
3. **Thickness Mapping**: Maps brightness to rod thickness (darker = thicker)
4. **Smoothing**: Applies multiple smoothing algorithms based on user settings
5. **SVG Generation**: Creates precise vector paths for laser cutting

### 3D Visualization
- **Model**: Realistic 3D representation with proper oval plates and rods
- **Materials**: Basic material rendering with lighting
- **Physics**: Accurate representation of the physical sculpture
- **Sweet Spot**: Camera position that demonstrates the anamorphic effect

## Anamorphic Effect Details

The anamorphic effect works through the principle of perspective alignment. When viewed from the "sweet spot" (typically from above), the scattered vertical rods visually align to form the original image. This effect is created by:

1. Sampling brightness values from the original image
2. Converting brightness to rod thickness (darker parts = thicker rods)
3. Strategically placing rods in 3D space while maintaining their alignment from one viewing angle
4. Creating varying thickness along each rod to represent image details

The physical sculpture maintains a 10mm margin from the edges of the oval plates to ensure structural integrity during manufacturing and assembly.

## Manufacturing Notes

### Laser Cutting Requirements
- **Material Recommendations**: Acrylic or wood (3-5mm thickness for ovals, 1-3mm for rods)
- **Kerf Compensation**: Accounted for in export files
- **Path Optimization**: Laser smoothing settings reduce jagged lines
- **Assembly Tabs**: Automatically generated in export files

### Assembly Instructions
1. Cut all pieces using a laser cutter
2. Clean any residue from the cut pieces
3. Insert vertical rods into the corresponding slots on the bottom oval
4. Carefully align and insert the top of each rod into the matching slot on the top oval
5. Secure with appropriate adhesive if needed
6. Place on a flat surface and view from the recommended angle

## Browser Compatibility

- **Modern Browsers**: Chrome, Firefox, Safari, Edge
- **WebGL Support**: Required for 3D preview
- **Mobile Support**: Responsive design works on tablets and phones

## Local Development

1. Clone the repository
2. Open `index.html` in a modern browser
3. No build process required - pure HTML/JS implementation

## License

MIT License - See LICENSE file for details.

## Contributing

Contributions welcome! Please feel free to submit a Pull Request.