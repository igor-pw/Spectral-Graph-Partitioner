# Graph Visualizer

A simple Java desktop application for analyzing, partitioning, and visualizing graphs stored in text and binary formats. The program provides a Swing-based graphical interface where you can choose a graph file, configure partitioning parameters, and view the result as colored groups.

## Key Features

- loading graphs from `.csrrg` files;
- visualizing graphs stored as `.txt` text files;
- converting binary `.bin` results to a text format;
- partitioning a graph into a selected number of groups;
- coloring graph nodes by group;
- scrolling and zooming the graph view with the mouse wheel;
- calculating the ratio of removed connections after partitioning.

## Project Structure

```text
Graph-Visualizer/
├── data/
│   ├── Divide/       # sample data for graph partitioning
│   └── Visualise/    # sample data for graph visualization
└── src/              # application source code
```

Main classes:

- `Main` - application entry point;
- `VisualiseGraph` - creates the main window and handles user actions;
- `ParseData` - reads graph data and converts binary files;
- `GraphData` - stores the graph and performs grouping operations;
- `GraphPanel` - renders the graph;
- `SpectralData`, `Matrix`, `Vector` - handle spectral analysis calculations.

## Requirements

- Java JDK 21 or newer;
- an operating system with desktop window support.

The project does not require any external libraries.

## Running the Application

Compile the project:

```bash
javac -d out src/*.java
```

Run the application:

```bash
java -cp out Main
```

After startup, the application window with the control panel will appear.

## Usage

1. Choose a graph file using the `Wybierz plik...` button.
2. Set `Margines` to a value between `0.0` and `1.0`.
3. Enter the number of groups into which the graph should be partitioned.
4. Click `RUN` to analyze and display the graph.

The `Podziel i zwizualizuj graf` mode lets you switch between processing a `.csrrg` file and visualizing an already partitioned graph from a text or binary file.

## Supported Formats

- `.csrrg` - input format used for graph partitioning;
- `.txt` - text representation of a graph or a partitioning result;
- `.bin` - binary representation of a partitioning result, converted to `output.txt` before visualization.

Sample files are available in the `data/Divide` and `data/Visualise` directories.

## Cleaning Build Files

The `.class` files and the `out/` directory are ignored by Git. To remove local build output, delete the directory:

```bash
rm -rf out
```

## Authors

An educational project for visualizing graphs and experimenting with graph partitioning.
