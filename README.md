# Lego Set Explorer Challenge
Maven Analytics guided projects

## Here’s a glimpse into what I worked on:

https://app.powerbi.com/view?r=eyJrIjoiYTIxNzg2MmQtZjM2Mi00MGQ4LTgwMWItY2JkOWZkZTliZDQzIiwidCI6IjNkZmU5YWI2LTgxYmYtNDkxYy1iNjcwLTAxYzgyNGEwOWUxOSJ9

📊 **Load and prepare the data:**

Loaded and cleaned the Lego dataset to ensure accuracy and usability.
Created calculated columns and measures to enable detailed analysis.

Tasks:
- Connected to the lego_sets CSV file via SQL Server. In Power Query, removed minifigs, bricksetURL and thumbnailURL fields, check data types for accuracy and filter out records without price, age, pieces or image URL values.
- Created conditional columns for Age Range (“Over 18”, “10 to 17”, “5 to 9”, “1 to 4”) and Price Range (>$500 = “$$$$$”, >$100 = “$$$$”, >$50 = “$$$”, >$25 = “$$”, otherwise “$”).
- Added measures to calculate the number of distinct sets (Total Sets) and theme groups (Total Groups), as well as the average age (Avg. Age), price (Avg. Price) and pieces (Avg. Pieces).
```
Total Sets = DISTINCTCOUNT('lego lego_sets'[set_id])
Total Groups = DISTINCTCOUNT('lego lego_sets'[themeGroup])
Avg. Age = AVERAGE('lego lego_sets'[age])
Avg. Pieces = AVERAGE('lego lego_sets'[pieces])
Avg. Price = AVERAGE('lego lego_sets'[price])
```

🔧 **Report design:** 

Designed a visually appealing and interactive layout with key metrics, slicers, and dynamic tables.
Added a dedicated section for detailed Lego set information and placeholders for multiple selections.

Tasks:
- Taked a moment to sketch potential report layouts, based on the project brief and objectives
- Inserted card visuals to show Total Sets, Avg. Pieces and Avg. Price
- Added slicers to filter based on the theme group, theme and age range
- Inserted a table to show name, set_id, theme, Age Range, Avg. Pieces, Avg. Price and Price Range
- Added a report section to show details for a selected set, including the name, image, price, year, pieces and age. Showed placeholder values if multiple sets are selected:
```
Selected Set = IF(HASONEVALUE('lego lego_sets'[name]), MAX('lego lego_sets'[name]), "Select a Set")
```
- Edited visual interactions to prevent table selections from filtering the top-level cards

🔄 **Interactivity enhancements:**

Introduced dynamic filters, hover-enabled tooltips, and reset buttons with custom actions.
Created a decomposition tree visual for deeper analysis and seamless navigation between pages.

Tasks:
- Created a numeric range parameter (Max Price) ranging from 0-850 and incrementing by 5. Add a slicer to the page, and a measure that allows you to filter the table based on the maximum price selected
- Enabled tooltips on the table to display the image of each LEGO set on hover
- Used bookmarks and button actions to allow users to reset all filters on the page
- Created a new report page with a decomposition tree visual to analyze Total Sets by category, theme group, theme and name, and add buttons to navigate between pages

✨ **What’s new for me:**

This project pushed me to explore and apply new skills, including creating dynamic filters, designing detailed set views, and incorporating advanced interactivity. The combination of creativity, problem-solving, and data insights made this an unforgettable experience.


