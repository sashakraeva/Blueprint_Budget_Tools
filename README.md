# Blueprint-Budget-Tools

A Python-based repository for architecture and construction students to explore image processing and cost estimation concepts through two focused exercises and a combined app.

## Contents

1. **[Blueprint Analyzer](Blueprint_Analyzer_Aleksandra_Kraeva.ipynb)**  
   Analyze blueprint images using OpenCV to detect walls, room boundaries, and calculate room areas.

2. **[Flooring Cost Estimator](flooring_cost_estimator/)**  
   Calculate flooring costs for rooms based on dimensions and material choices. A beginner-friendly introduction to Python programming concepts.

3. **[Blueprint & Budget Builder](combined_app/)**  
   A combined application integrating blueprint analysis with material cost estimation, allowing users to seamlessly calculate construction costs from blueprint images.

---

## **1. [Blueprint Analyzer](Blueprint_Analyzer_Aleksandra_Kraeva.ipynb)**

This project introduces architecture students to the basics of OpenCV through a practical exercise in image processing. The program processes blueprint images, highlights walls and room boundaries, and calculates areas of detected rooms. It’s designed for beginners to learn Python and OpenCV while applying programming skills to an architecture-related task.

#### Learning Objectives

- Learn the basics of OpenCV for image processing.
- Understand how to load, display, and manipulate images in Python.
- Use edge detection and contour analysis to extract shapes from images.
- Perform calculations like area measurement based on image data.

#### Features

- Load and Display Blueprint
- Load a blueprint image from a file.
- Display the image in a separate window.
- Convert the image to grayscale to simplify processing.
- Edge Detection to highlight walls and boundaries.
- Contour Detection to identify closed areas (like rooms).
- Calculate Room Areas

#### How to Run

1. Open Google Colab Notebook [Blueprint Analyzer](Blueprint_Analyzer_Aleksandra_Kraeva.ipynb).
2. Make a copy of it and save it to you drive/github.
3. Upload images: 1st exercise: [four_squares](four_squares.png) 2nd exercise: [simple_square](simple_square.png) from [blueprints](blueprints/) folder
4. Save the Python script as blueprint_analyzer.py.
5. Run the program from the terminal:

python blueprint_analyzer.py
Provide the path to a sample blueprint image (e.g., a JPEG or PNG file) when prompted.

Example Workflow

Enter the path to the blueprint image: blueprint.jpg

-- Displays the following windows --
1. Original Blueprint
2. Edges (processed image)
3. Outlined Blueprint (detected room contours)

-- Console Output --
Contour 0: Area = 1200.50 square pixels
Contour 1: Area = 800.75 square pixels
...
