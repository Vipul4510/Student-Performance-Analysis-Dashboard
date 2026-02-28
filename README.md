Student Performance Analysis Dashboard 🎓
Project Overview
This Power BI dashboard provides a deep-dive analysis of student academic performance across various engineering departments. It is designed to help educators and administrators identify trends, recognize top-performing groups, and understand the impact of socio-economic factors like parental education on student success.

✨ Key Features
Dynamic Performance Metrics: Instant visibility into Average Total Scores, Overall Pass Rates, and student counts.

Best/Worst Performing Grade: Automatically identifies which grade level is leading based on current filters.

Parental Education Impact: A specialized breakdown showing the correlation between home environment and academic results.

Departmental Filtering: Interactive slicers for Civil, Computer Science, Electrical, and Mechanical Engineering.

Advanced UI Design: Custom-sized canvas with transparent visuals to provide a clean, modern user experience.

📊 DAX Measures & Logic
To ensure the dashboard remains interactive and accurate, the following DAX logic was implemented:

1. Best Performing Grade
This measure identifies the grade with the highest average score. It is used in a "Top N" filter context to display the specific grade name dynamically.

Code snippet
Best Performing Grade = 
TOPN(
    1, 
    ALL('StudentData'[Grade]), 
    [Average Total Score], 
    DESC
)
2. Overall Pass Rate
Calculates the percentage of students who achieved a "Pass" status versus the total student population.

Code snippet
Overall Pass Rate = 
DIVIDE(
    CALCULATE(COUNTROWS('StudentData'), 'StudentData'[Result] = "Pass"),
    COUNTROWS('StudentData'),
    0
)
🛠️ Design & Technical Challenges Solved
Axis Visibility: Fixed the "Axis font reduced" error by disabling the Responsive property and adjusting the visual container size to ensure X-axis labels (Grade A-E) remained visible.

UI Transparency: Removed default white backgrounds from Card visuals to allow the custom background image to show through, creating a seamless "floating" effect.

Canvas Optimization: Switched from a standard 16:9 ratio to a Custom (1280 x 1200 px) layout to prevent overcrowding and improve readability.

Slicer Formatting: Optimized the Department slicer by adjusting Padding and Font Scaling to ensure text fits perfectly within the selection boxes.

🚀 How to Use
Download: Clone the repository and open the .pbix file in Power BI Desktop.

Filter: Use the Department slicer on the left to see how specific engineering branches are performing.

Analyze: Hover over the bar charts to see detailed tooltips regarding student distribution and result categories.


<img width="1751" height="963" alt="image" src="https://github.com/user-attachments/assets/369577c6-6115-4d86-8b28-6a89bc9d55cc" />

