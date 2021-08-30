#  UFOs
## Overview of Project
> Dana’s webpage and dynamic table are working as intended, but she’d like to provide a more in-depth analysis of UFO sightings by allowing users to filter for multiple criteria
 at the same time. In addition to the date, we will add table filters for the city, state, country, and shape. 

1. ***Deliverable 1***: Filter UFO sightings on multiple criteria
2. ***Deliverable 2***: A written report on the UFO analysis. 

## Resources:


* Data Tools: ECMAScript, JavaScript, Jupyter Notebook, Python and MongoDB
* Software: ES6+, ECMAScript, MongoDB, Python 3.8.3, Visual Studio Code 1.50.0

 


# Deliverable 1: 
 
## Filter UFO sightings on multiple criteria
### Deliverable Requirements:
Using JavaScript and HTML, we will modify the code in your `index.html` file to create more table filters. In addition to the date filter you created in this module, we will add filters
 for the city, state, country, and shape, as shown in the following image:

![html_page1.PNG](https://github.com/Praveeja-Sasidharan-Suni/UFOs/blob/main/resources/html_page1.PNG?raw=true)

![html_page2.PNG](https://github.com/Praveeja-Sasidharan-Suni/UFOs/blob/main/resources/html_page2.PNG?raw=true)

Using JavaScript, we will replace the handleClick() function in our app.js file with a new function that saves the element, value, and id of the filter that was changed. 
Then, we will create a new function to loop through the dataset and keep only the results that match the search criteria. 
The webpage will be updated with the search criteria after pressing "Enter".


1. The list element that creates the button is removed, and there are five list elements for filtering in the `index.html` file. 
2. The event listener is modified to detect changes to each filter in the `app.js` file.
3. ​The `updateFilters()` function saves the element, value, and the id of the filter that was changed.
4. The filterTable() function loops through all of the filters and keeps any data that matches the filter values.
5. The webpage filters the table correctly based on user input.

 
### Results with detail analysis:

1. **The list element that creates the button is removed, and there are five list elements for filtering in the `index.html` file.**


> Image with `JavaScript` & `HTML` Code below.

**Code and Image**


                    

![htmlcode_filters.PNG](https://github.com/Praveeja-Sasidharan-Suni/UFOs/blob/main/resources/htmlcode_filters.PNG?raw=true)

![html_page2.PNG](https://github.com/Praveeja-Sasidharan-Suni/UFOs/blob/main/resources/html_page2.PNG?raw=true)

2. **The event listener is modified to detect changes to each filter in the `app.js` file.**


> Image with `JavaScript` & `HTML` Code below.

**Code and Image**


````java
// 1. Create a variable to keep track of all the filters as an object.
var filters = {};

// 3. Use this function to update the filters. 
function updateFilters() {

    // 4a. Save the element that was changed as a variable.
    let inputElement = d3.select(this);
````

![filters.PNG](https://github.com/Praveeja-Sasidharan-Suni/UFOs/blob/main/resources/filters.PNG?raw=true)



3. ​**The `updateFilters()` function saves the element, value, and the id of the filter that was changed.**


> Image with `JavaScript` & `HTML` Code below.

**Code and Image**


````java
function updateFilters() {

    // 4a. Save the element that was changed as a variable.
    let inputElement = d3.select(this);

    // 4b. Save the value that was changed as a variable.
    let inputValue = inputElement.property("value");

    // 4c. Save the id of the filter that was changed as a variable.
    let inputID = inputElement.attr("id");
````

![updateFilters.PNG](https://github.com/Praveeja-Sasidharan-Suni/UFOs/blob/main/resources/updateFilters.PNG?raw=true)




4. **The webpage filters the table correctly based on user input.**


> Image with `JavaScript` & `HTML` Code below.

**Code and Image**


````java
  // 7. Use this function to filter the table when data is entered.
  function filterTable() {
  
    // 8. Set the filtered data to the tableData.
    let filteredData = tableData;
  
    // 9. Loop through all of the filters and keep any data that
    // matches the filter values
    Object.entries(obj).forEach(([fkey, fval]) =>{
        
      filteredData = filteredData.filter((row) => row[fkey] === fval)
          

  });  
  
    // 10. Finally, rebuild the table using the filtered data
    buildTable(filteredData); 
  }
````

![filterTable.PNG](https://github.com/Praveeja-Sasidharan-Suni/UFOs/blob/main/resources/filterTable.PNG?raw=true)


# Deliverable 2: 

## A written report on the UFO analysis

When the site visitor first lands on the homepage it appears like this and contains the full list of available UFO sightings in the table. 

![html_page1.PNG](https://github.com/Praveeja-Sasidharan-Suni/UFOs/blob/main/resources/html_page1.PNG?raw=true)

![html_page2.PNG](https://github.com/Praveeja-Sasidharan-Suni/UFOs/blob/main/resources/html_page2.PNG?raw=true)

### Date Search
The user can filter the search criteria by inputting the desired date. The screenshot below shows the returned results for when 1/4/2010 is searched.

![date_img.PNG](https://github.com/Praveeja-Sasidharan-Suni/UFOs/blob/main/resources/date_img.PNG?raw=true)


### City Search
The user can filter the search criteria by inputting the desired city. The screenshot below shows the returned results for when the city Maricopa is searched.

![city_image.PNG](https://github.com/Praveeja-Sasidharan-Suni/UFOs/blob/main/resources/city_image.PNG?raw=true)


### State Search
The user can filter the search criteria by inputting the desired State. The screenshot below shows the search results for the state of Arizona.

![state_img.PNG](https://github.com/Praveeja-Sasidharan-Suni/UFOs/blob/main/resources/state_img.PNG?raw=true)


### Country Search
The user can filter the search criteria by inputting the desired Country. Below is the screenshot when the US is input in the search field. 

![country_img.PNG](https://github.com/Praveeja-Sasidharan-Suni/UFOs/blob/main/resources/country_img.PNG?raw=true)

### Shape Search
The user can filter the search criteria by inputting the desired shape. The search below is the results for fireball.

![shape_img.PNG](https://github.com/Praveeja-Sasidharan-Suni/UFOs/blob/main/resources/shape_img.PNG?raw=true)

## Summary
~ A drawback of this webpage design is that the user wouldn't know all the avaialbe search options for filtering.  For example to pick a shape, the user would have to search through the tab
le to see what are all the options avaialbe to filter through.It's not an exactly effeciant way to research the website. 

~One way to fix this would be to include a drop-down lists including all filter options in place of the input fields.
Each list would need to update after a parameter is selected in any filter.

~Another recommendation would be to also include a clear filter button to reset the search table.  This can be the last item in the filter search feild. 


