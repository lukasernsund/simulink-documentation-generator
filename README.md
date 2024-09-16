# Automatic Simulink Documentation Generator

This MATLAB script automatically generates comprehensive PDF documentation for Simulink models, using the Simulink Report Generator package API. The documentation is generated using a hierarchical top-down approach, starting from the main model and recursively exploring referenced models and subsystems.

## Features

- Generates documentation from any Simulink model
- Supports subsystems, referenced models, and Stateflow diagrams

## Content
- Title page
- Table of contents
- Model documentation (hierarchical structure)
  - Main model
    - Model name and description
    - Interactive model diagram
    - Inputs/outputs/constants table
  - Subsystems (for each subsystem, recursively)
    - Subsystem name and description
    - Interactive subsystem diagram
    - Inputs/outputs/constants table
  - Referenced models (for each referenced model, recursively)
    - Referenced model name and description
    - Interactive model diagram
    - Inputs/outputs/constants table
    - Its own subsystems and referenced models (following the same structure)
  - Stateflow documentation (for each Stateflow chart)
    - Chart name
    - States
      - State names and descriptions
      - Entry, during, and exit actions
    - Transitions
      - Transition conditions and actions

## Prerequisites

- MATLAB
- Simulink
- Simulink Report Generator toolbox

## Usage

1. Place the script in your MATLAB working directory or add it to your MATLAB path.
2. Open the script in MATLAB.
3. Set the following variables at the beginning of the script:
   ```matlab
   modelName = 'YourModelNameHere';  % Replace with your Simulink model name
   ```
   ```matlab
   version = '';  % Optional: Set the version number (e.g., '1.0') or leave empty
   ```
   ```matlab
   outputFolderPath = '';  % Optional: Set the output folder path or leave empty for default
   ```
5. Run the script in MATLAB.
6. The script will generate a PDF report in the specified output folder (or in a 'Documentation' folder in the current directory if not specified).

## Configuration Options

- `modelName`: (Required) The name of your Simulink model.
- `version`: (Optional) The version number of your model. If provided, it will appear in the documentation title.
- `outputFolderPath`: (Optional) The folder where you want to save the documentation. If not provided, it defaults to a 'Documentation' folder in the current working directory.

## Output

The script generates a PDF file named [modelName].pdf in the specified output folder. For example, if your model is named "MySimulinkModel", the output file will be "MySimulinkModel.pdf". This file contains the complete documentation of your Simulink model, structured in a hierarchical manner reflecting the model's architecture.

## Customization

You can modify the script to adjust the report structure, content, or styling based on your specific needs. The main functions that you might want to customize are:

- `generateReport()`: Overall report generation process
- `exploreModel()`: How the model hierarchy is explored
- `createTables()`: How input, output, and constant tables are created
- `exploreChart()`: How Stateflow charts are documented

## Troubleshooting

If you encounter any issues:

1. Ensure all prerequisites are installed.
2. Check that the model name is correct and the model is in your MATLAB path.
3. Verify that you have write permissions for the output folder.

If problems persist, check the error message printed in the MATLAB console for more details.

## Contributing

Contributions to improve the script or extend its functionality are welcome. Please feel free to submit issues or pull requests.

This project is licensed under the MIT License:

MIT License

Copyright (c) [2024] [Lukas Mojas Ernsund]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

## Acknowledgments

This script utilizes the Simulink Report Generator package API provided by MathWorks. A significant portion of this code is derived from or inspired by the examples and documentation provided in the Simulink Report Generator documentation.

For more information about Simulink Report Generator and its capabilities, please refer to the official documentation:

[Simulink Report Generator](https://se.mathworks.com/products/simulink-report-generator.html)
