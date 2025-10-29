# Cabinet Door Cut Planner

A comprehensive web-based tool for planning cabinet door construction with visual diagrams, optimized cutting layouts, and material purchase recommendations.

## Features

### 🎯 **Core Functionality**
- **Visual Door Construction Diagrams** - Exploded view with professional blueprint-style dimensioning
- **Optimized Cut Lists** - Automatic calculation of all door components with dual unit support (mm/inches)
- **Smart Board Layout** - Visual cutting diagrams showing how pieces fit on stock boards
- **Material Efficiency** - Automatic optimization for minimal waste
- **Stock Purchase Recommendations** - Calculate exactly what materials to buy based on what you already have

### 📐 **Technical Capabilities**
- **Dual Unit Support** - Input and display measurements in both millimeters and inches
- **Professional Dimensioning** - Blueprint-style dimension lines with witness marks and arrows
- **Waste Optimization** - Algorithm calculates most efficient use of 6ft and 8ft stock
- **Kerf & Trim Allowances** - Accounts for saw blade width and end trimming
- **Panel Clearance** - Includes wood movement allowance for panel fit

### 🖨️ **Print-Ready Output**
- **Ink-Saving Design** - White backgrounds with black text for economical printing
- **Landscape Board Layouts** - Optimal orientation for cutting diagrams
- **Page Breaks** - Clean separation between sections
- **Professional Format** - Ready for shop use

## How to Use

### 1. **Setup**
1. Open `cabinet_cut_planner.html` in any modern web browser
2. No installation required - runs entirely in the browser
3. For best results, use a local HTTP server (optional):
   ```bash
   # Python 3
   python -m http.server 8000
   
   # Python 2
   python -m SimpleHTTPServer 8000
   
   # Node.js
   npx http-server
   ```

### 2. **Configure Parameters**

#### **Fixed Parameters**
- **Primary Units**: Choose mm or inches for display
- **Overlays**: Side and top/bottom overlay measurements
- **Center Gap**: Space between double doors
- **Panel Allowance**: Clearance for wood movement (typically 0.8mm)
- **Component Widths**: 
  - Stile Width (typically 63mm)
  - Top Rail Width (typically 63mm) 
  - Bottom Rail Width (typically 89mm)
- **Joinery**: Tongue length and groove depth for rail/stile joints
- **Cutting**: Kerf width and end trim allowance
- **Stock Lengths**: Available board lengths (default: 1829mm, 2438mm)

#### **Existing Stock**
- **Existing 6ft boards**: Number of 1829mm boards you already have
- **Existing 8ft boards**: Number of 2438mm boards you already have

### 3. **Define Cabinet Openings**

For each cabinet opening, specify:
- **Name**: Descriptive name (e.g., "Base - Sink", "Upper - Left")
- **Width**: Cabinet opening width (not door width)
- **Height**: Cabinet opening height (not door height)  
- **Doors**: Number of doors (1 or 2)

### 4. **View Results**

#### **Cut List**
- Complete list of all pieces needed
- Cut lengths and widths for each component
- Organized by opening and door

#### **Door Construction Visual**
- Exploded view diagrams for each door
- Professional blueprint-style dimensioning
- Shows stile width, rail height, panel dimensions
- Proper witness marks and dimension lines

#### **Stock Purchase Recommendations**
- **Boards Needed**: Total required for project
- **Boards You Have**: Existing stock from settings
- **Boards to Purchase**: Exact amount to buy
- **Material Efficiency**: Waste percentage
- **Visual Indicators**: Green (sufficient stock) or Yellow (purchase needed)

#### **Board Layout**
- Visual cutting diagrams showing piece placement
- Optimized for minimal waste
- Clear board width identification (63mm Wide, 89mm Wide)
- Kerf allowances and end trim included

### 5. **Print & Export**

#### **Print**
Two print options are available:

1. **Print Full Project** - Complete documentation including:
   - Cut List with all parts
   - Door Construction Visuals with dimensions
   - Stock Purchase Recommendations
   - Board Layout diagrams
   - Mixed portrait/landscape orientation as needed

2. **Print Cutting Layouts** - Board and panel cutting diagrams only:
   - **Landscape orientation** for optimal viewing
   - Includes both linear board layouts (stiles/rails) and 2D panel layouts
   - Multiple boards per page when space allows
   - Clear section headers for "Board Layout" and "Panel Layout"
   - Ideal for shop floor use
   - Excludes all other project information

#### **Export**
- **CSV**: Cut list data for spreadsheet import
- **JSON**: Complete project data for backup/sharing

## Technical Details

### **Calculations**

#### **Door Dimensions**
- **Door Width**: `(Opening Width + 2×Side Overlay - Center Gap) ÷ Number of Doors`
- **Door Height**: `Opening Height + 2×Top/Bottom Overlay`

#### **Component Sizes**
- **Stile Length**: `Door Height`
- **Rail Length**: `Door Width - 2×Stile Width + 2×Tongue Length`
- **Panel Width**: `Door Width - 2×(Stile Width - Groove Depth) - Panel Allowance`
- **Panel Height**: `Door Height - (Top Rail Width - Groove Depth) - (Bottom Rail Width - Groove Depth) - Panel Allowance`

#### **Cutting Optimization**
- Groups pieces by width to avoid mixing different board widths
- Uses First Fit Decreasing algorithm for optimal board packing
- Calculates efficiency for both 6ft and 8ft stock
- Automatically selects most efficient stock length

### **File Structure**
```
cabinet_cut_planner.html    # Main application file
README.md                   # This documentation
```

### **Browser Compatibility**
- Chrome (recommended)
- Firefox
- Edge
- Safari
- Any modern browser with JavaScript support

## Tips for Best Results

### **Measurement Accuracy**
- Measure cabinet openings precisely
- Account for any irregularities in openings
- Use consistent units throughout project

### **Material Planning**
- Enter existing stock accurately
- Consider buying extra for mistakes/defects
- Check local lumber yard stock availability

### **Cutting Efficiency**
- Follow the board layout diagrams exactly
- Cut longest pieces first
- Use proper saw setup for kerf width
- Allow for end trim on each board

### **Printing**
- **Use "Print Cutting Layouts"** for shop floor cutting diagrams (automatic landscape)
  - Includes both board layouts (stiles/rails) and panel layouts (2D sheets)
  - Clear section headers separate the two layout types
- **Use "Print Full Project"** for complete documentation with all calculations
- Print on white paper for best visibility
- Consider laminating shop copies for durability
- Layouts will fit multiple items per page when space allows

## Troubleshooting

### **Print Issues**
- **Slow printing**: Complex SVG diagrams may cause delays
- **Missing diagrams**: Ensure JavaScript is enabled
- **Layout problems**: Try different browsers or print to PDF first

### **Calculation Errors**
- **Wrong dimensions**: Check opening measurements and parameters
- **Missing pieces**: Verify all openings are defined
- **Unit confusion**: Ensure consistent unit selection

### **Performance**
- **Slow loading**: Large projects with many openings may be slower
- **Browser issues**: Try refreshing or using a different browser

## Support

This is a standalone HTML application. For issues or improvements:
1. Check browser console for JavaScript errors
2. Verify all input values are reasonable
3. Try refreshing the page
4. Ensure JavaScript is enabled

## License

This project is provided as-is for educational and practical use in cabinet making and woodworking projects.
