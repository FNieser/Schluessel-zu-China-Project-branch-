# Unlocking China

How to Use It

As it is a single, self-contained HTML file, no installation or web server is required.

*   Click on the `Schluessel_zu_China_Visualisierung.html` file
*   Download the file (Download symbol next to the 'Raw' and 'Copy Raw-File' symbols)
*   Open the file in a modern web browser (e.g., Chrome, Firefox, Edge).

XML Relations Network Visualization

This project is an interactive, web-based visualization of a relationship network extracted from XML data. It represents bibliographic entries and persons as nodes and visualizes the different types of relationships (citations, references, etc.) between them as edges. The application is implemented in a single, standalone HTML file and uses the JavaScript library vis.js for network rendering.

*   **Interactive Graph:** Nodes can be moved, selected, and inspected. The network layout is calculated dynamically.
*   **Hierarchy Filter:** Filter the displayed relationships by their hierarchical level (e.g., primary citations only, secondary only, etc.). Lower levels are retained as a gray "baseline structure" to maintain context.
*   **Filter by Relation Type:** Turn individual relationship types (e.g., CitOf, SecCit) on or off via checkboxes.
*   **Node Focus:** Select a specific node from a dropdown list to center it in the network and highlight its direct connections.
*   **Detailed Tooltips:** Hover over a node or edge to display detailed information.
*   **Legend:** A fixed legend at the bottom explains the color coding for the different hierarchies and node types.

The network will load, and you can immediately interact with the controls.

Controls Explained

*   **Hierarchy Filter:**
    *   **All Relations:** Displays all active relationships in their respective colors.
    *   **1st Degree (Primary):** Highlights primary relationships (CitOf, CitIn).
    *   **2nd Degree (Secondary):** Highlights secondary relationships (SecCit) and represents primary relationships as a gray baseline.
    *   **3rd Degree (Tertiary):** Highlights tertiary relationships (ThirdCit) and represents lower levels as a gray baseline.
    *   **Possible New Relations:** Isolates potentially new, not yet confirmed relationships (PotCit).
    *   **Confirmed New Relations:** Isolates newly discovered and confirmed relationships (NewCit).

*   **Relation Types:**
    These checkboxes allow you to selectively show and hide types of edges. The colors correspond to those in the legend:
    *   CitOf, CitIn (Primary, Red)
    *   SecCit (Secondary, Green)
    *   ThirdCit (Tertiary, Blue)
    *   PotCit (Potential, Brown)
    *   NewCit (New & Confirmed, Violet)

*   **Focus Node:**
    Select a bibliographic entry from the list to center the network on this node and zoom in.

*   **Reset:**
    Resets the focus and applies the current filters to the entire network.

Technical Details

Technologies Used

*   **HTML5:** Basic page structure.
*   **CSS3:** User interface styling.
*   **Bootstrap 5:** CSS framework for a responsive and clean layout of the controls.
*   **JavaScript (ES6):** Application logic for filtering and interaction.
*   **vis.js (vis-network):** The core library for creating and manipulating the interactive network visualization.

Data Structure

The network data (nodes and edges) are embedded directly as JavaScript arrays (`nodeData`, `edgeData`) in the HTML file.

Nodes (`nodeData`)

Each node represents an entity (e.g., a bibliographic source) and has the following structure:

```json
{
  "id": "bibl00023",
  "label": "A Madman's Diary",
  "type": "bibliography",
  "color": "#FFA500",
  "title": "ID: bibl00023\\nTyp: bibliography\\nTitel: A Madman's Diary...",
  "shape": "square",
  "size": 20
}
```

Edges (`edgeData`)

Each edge represents a relationship between two nodes and has the following structure:

```json
{
  "from": "bibl00021",
  "to": "bibl00023",
  "type": "CitOf",
  "hierarchy": "primary",
  "color": "#FF4444",
  "date": "",
  "desc": "",
  "width": 2
}
```
