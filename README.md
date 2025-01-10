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

- Load and Display Image:
     - There are several ways to upload the files to google colab. We can do it through google colab files, conecting the notebook to google drive folder, or calling the files from repository in GitHub.
- Display the image in a separate window.
     - To display several pictures at the same time for better analysis we can use matplotlib to plot them.
- Convert the image to grayscale to simplify processing.
     - To convert image to grayscale we can use cv2 library
- Edge Detection to highlight walls and boundaries.
     - To detect edges Canny and Scharr methods were used
- Contour Detection to identify closed areas (like rooms).
     - Several trials were maid to detect accurate amount of contours. The problem faced: it was doubling the amount of contours
     - How it was solved:
          - Why x*2 amount of contours were appearing previously?
               - Canny Edge Detection: This detects all edges in the image, including both the inner and outer edges of the rectangle.
               - Contours Detection: The cv2.findContours function sees each edge separately because it traces boundaries around both the inner and outer edges.
               - Result: Since there are two loops (one for the outer rectangle and one for the inner hollow rectangle) and each loop has two sides (inner and outer edges), the function detects 4 separate contours.
         - Why x amount of contours?
              - Thresholding was included: Converts the grayscale image into a binary image (black and white). The black areas are treated as the background, and the white areas represent the shape.
              - Here, the entire rectangle (both outer and inner parts) is treated as a single filled shape with two boundaries: outer and inner.
              - Contours Detection: The cv2.findContours function detects only the outer boundary of the shape and the hole inside it.
              - Result:The algorithm detects 2 contours: one for the outer boundary of the rectangle and one for the inner hollow space.
- Calculate Room Areas.
     - the second exercise with [4 rooms](blueprints/simple_square.png) was made in a way that all contours (except the lat enternal one) could be detected and the area of them could be calculated. This approach can work with different blueprint images. If you are working with your own bluepriunt, the only cell you need to change there is: room_labels = ["Toilet", "Bedroom", "Office", "Livingroom"]

#### Tools & Libraries
- GoogleCollab
- Python
- cv2 library
- matplotlib.pyplot library

#### How to Run

1. Open Google Colab Notebook [Blueprint Analyzer](Blueprint_Analyzer_Aleksandra_Kraeva.ipynb).
2. Make a copy of it and save it to you drive/github.
3. Upload images: 1st exercise:[simple_square](blueprints/simple_square.png) from [blueprints](blueprints/) folder
4. Work with Google Colab cell-by-cell to analyze the process and see the result
5. 2nd exercise: [four_squares](blueprints/four_squares.png) from [blueprints](blueprints/) folder
6. Work with Google Colab cell-by-cell to analyze the process and see the result
7. If you are workig with your own blueprint, you should change names of rooms in [four_squares](blueprints/four_squares.png) excercise in the cell: room_labels = ["Toilet", "Bedroom", "Office", "Livingroom"]
8. Enjoy!



## 2. [Building Material Cost Estimator](Building_Material_Cost_Estimator_Aleksandra_Kraeva.ipynb)

This project serves as an opportunity for students with architectural background to learn Python. It assumes that the student is an absolute beginner and is used to teach the fundamental conecpts of Python through a hands on approach.

#### Learning Objectives

- Learn basic Python syntax.
- Understand variables and data types.
- Work with conditional statements.
- Use loops for repetitive tasks (if expanded).
- Create and use functions.
- Work with lists, tuples, and dictionaries.
- Learn basic file handling operations.

#### Features
- Calculate Room Area
- Users input the length and width of the room.
- The program calculates the total area in square feet.
- Choose Material
- Users choose a material from predefined options.
- Each material has a cost per square foot.
- Calculate Total Cost
- Save Project Details to .csv file

#### Tools & Libraries
- GoogleColab
- Python
- csv library
- matplotlib.pyplot library

#### How to Run
1. Open Google Collab Notebook [Building Material Cost Estimator](Building_Material_Cost_Estimator_Aleksandra_Kraeva.ipynb)
2. Run the Notebook cell-by-cell

#### How to Use
1. Run all the cells icluding the last one with main():
2. Choose a Surface:
   - Select the surface type by entering the corresponding number from the displayed options.
3. Enter Dimensions:
   - Provide the necessary dimensions for the selected surface.
4. Select Material:
   - Choose a material from the list and confirm your choice.
5. View Results:
   - The program will display the surface area and total cost based on the chosen material.
6. Save or Add Another Surface:
   - Optionally save your project to a CSV file or add another surface to calculate.
7. Export to CSV:
   - Save all project details to a CSV file by selecting the option at the end.
  
#### Future Improvements
- Add visualization of cost breakdown using charts.
- Allow users to input custom materials and costs.
- Implement budget management and material waste calculations.
- Add functionality to handle imperial units.


