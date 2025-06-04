# 📌Creating Line Plots of GDP Data

In this Python program you'll use the Pygal library to visualize CSV data processed with dictionaries. this combine data analysis and plotting, helping you learn how to integrate third-party packages into your Python scripts.

-------

# Project description

The project consists of multiple problems. Each problem will utilize functions you wrote for the previous problems. You can also download all of the files used when testing your code as a zip file.

### Working with the CSV file
As the format of the CSV file that stores the GDP data could change (or you could acquire data from somewhere else), the functions that operate directly on the data will all take a "gdpinfo" dictionary that provides information about the file. That way, you do not need to use constants within your code to access the CSV file and their columns. If the years for which there is data within the file change, for instance, you can simply update the gdpinfo structure appropriately and all of your code will continue to work. Furthermore, if you have a CSV file that uses different field separators, you can tailor the gdpinfo structure appropriately to deal with that without needing to change any of your other code. The gdpinfo dictionary contains the following keys, all of which are strings (the use of these keys will become apparent as you work on the project, you may want to refer back to this information as you work on the different parts of the project):

🔹"gdpfile": the name of the CSV file that contains GDP data.
🔹"separator": the delimiter character used in the CSV file.
🔹"quote": the quote character used in the CSV file.
🔹"min_year": the oldest year for which there is data in the CSV file.
🔹"max_year": the most recent year for which there is data in the CSV file.
🔹"country_name": the name of the column header for the country names.
🔹"country_code": the name of the column header for the country codes.

### Problem 1: Read a CSV file as a nested dictionary
First, you will write a function called read_csv_as_nested_dict that takes the name of a CSV file and returns the data within the file as a dictionary of dictionaries. Each key-value pair in the outer dictionary corresponds to a row in the CSV file. The keys in that dictionary are the values of a header column in the table. The function takes the name of that header column as the input keyfield. If a key appears multiple times in column corresponding to keyfield, the last row containing the key is used to create the dictionary used as the corresponding value.The inner dictionaries within the outer dictionary map the field names to the column values for that row. As CSV files can use different separator characters and quote characters, this function takes those characters as input and uses them to properly parse the CSV file. Note that the key-value pair for keyfield should be in the inner dictionaries, even though its value is used as the key in the outer dictionary.

### Problem 2: Create a list of GDP data suitable for XY plotting
Next, you will write a function called build_plot_values that takes a gdpinfo, a gdpinfo dictionary describing the CSV file that contains the GDP data, and gdpdata, a dictionary that contains a single country's GDP data mapped by year and returns a list of tuples suitable for XY plotting. The gdpdata dictionary maps years (which are strings) to GDP data for that year (also stored as strings). The tuples in the returned plot values list should be of the form (year, gdp) where 
year is an integer between the minimum and maximum years (inclusive) specified in gdpinfo and gdp is a float corresponding  to the GDP for the given year.

### Problem 3: Create a dictionary mapping countries to XY plot lists
Third, you will write a function called build_plot_dict that takes gdpinfo, a gdpinfo dictionary describing the CSV file that contains the GDP data, and country_list, a list of strings which are country names, and returns a dictionary that maps all of the country names within country_list to plot value lists of GDP data for that country.

### Problem 4: Create an SVG image of XY plots for yearly GDP for a specified list of countries
Finally, you will write a function called render_xy_plot that utilizes the first three functions you wrote to create an XY plot of the World Bank GDP data for a specified list of countries.  This function will take gdpinfo, a gdpinfo dictionary describing the CSV file that contains the GDP data, country_list, a list of strings that name the countries that should be in the output plot, and plot_file, a string that names the output file the function should create. The output plot should be an SVG image of the resulting XY plot.  To create create this plot,  you should review Pygal's documentation on XY plots and outputting the results of the plot as an image file.

# Key Features (Short Summary)
1. gdpinfo dictionary: Stores CSV structure info (file name, separator, quote, year range, column names).
2. read_csv_as_nested_dict: Reads CSV into a nested dictionary using a specified key column.
3. build_plot_values: Converts a country's GDP data into a list of (year, gdp) tuples for plotting.
4. build_plot_dict: Maps country names to their respective GDP XY data lists.
5. render_xy_plot: Uses Pygal to generate and save an SVG XY plot of GDP for selected countries.
6. Modular design: Each function supports reusable and flexible data analysis and visualization.


------


