Mermaid is a **powerful tool** for **creating diagrams and visualizations using text**. It is especially **useful in Markdown environments** like Obsidian, GitHub, and Notion (with extensions), where you can quickly visualize concepts using flowcharts, sequence diagrams, Gantt charts, and more.

Here's a **complete guide** on using Mermaid to create **flowcharts**:
[[toc]]

---
# FLowcharts 
## Basic Syntax

In Mermaid, flowcharts are declared using the `graph` or `flowchart` keyword followed by a flow direction:

- `TD` (Top to Bottom)
- `LR` (Left to Right)
- `BT` (Bottom to Top)
- `RL` (Right to Left)

The basic syntax for a Mermaid flowchart looks like this:

```mermaid
graph TD
    A --> B
    B --> C
    C --> D
```

In this example:
- `graph TD` declares a top-to-bottom flowchart.
- The `-->` defines a directed edge (arrow) between nodes.


>[!danger] WARNING
If you are using the word "end" in a Flowchart node, capitalize the entire word or any of the letters (e.g., "End" or "END"), or apply this [workaround](https://github.com/mermaid-js/mermaid/issues/1444#issuecomment-639528897). Typing "end" in all lowercase letters will break the Flowchart.

>[!danger] WARNING
If you are using the letter "o" or "x" as the first letter in a connecting Flowchart node, add a space before the letter or capitalize the letter (e.g., "dev--- ops", "dev---Ops").
Typing "A---oB" will create a [circle edge](https://mermaid.js.org/syntax/flowchart.html#circle-edge-example).
Typing "A---xB" will create a [cross edge](https://mermaid.js.org/syntax/flowchart.html#cross-edge-example).

---
## Node Definition

Nodes can be defined in different styles:
1. **Text-only nodes**: Simply write the node’s label (e.g., `A` or `B`) and connect them with arrows.
  Prefer Writing within ```"`As This Supports Markdown`"```
2. **Styled nodes**: Use parentheses, brackets, or square brackets for different shapes.
- **Rectangle (Process):** use `A[Text]`
- **Rounded Rectangle (Action):** use `A(Text)`
- **Stadium (Input/Output):** use `A([Text])`
- **Circle (Start/End):** use `A((Text))`
- **Subroutine (Function):** use `A[[Text]]`
- **Rhombus (Decision):** use `A{Text}`
- **Cylinder (Data):** use `A[(Text)]`
- **Flag (Loops):** use `A>Text]`
- **Hexagon (Preparation):** use `A{{Text}}`
- **Double Circles(Stop):** Use `((()))`
- **Parallelogram (Input/Output):** use `A[/Text/]`
- **Trapezoid (Manual Operations):** use `A[/Text/]`
>[!info] You may use `\` instead of `/` to change the indent of paralleograms and trapezoids
## Arrows and Links

Arrows (`-->`) between nodes define the flow of the chart.
It is possible declare **many links in the same line** as  `A -- text --> B -- text2 --> C`
Links can be **made longer by adding extra dashes **
### Types : 

- **Straight Arrow**: `-->` 
- **Dotted Arrow**: `-.->` .
- **Thick Arrow**: `\==>` .
- **Invisible Link**: `~~~` 

- **Cross Arrow: `--x` 
- **Circle Arrow: `--o` 
- **Multi-Directional Arrow**: Suited with any type example `o--o` 

---


```mermaid

flowchart LR
    X[My link is invisible] ~~~ Y[Start]
    Y[Start]  o==o Z["`Different Node **Shapes** OK?`"]
    Z -.-> A(Round Rectangle)
    Z -.-> B([Stadium Shaped])
    Z -.-> C((Circular))
    Z -.-> D[[Subroutine]]
    Z -.-> E{Rhombus}
    Z -.-> F[(Cylindrical)]
    Z -.-> G>FLag]
    Z -.-> H{{Hexagon}}
    Z -.-> I(((Double Circles)))
    Z -.-> J[/Parallelogram /]
    Z -.-> K[/Trapezoid\]

```

---
## Text in Nodes

### Link Labels
You can use the `|label|` syntax to add more complex or directional labels.

```mermaid
graph TD
    A -->|Yes| B
    A -->|No| C
```
### Multiline Text in Nodes
To add multiline text inside a node, use `<br>` tags.

```mermaid
graph TD
    A[This is<br>multi-line<br>text]
    B[Another node]
    A --> B
```


---

##  Subgraphs
Incorporated with `subgraph` as keyword it allow you to group nodes into sections. 
Each **Subgraph is a graph in itself**.** It has a direction but it **is ignored when it's connected parent has different direction**

```mermaid
graph TD
    subgraph Department 1
    direction TB
        A1[Node A1] --> A2[Node A2]
    end
    
    subgraph Department 2
    direction LR
        B1[Node B1] --> B2[Node B2]
    end
    
    A1 --> B1
```

---

## Adding Text and Annotations

You can add plain text annotations outside of nodes using `:::` or within a node with `:::nodeClass`.

```mermaid
graph TD
    A --> B
    B --> C

    classDef comment fill:none,stroke:none,font-style:italic;
    
    %% This is a comment outside of the chart
    class B comment
```

---
##  Node Styles and Customization

### Customizing Nodes
You can style individual nodes using the `style` directive.

- `fill`: Background color.
- `stroke`: Border color.
- `stroke-width`: Border thickness.

```mermaid
graph TD
    A[Start] --> B{Choose}
    B --> C[Option 1]
    B --> D[Option 2]

    style B fill:#f96,stroke:#333,stroke-width:2px
    style C fill:#bbf,stroke:#333
    style D fill:#bbf,stroke:#333
```

### Classes for Group Styling
You can group nodes under a class and then style them together.

- `classDef`: Defines the class styles.
- `class`: Assigns nodes to a class.


```mermaid
graph TD
    classDef green fill:#9f9,stroke:#333,stroke-width:2px;
    classDef red fill:#f99,stroke:#333,stroke-width:2px;
    
    A[Start] --> B{Choose}
    B --> C[Option 1]
    B --> D[Option 2]

    class A,B green
    class C,D red
```

---
## Real-Life Examples

### Nested Decisions

```mermaid
graph TD
    A[Start] --> B{Is it raining?}
    B -->|Yes| C{Do you have an umbrella?}
    B -->|No| D[Go outside]
    C -->|Yes| D
    C -->|No| E[Stay inside]
```

###  Multi-directional Flow

```mermaid
graph LR
    A[Start] --> B{Choose Path}
    B -->|Option 1| C[End 1]
    B -->|Option 2| D[End 2]
    C --> E[Review]
    D --> E
```

---
##  Tooling and Usage

### Supported Platforms
Mermaid is supported in various tools like:
- **Obsidian**: Directly supported in code blocks.
- **GitHub**: Add diagrams to your README files.
- **Markdown Editors**: Many editors with extensions support Mermaid.
- **Standalone tools**: You can render Mermaid diagrams with online editors (like [Mermaid Live Editor](https://mermaid-js.github.io/mermaid-live-editor/)).

---
# Sequence Diagram 

```mermaid
sequenceDiagram
    Alice->>John: Hello John, how are you?
    John-->>Alice: Great!
    Alice-)John: See you later!

```

# Pie chart

Drawing a pie chart is really simple in mermaid.

- Start with `pie` keyword to begin the diagram
    - `showData` to render the actual data values after the legend text. This is **_OPTIONAL_**
- Followed by `title` keyword and its value in string to give a title to the pie-chart. This is **_OPTIONAL_**
- Pie slices will be ordered clockwise in the same order as the labels.
    - `label` for a section in the pie diagram within `" "` quotes.
    - Followed by `:` colon as separator
    - Followed by `positive numeric value` (supported up to two decimal places)

```mermaid
%% You may play with these default values : %%
%%{init: {"pie": {"textPosition": 0.5}, "themeVariables": {"pieOuterStrokeWidth": "5px"}} }%%

pie showData
    title Key elements in Product X
    "Calcium" : 32
    "Potassium" : 46
    "Magnesium" : 10
    "Iron" :  12
```

# Quadrant Chart

It is used to plot data points on a **two-dimensional grid,** with one variable represented on the x-axis and another variable represented on the y-axis.
The syntax is `<text>: [x, y]` here x and y value is in the range 0 - 1

```mermaid
quadrantChart
    title Title Here
    x-axis Low Marker --> High Marker
    y-axis Low Anything --> High Anything 
    quadrant-1 Title1
    quadrant-2 Title2
    quadrant-3 Title3
    quadrant-4 Title4
    Campaign A: [0.3, 0.6]  
    Campaign B: [0.45, 0.23]
    Campaign C: [0.57, 0.69]
    Campaign D: [0.78, 0.34]
    Campaign E: [0.40, 0.34]
    Campaign F: [0.35, 0.78]
    

```

# Mind-Maps

The syntax for creating Mindmaps is simple and relies on indentation for setting the levels in the hierarchy.

Different Shapes discussed in flowchart are possible but not showing

```mermaid
mindmap
  root((Mermaid Guide))
    ))Flowchart((
      )Easy( 
      Very Customizacble
       Shapes
    Mind-Maps
      On effectiveness<br/>and features
      Easiest
        Uses
            Learning  techniques
            Strategic planning
            Argument mapping
    Tools
      Pen and paper
      Mermaid


```

# TImeline

Start with `timeline` followed by title and its name. then mention time periods and add things as -

```mermaid
timeline
    title Timeline of Industrial Revolution
    section 17th-20th century
        Industry 1.0 : Machinery, Water power, Steam <br>power
                     : Labour
        Industry 2.0 : Electricity, Internal combustion engine, Mass production
        Industry 3.0 : Electronics, Computers, Automation
    section 21st century
        Industry 4.0 : Internet, Robotics, Internet of Things
        Industry 5.0 : Artificial intelligence, Big data, 3D printing

```

# XY Chart

The chart can be drawn horizontal or vertical, default value is vertical by `xychart-beta horizontal 

The x-axis primarily serves as a categorical value, although it can also function as a numeric range value when needed. The y-axis is employed to represent numerical range values, it cannot have categorical values.

1. `x-axis title min --> max` x-axis will function as numeric with the given range
2. `x-axis "title with space" [cat1, "cat2 with space", cat3]` x-axis if categorical, categories are text type For y-axis only the title `y-axis title`

For **bar and line graphs just type in the y coordinates** as - 

```mermaid

xychart-beta
    title "Sales Revenue"
    x-axis [jan, feb, mar, apr, may, jun, jul, aug, sep, oct, nov, dec]
    y-axis "Revenue (in $)" 4000 --> 11000
    bar [5000, 6000, 7500, 8200, 9500, 10500, 11000, 10200, 9200, 8500, 7000, 6000]
    line [5000, 6000, 7500, 8200, 9500, 10500, 11000, 10200, 9200, 8500, 7000, 6000]

```
