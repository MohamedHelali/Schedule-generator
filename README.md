# Schedule Generator

####  Video Demo: https://youtu.be/a8f2BQu_BY4

## About the project

This project offers an interactive graphical interface enabling users to create timetables for multiple university classes.

Project structure : 
* Images (Folder)
* course.py
* database.py
* logic.py
* project.py
* settings.py
* table.py
* test_course.py
* test_databse.py
* test_project.py
* TimeTable.docx (timetable template)
* university.db (database file)

## Running the application
To run this application, just run the **project.py** file.

## Libraries
- **random**: this library servers the purpose of generating random numbers. It provides the user with different functions for generating random numbers from various distributions. [Read more](https://docs.python.org/3/library/random.html)
- **sqlite3**: this library offers a lightweight disk-based database system that operates without the need for a separate server process. it allows access to the database using a nonstandard variant of the SQL query language. [Read more](https://docs.python.org/3/library/sqlite3.html)
- **re**: this module provides regular expression matching operations akin to those found in Perl. [Read more](https://docs.python.org/3/library/re.html)
- **os**: this module provides a portable method for utilizing operating system-depending functionality. [Read more](https://docs.python.org/3/library/os.html)
- **datetime**: this module supplies classes for manipulating dates and times.[Read more](https://docs.python.org/3/library/datetime.html)
- **calendar**: this module provides various functions related to calendars, including generating calendars for a specific month or year, determining the weekday of a given date, etc. [Read more](https://docs.python.org/3/library/calendar.html)
- **python-docx**: this library is used for creating and updating Microsoft Word (.docx) files. [Read more](https://python-docx.readthedocs.io/en/latest/)
- **copy**: this module provides functions for creating **shallow** and **deep** copies of objects. Its primary perpose is to facilitate the creation of copies of mutable objects without the risk of altering the original object. [Read more](https://docs.python.org/3/library/copy.html)
- **pytest**: this framework allows users to easily write readable tests that can support complex functional testing for applications and libraries. [Read more](https://docs.pytest.org/en/8.0.x/)
- **tkinter**: this package is the standard Python interface to tck/tk GUI toolkit. [Read more](https://docs.python.org/3/library/tkinter.html)
- **customtkinter**: this Python UI\_library based on tkinter, which provides new, modern, and fully customizable widgets. [Read more](https://github.com/TomSchimansky/CustomTkinter)
- **CTkMessagebox**: this module provides a modern and fully customizable messagebox for CustomTkinter. [Read more](https://github.com/Akascape/CTkMessagebox)
- **tkcalendar**: this Python module provides the Calendar and DateEntry widgets for tkinter. [Read more](https://tkcalendar.readthedocs.io/en/stable/)
- **darkdetect**: this package enables the detection of whether the user has activated Dark Mode on their operating system. [Read more](https://pypi.org/project/darkdetect/) 

## Installing Libraries

The **requirements.txt** file  contains all the libraries used in this application.
 These libraries can be  easily installed using the following pip command:
 ``pip install -r requirements.txt``
 
## Application Information
This application was primarily inspired by the timetables provided by my university. It was designed to enable users to generate a range of unique timetable for university students based on various constraints using the **Backtracking** algorithm.

The **Backtracking** algorithm is a problem-solving algorithm that involves incrementally finding a solution by exploring different options to determine the best possible outcome.
This algorithm operates by attempting various  possibilities/options to solve the problem at hand. if a particular option does not lead to a solution, the algorithm backtracks and explores alternative options until it finds a suitable one. [Read more](https://www.geeksforgeeks.org/backtracking-algorithms/)

We selected this algorithm because it is widly employed in solving scheduling problems, thereby enabling us to create custom timetables for each class within the university.

**Timetable Layout**: The schedule for each class primarily consists of six days (Monday to Saturday) where each day is composed of six periodes of 90 min seperated by a 10 min breaks except Wednesday and Saturday which only have 4 periodes.

**Timetable Rules**: Each timetable adheres to a set of rules, if possible:

* Each class should not have the same lecture more than once a week.
* Each class should not have the same lecture multiple times on the same day.
* Classes should not have lectures scheduled during the fifth and sixth periods on Wednesdays and Saturdays.
* No class should be taught by the same professor at the same time on the same day.
* No classes should use the same classroom at the same time on the same day.
  
  ## Usage
 When executing the command  ``python project.py``, the user will be greeted with the following interface:

  **Dark mode**:
![interface-dark-mode](https://github.com/MohamedHelali/Schedule-generator/assets/155182909/68d43e9e-428e-439b-b439-582b7646d6f1)
 
**Light mode**:

![interface-light-mode](https://github.com/MohamedHelali/Schedule-generator/assets/155182909/bcb4c68b-19e2-412a-a3dd-08c7b9346310)

> [!NOTE]
> The type of interface displayed depends on whether the user's operating system has dark mode activated or not.

In the **departement** section, the user must provide a departement name to which the different classes belong.

![departement-input](https://github.com/MohamedHelali/Schedule-generator/assets/155182909/a00ae6de-0cfc-4fe4-946f-52544538e765)


> [!IMPORTANT]
> - This field must not be left empty.

In the **semester** section, the user must provide the semester value.

![semester-input](https://github.com/MohamedHelali/Schedule-generator/assets/155182909/a267fb92-2cfb-4d61-8e9c-3ae96075fdb8)


> [!IMPORTANT]
> - This field must not be left empty.

For the **Start date** and **End date** sections, the user must specify the start and end of the week for which they want to generate a timetable.

![start-end-date-input](https://github.com/MohamedHelali/Schedule-generator/assets/155182909/49b14f1c-2b02-441d-9a32-ff7bb351de63)

> [!IMPORTANT]
> When selecting the start and end dates, the user must adhere to these rules:
>  - The start day must be a Monday.
>  - The end day must be a Saturday.
>  - Both the start and end days must belong to the same week.
>  - The selected week must be the following week relative to the current day.

The user can then select the various **courses**, **professors** and **classrooms** to be used in the creation of the timetables.
 
![prof-course-classrooms-selection](https://github.com/MohamedHelali/Schedule-generator/assets/155182909/a53508bc-7548-4083-840b-2308d5d7eac3)


The application also provides the possibility of removing specific values. This can be done by clicking on the red button next to a specific value.

> [!IMPORTANT]
> - When clicking on the delete button, the value will be permanently removed from the application, thus making it non longer available for future use.

In addition to that, the user can also add news values to the application, by typing them into the input section situated bellow the scrolling list of checkboxes and pressing the add button.
 
 ![prof-course-classrooms-add-value](https://github.com/MohamedHelali/Schedule-generator/assets/155182909/0a5eb0aa-f091-4ac9-8757-cd033fcc5c29)


> [!IMPORTANT]
> - When adding a new professor name, the user must adhere to the following format: **Prof. / Dr.** (case sensitive) **Name** **Lastname**, for example: **Dr. Jhon Smith**.
>  - When adding a new classroom the user must adhere to the following format: **Bloc name**(a single character) **classroom number**, for example: **C 10**.

The user then needs to specifiy the number of classes for which they want to generate their respective timetables.

![number-of-classes-input](https://github.com/MohamedHelali/Schedule-generator/assets/155182909/022ee638-6e9c-40ff-a167-8afbafea790c)

Once all the required fields all filled, the user can click on the **Generate** button to generate the requested timetables. These tables will be stored inside a docx file.
The following image is an example of a custom timetable generated for **Class1** using the application:

![timetable-output](https://github.com/MohamedHelali/Schedule-generator/assets/155182909/0cca382e-8cba-4d50-af0a-6eaacd5a8046)
   

## Functioning
Besides the **main** function, this project is mainly composed of **8** classes, **71** functions stored in **5** separate files (excluding the pytest files).

## project.py
This file contains all the classes needed for the creation of GUI. Most of these classes are created using the **Tkinter** and **CustomTkinter** framework in an attempt to create an easy-to-use interactive graphical user interface.

The image below provides a comprehensive overview of the different classes utilised in creating the graphical user interface (GUI) for the application:
![interface_classes_names](https://github.com/MohamedHelali/Schedule-generator/assets/155182909/f3e98e9a-b69a-49f3-b3d7-c1afe39cbad0)



#### App class:
The first class in the **Project.py** file, this class survices as the base window for our GUI. This class contains the following function:
 *   **\_\_init\_\_** (**is_dark** = False, **test** = False): This constructor used to initialize a newly created **App** object.
	 * **Parameters**:  
		 * **is_dark**:  A boolean used to check if the user's operating system is using the dark theme mode.
		 * **test**: A boolean to check if the application is in test mode.

*  **create_widgets**(): this functions is used to create the various widgets needed for our user interface.
* **create_generate_frame**(row,col): This  function is used to create the generate section, which includes an input section for the number of classes and a generate button. It takes two positionals arguments represented by two integer specifying the location to place these widgets.

* **generate_timetables**(): This function is used to collect the user input from the  widgets within the application GUI and then use them to generate our timetables.
* **check_dates**(start_date_str,end_date_str): This function is used to convert both date string into datetime objects. Then, it checks whether the user has inputed a valid start and end dates needed to generate the timetables. 
This function returns a tuple containing both the start and end dates, or else it raises a **ValueError** exception.
	* **Parameters**:  
		 * **start_date_str**: A string containing the starting day of the week.
		 * **end_date_str**: A string containing the ending  day of the week.

> [!Note]
> - This function ensures that both start and end dates adhere to the following rules:
>	- The start day must be a Monday.
>   - The end day must be a Saturday.
>    - Both start and end days must belong to the same week.
>    - The selected week must be the following week relative to current day.

 #### TextInput class:
 This class is used to create the input sections within the application. This class contains the following functions:
 *   **\_\_init\_\_** (**parent**, **title**, **row**, **col**, **fg_color** = None): the constructor used to initialize a newly created **TextInput** object.
	 * **Parameters**:  
		 * **parent**: Specifies the parent widget where the frame (or any other widget) will be placed.
		 * **title**: A string containing the title to be place on top of the input widget.
		 * **row**: An integer indicating the row where to place the widget.
		 * **col**: An integer indicating the column where to place the widget.
		 * **fg_color**: A string indecating the forground color for the input section.

* **create_widgets**(): This function is used to create the various widgets required for the creation of the input section.
*  **get_content**(): This function returns a string containing the input provided by the user, or else it raises a **ValueError** if the input field is empty.

#### NbrClassesInput:
This class inheretes from the **TextInput** class and is used to create the **number of classes** input section with the only difference that it only accepts integer values. This class contains the following functions:

 *   **\_\_init\_\_** (**parent**, **title**, **row**, **col**, **fg_color** = None): This constructor is used to initialize a newly created **NbrClassesInput** object.
	 * **Parameters**:  
		 * **parent**: Specifies the parent widget where the frame (or any other widget) will be placed.
		 * **title**: A string containing the title to be place on top of the input widget.
		 * **row**: An integer indicating the row where to place the widget.
		 * **col**: An integer indicating the column where to place the widget.
		 * **fg_color**: A string indicating the forground color for the input section.

* **create_widgets**(): This function is used to create the various widgets required for the creation of the input section.
*  **get_content**(): This function returns an integer provided by the user, which specifies the number of classes for which we want to create timetables. If the input field is empty or if the input value is not numeric value, it raises a **ValueError** exception.

#### CalendarInput:
This class is used to create the drop-down calendar section used to select the start and end dates of the week. This class contains the following functions:

 *   **\_\_init\_\_** (**parent**, **title**, **row**, **col**, **fg_color** = None): the constructor used to initialize a newly created **CalendarInput** object.
	 * **Parameters**:  
		 * **parent**: Specifies the parent widget where the frame (or any other widget) will be placed.
		 * **title**: A string containing the title to be place on top of the input widget.
		 * **row**: An integer indicating the row where to place the widget.
		 * **col**: An integer indicating the column where to place the widget.

* **create_widgets**(title): This function is used to create the various widgets required for the calendar section.
	* **Parameters**:  
		 * **title**:  A string specifying the text to be placed on top of the calendar widget.
* **get_content**(): this function returns a string value containing the date selected by the user.
#### MainContent:
This class is used to create the scrolling section containing the various professors' names, courses' names and classroom' numbers. This class mainly consists of the following functions:

*   **\_\_init\_\_** (**parent**, **title**, **row**, **col**, **fg_color** = None): Constructor for initializing a new instance of MainContent.
	 * **Parameters**:  
		 * **parent**: Specifies the parent widget in which the new frame (or any other widget)  will be placed.
		 * **title**: A string that appears as a title above the input widget.
		 * **row**: An integer specifying the row position of the widget within the grid.
		 * **col**: An integer specifying the column position of the widget within the grid.
		 * **data**: A list containing the initial data for the widget (e.g., professor names).
		 * **del_func**: A callback function that executes when an item is deleted from the list (e.g., `delete_professor`).

		 * **add_func**: A callback function that executes when a new item is added to the list (e.g., `add_professor`).

* **create_widgets**(title, data, del_func, add_func) : Constructs the necessary widgets for the scrolling section.
	* **Parameters**:  
		 * **title**: The label for the scrolling section.
		 *  **data**: A list of items to be displayed within the section.
		 *  **del_func**: The callback function for item deletion.
		 * **add_func**: The callback function for adding new items.
* **load_data**(data_frame,data,del_func): Populates the scrollable widget with data.
	* Parameters:
		* **data_frame**: The frame or container holding the scrollable list.
		* **data**: A list of data items to load into the frame.
		* **del_func**: The deletion callback function for each item.

*   **get_selected_values**(): Returns a list of all selected items (via checkboxes) from the scrolling section.

> [!Note]
> Due to the limitation of the **backtracking** algorithm used by the application, users must select a minimum of 3 options in each scrolling section. This is necessary to avoid creating imposible scheduling conditions, such as attempting to assign only one professor to three different classes. Failure to adhere to this guideline may result in errors during timetable generation.

* **select_deselect_all**(): This function toggles the selection state of all checkboxes within the scrolling section. It is activated by clicking the **Select All** button, allowing the user to either select all or deselect all checkboxes simultaneously.

#### DataLineFrame:
This class is used to create individual entries within the scrolling section, each entry consisting of a **checkbox** and a **delete button**. Here are the primary functions of the DataLineFrame class:

*   **\_\_init\_\_** (**parent**, **val**, **del_func**): Initializes a new instance of the class.
	 * **Parameters**:  
		 * **parent**: specifies the parent widget that will contain this frame.
		 * **val**: A string representing the value to be desplayed by the checkbox.
		 * **del_func**: The function that is called when pressing on the delete button.

* **create_widget**(val,del_func): Creates the necessary widgets for the line in the scrolling section.
	* **Parameters:**
		* **val**: The string value displayed by the checkbox.
		*  **del_func**: The function to call to delete this specific line from the scrolling section.

* **val_status**(): Returns a tuple containing the checkbox's value and its status (checked or unchecked, represented as 1 or 0).
*  **select_val**(): Selects the checkbox within this specific line in the scrolling section.
*  **deselect_val**(): Deselects the checkbox within this specific line in the scrolling section.
* **delete_line**(func,val): Deletes a specific line from the scrolling section.
	* **Parameters:**
		* **func**: The function used to delete the line from the scrolling section.
		* **val**: The string value of the line to be deleted.

#### AddDataFrame:
This class facilitates the creation of the **Add new value** section located beneath the scrolling section of the application. It consists of the following functions:
*   **\_\_init\_\_** (parent, row, col, add_func, del_func, data_frame): Constructor for initializing a new instance of this class.
	 * **Parameters**:  
		 * **parent**: Specifies the parent widget that will contain this frame.
		 * **row**: An integer specifying the row where the widget will be placed.
		 * **col**: An integer specfying the column where the widget will be placed.
		 * **add_func**: The function to be used for adding new values to the application.
		 * **del_func**:  The function to be used for deleting specific values.
		 *  **data_frame**: The variable containing the scroll widget.

* **create_widget**(**add_func**, **del_func**, **data_frame**): Creates the necessary widgets for the "Add New Value" section.

	* **Parameters:**
		* **add_func**: The function called to add a new entry to the scrolling section.
		*  **del_func**: The function called to delete a specific entry from the scrolling section.
		* **data_frame**: The variable containing the scroll widget.

* **add_data**(**add_func**,**del_func**,**data_frame**): 
This function adds new values to the scrolling sections based on user input. It retrieves the user-provided value from an input widget and passes it to the **add_func** function (e.g., add_professor). After successfully adding the value to the application database, a new **DataLineFrame** object is created for the newly added value and added to its respective scroll widget at the end of the section. This ensures that the newly added entry is visible to the user. This function will raise a **ValueError** if an attempt is made to add an empty or whitespace-only string. 

## database.py
When designing the application, we opted for a relational database to standerdize the format used for storing the necessary data. This approach not only facilitates ease of use and maintenance but also support dynamic data loading as required by the application.

We chose **SQLite** as the **DBMS** mainly because it is serverless, requiring no configuration to operate and it is a cross-platform, capable of running on multiple operating systems such as **macOs**, **Windows**, etc.

This application utilizes a database named **university**, stored inside a file named **university.db**. This database comprises 3 tables, presented as follows:

* **professors**: This table stores the names of all professors. This table is composed of 3 columns:
	* **title**: a **TEXT** value that stores the professor's title, e.g., Prof.
	*  **first_name**: a **TEXT** value that stores the professor's first name.
	*  **last_name**: a **TEXT** value that stores the professor's last name.

* **courses** : This table is used to store the names of all courses taught at the university. it consists of single column:
	*  **name**: a **TEXT** value that stores the name of the course.
* **classroom**: This table contains information about all the classrooms within the univsersity. This table includes the following columns:
	* **bloc**: a **TEXT** value that indicates the block to which a classroom belongs.
	* **room**: a **INTEGER** value that specifies the room number. 
   
This file contains various functions that allows the application to add, delete, or retrieve data from the database efficiently. These functions are presented as follows:
### General Functions 

* **check_database**(): Checks if `university.db` database exists in the project directory. if it does not exist, it creates the database, sets up the required tables, and populates them with initial data. if the database exists, it returns True.

* **db_create_tables**(): called within the **check_database** function to create the necessary tables in the database.

### Populate Tables

* **fill_db_professors**(profnames): Populates the **professors** table with a list of professors' names.
	* **Parameters**:
		* **profnames**:  List of strings containing predefined professors' names.

* **fill_db_courses**(courses): Populates the **courses** table with a list of courses names.
	* **Parameters**:
		* **courses**: List of strings containing  predefined courses' names.

* **fill_db_classrooms**(): Populates the **classrooms** table with predefined classrooms data.

### Adding Data

* **add_course**(course): this function is used to add a specific course to the **courses** table. The function starts by checking whether the new value is neither an empty value or a whitespace string, if **True** the function will raise a **ValueError** informing the user that they input an invalid value, else the system will first check wether the new value already exists in the database if the condition is **True**, the function will raise **Valueerror** informing the user that the value already exists inside the database else the function will insert the new value into the **courses** database table. Once the insertion is complete the function will return **True**.
	* **Parameters**:
		* **course**: a string variable containing the new course value to be added to the database.

* **add_professor**(professor): this function is used to add a specific professor to the **professors** table. The function starts by checking whether the new value matches the predefined pattern, if **False** the function will raise a **ValueError** informing the user that they input an invalid value, else the system will first check whether the new value already exists in the database if the condition is **True**, the function will raise **Valueerror** informing the user that the value already exists inside the database else the function will insert the new value into the **professors** database table. Once the query is executed, the function will return **True**.

	* **Parameters**:
		* **professor**: a string variable containing the name of the new professor to be added to the database.

* **add_classroom**(classroom): this function is used to add a specific professor to the **classrooms** table. The function starts by checking whether the new value matches the predefined pattern, if **False** the function will raise a **ValueError** informing the user that they input an invalid value, else the system will first check whether the new value already exists in the database if the condition is **True**, the function will raise **ValueError** informing the user that the value already exists inside the database else the function will insert the new value into the **classrooms** database table. Once the query is executed, the function will return **True**.

	* **Parameters**:
		* **classroom**: a string variable containing the new classroom to be added to the database.

### Deleting Data

* **delete_course**(course): This function removes a specific course from the **courses** table. It first validates that the input is not empty or only whitespace. If the input is invalid, a **ValueError** is raised, indicating an invalid input. If valid, the function checks if the course exists in the database:
	-   If it exists, it deletes the course and returns **True**.
	-   If it does not exist, it raises a **ValueError** indicating that the course was not found in the database.

	* **Parameters**:
		* **course**: A string representing the name of the course to be deleted from the **courses** table.

* **delete_professor**(prof): This function deletes a specific professor from the **professors** table. Initially, it checks if the input matches a predefined validation pattern:

	-   If the input is invalid, it raises a **ValueError** indicating an invalid input.
	-   If valid, it verifies whether the professor exists in the database:
	    -   If the professor exists, the function deletes the professor's entry and returns **True**.
	    -   If not, it raises a **ValueError** indicating that the professor was not found.

	* **Parameters**:
		* **prof**: A string representing the name of the professor to be deleted from the **professors** table.
		* 
* **delete_classroom**(classroom): This function removes a specific classroom from the **classrooms** table. It begins by validating the input against a predefined pattern:

	-   If the input fails validation, a **ValueError** is raised, indicating an invalid input.
	-   If the input is valid, the function checks if the classroom exists in the database:
	    -   If the classroom is found, it is deleted from the table, and the function returns **True**.
	    -   If not found, a **ValueError** is raised indicating that the classroom does not exist.

	* **Parameters**:
		* **classroom**: A string representing the details of the classroom to be deleted from the **classrooms** table (ideally, it should be structured to include both bloc and room information. e.g., **C 10**).

### Displaying Data

* **display_professors_table**(): This function outputs the values stored within the **professors** table to the shell.

* **display_courses_table**(): This function outputs the values stored within the **courses** table to the shell.

* **display_classrooms_table**(): This function outputs the values stored within the **classrooms** table to the shell. 

### Retrieving Data

* **get_professors**(): Returns a list of all professors' names from the database.
* **get_courses**(): Returns a list of all courses' names from the database.
* **get_classrooms**(): Returns a list of all classrooms from the database.

## course.py
This custom class serves as a repository for different courses necessary to populate our future timetables. Each instance of the **Course** object represents a slot in our timetable and encapsulates all the necessary information for scheduling a particular course. 

During the application design phase, we determined that a **Course** object must include the following details:
* The complete name of the course.
*  The full name of the professor assigned to teach the course.
* The classroom number.
* The **Course** object also includes the type of course, which can currently only be one of the following:
	* **C**: This designation denotes a lecture (cours in french), where the professor presents material to a large group of students. The primary focus is on delivering theoretical knowledge to students.
	* **TD**: Translated as "directed work" (Travaux dirigés in french), these sessions are more interactive and involve smaller groups of people compared to regular lectures ( **C** type). The main objective of the **TD** session is to help the students  deepen their understanding of materials covered in lectures ( **C** type) through exercises, discussions and practical applications of various concepts.
	* **TP**: These sessions, othen transalated to **practical sessions** or **lab sessions** (Travaux pratiques in french), Typically involve experiments in a lab, computer programming, or any other activity that requires practicing in a real or simulated environment. They are crucial in scientific and technical disciplines.
	* **CI**: This refers to an integrated course (Cours intégré in french), which is a special type of courses that combines elements of **lectures**, **TDs** and **TPs** courses. This session is designed to help students integrate and apply the knowledge gained from regular lectures.
* Color of the course, which service as a visual cue in order to help students better differentiate between the various courses types.

> [!NOTE]
> In short:
>  **C** courses typically involve passive learning.
>   **TD** courses emphasize active learning and problem-solving.
>  **TP** courses focus on practical application.
>  **CP** aims to integrate all the aforementioned approches in one comprehensive learning experience.   

The **Course** class is mainly composed of the following functions:

* **\_\_init\_\_**(course="",prof="",classroom="",type=""): Constructor for initializing a  **Course** object.
	* **Parameters**:
		* **course**: A string containing the full course name.
		* **prof**: A string containing the full professor name.
		* **classroom**: A string containing the classroom reference.
		* **type**: A string containing the type of the course.

* **course**(): Getter the course property.
* **course**(course): Setter for the course property. Raises a **ValueError** exception if input is empty or consists of only whitespaces.
	* **Parameters**:
		* **course**: A string containing the course name.

* **prof**(): Getter for the prof property.

* **prof**(professor): setter for the prof property. Raises a **ValueError** exception if input is empty or consists of only whitespaces.
	* **Parameters**:
		* **professor**: A string containing the professor name.

* **classroom**(): Getter for the classroom property.

* **classroom**(classroom): Setter for the course property. Raises a **ValueError** if input is empty or consists of only whitespaces.
	* **Parameters**:
		* **classroom**: A string containing the classroom reference.

* **type**(): Getter for the type property.

* **type**(type): Setter for the course property. Raises a **ValueError** if input is not one of the predefined types.
	* **Parameters**:
		* **type**: a string containing the course type.

* **color**(): Getter for the color property.

* **color**(color): Setter for the color property. Raises a **ValueError** if input is input is empty or consists of only whitespaces.
	* **Parameters**:
		* **color**: A string containing the cell color.

* **set_color**: Set the course cell color based on the course type.

* **\_\_eq\_\_**(other): Overrides the default behavior for the equality operator  to provide a custom implementation of equality checking. This function compares two **Course** objects by checking their course, prof, classroom and type properties. It returns **True** if both objects are equal, otherwise **False**.

	* **Parameters**:
		* **other**: A **Course** object.

* **\_\_str\_\_**: Formats the object's properties into a readable string.

 
## table.py

To generate our timetables, we have chosen to use the **python-docx** library. This library facilitates the reading, creating and updating of Microsoft Word 2007+ docx files.
Essentially, the system takes a template docx file and generates a new docx file containing the updated timetables based on the user input.

To generate our timetables, we opted to use the following template:

![timetable-template](https://github.com/MohamedHelali/Schedule-generator/assets/155182909/f7a0268d-a3d7-4c11-bb58-671c2702a426)

This template consists of two main sections:
* **The header section**: located at the top of the template, this section contains general informations such as **the departement name**,**class number**, **semester **,etc.
* **The table section**: This section comprises a single large table where the system stores various lectures.

In this context, the **table.py** contains all the functions necessary for generating our docx timetable file. These functions are outlined below:

* **get_template**(template_name): This function loads the template docx file required for generate the timetables. It returns a **Document** object from the loaded docx file or raises a **ValueError** exception if the file can not be loaded.
	* **Parameters**:
		* **template_name**: a string containing the name of the docx template file.

* **generate_tables_template**(template_name,n,departement_name): This function's objective is to create a new docx file containing  **n** empty timetables based on the provided **template file**. It begins by creating a new empty docx file. Then, it adjusts various document properties such as  **page dimensions**,  **margins**, **font** and **font size**,etc to fit the timetable. Subsequently, the function generates **n** new empty tables based on the template table and inserts them into the newly created file. Finally, it returns a string containing the name of the newly generated docx file containing the **n** timetables.
	* **Parameters**:
		* **template_name**: A string value containing the name of the timetable template file.
		* **n**: An integer specifying the number of timetables to generate.
		* **departement_name**: A string containing the name of the university departement for which the timetables are being generated. this paramter is required for naming the new docx generated by this function.

* **fill_tables**(matrix,doc,departement_name,semester_name,start_date,end_date): This functions is used to populate the empty tables inside the newly generated docx file. It utilizes the data stored within the **matrix** variable, which is an empty 3D matrix representing the structure of our timetable. Each layer within the 3D matrix is a 2D matrix representing a specific timetable. These timetables consist of 6 columns (representing days of the week) and 6 rows (representing class sessions, e.g., 8:00 AM to 9:30 AM). Each cell of the 2D matrix contains a **Course** object ,which is a custom class designed to store data related to specific lectures or courses.
	* **Parametes**:
		* **matrix**: A list variable containing one or more timetables.
		* **doc**: A string containing the name of the docx file with empty timetables.
		*  **departement_name**: A string containing the university departement name for which the timetables are being generated.
		*  **Semester_name**: A string containing the sepecific semester to the generated timetables belong.
		* **start_date**: A datetime variable containing the start day of the week for which we want to generate a timetable.
		*  **end_date**: A datetime variable containing the end day of the week for which want to generate a timetable.

*  **fill_header**(table,group,departement_name,semester_name,start_date,end_date): This function is responsible for populating the headers of each timetable inside the docx file. 
	* **Parameters**:
		* **table**: The sepcific header section to be filled inside the docx file.
		* **group**: An integer representing the number of a specific class.
		* **departement_name**: A string containing the university departement name for which the timetables are being generated.
		* **semester_name**: A string containing the sepecific semester to which the generated timetables belong.
		* **start_date**: A datetime variable containing the start day of the week for which we want to generate a timetable.
		* **end_date**: A datetime variable containing the end day of the week for which want to generate a timetable.

* **append_text_to_header**(cell,text,bold=False): This function inserts a specific text value inside a particular cell in the header section of the timetable.
	* **Parameters**:
		* **cell**: i An nteger containing the index of the header cell where the text will be inserted.
		* **text**: A string containing the text to be inserted into the header cell.
		* **bold**: A boolean value that determines whether the font weight should be set to bold.

* **fill_timetable**(matrix,table,group): this function used to populate the table sectioons of timetable inside the docx file. 
	* **Parameters**:
		* **matrix**: An empty 3D matrix containing the structure of our timetable.
		* **table**:  The sepcific table section to be filled inside the docx file.
		* **group**: An integer representing the number of a specific class.

* **append_text_to_cell**(cell,text,font_size,color): this function is used to insert specific text value into a particular cell in the table section of the timetable. 
	* **Parameters**:
		* **cell**: An integer containing the index of the cell within the table section where the specifc text will be inserted.
		* **text**: A string containing the text to be inserted into the cell.
		* **font_size**: An integer indicating the size of the font used inside the cell.
		* **color**: A tuple containing the RGB color value for the text inside the cell.

 * **set_cell_bg_color**(cell,bgcolor): this function sets the background color of the specified cell within the table section of the docx file.
	 * **cell**: integer representing the index of the cell in the table section.
	 * **bgcolor**: A string containing the hex color code for the cell's background color.

## logic.py
This file contains the primary implementation of the **Backtracking** algorithm, used for resolving various scheduling issues related to this project. It hosts the following functions:

* **create_timetable_matrix**(n): This function is used generates an empty 3D matrix where each element serves a logical representation of a timetable. These elements temporarilly store the timetables before being loaded into the output docx file. 
	* **Parameters**:
		* **n**: An integer specifying the number of empty matrix to be created.

The following image represents an empty timetable matrix.

![matrix-example](https://github.com/MohamedHelali/Schedule-generator/assets/155182909/39befae7-819c-4249-aed5-129e820b3e0c)

* **find_empty**(matrix): This function returns a tuple containing the coordinates of the first empty cell within the timetable matrix.
* **Parameters**:
		* **matrix**: a 3d matrix containing the structure of our timetable.

* **valid**(course,pos,matrix):  This function checks whether it's possible to insert a course into a specific position inside the matrix. It validates various scheduling conditions established at the beginning of the project. If all conditions are successfully met, the function returns **True**, indicating that it's possible to place the **course** in the specified **pos**. Otherwise, it returns **False** if any of the conditions are not satisfied.
	* **Parameters**:
		* **course**: A Course object containing the information relative to the course to inserted.
		* **pos**: A tuple containing the coordinates of a specific cell within the matrix.
		* **matrix**:  A 3D matrix containing the structure of our timetable.

* **generate_tables**(matrix,courses_list,professors_list,classrooms_list): This recursive function is responsible for generating timetables for various classes. It begins by finding the first empty cell within the timetables matrix using the **find_empty** function. Once an empty cell is found, the function proceeds to generate a list of **Course** objects, created by combining various values randomly selected from the courses, professors, and classrooms lists provided by the user. Finally, the function loops through this newly created list to fill the timetable matrix using the **valid** method, ensuring adherence to all scheduling conditions. The function returns **True** if the matrix is successfully filled, otherwise it returns **False**.

	* **Paramesters**:
		* **matrix**:  A 3D matrix containing the structure of our timetable.
		* **courses_list**: A list containing the names of all available courses.
		* **professors_list**: A list containing the names of all available professors.
		* **classrooms_list**: A list containing the names of all available classrooms.

* **display_matrix**(matrix): This function is used to display the 3D matrix, which serves as the structure of our timetables in the shell.
	* **Parameters**:
		* **matrix**:  A 3D matrix containing the structure of our timetable.

## settings.py

**settings.py** serves as a centralized configuration file, housing all the necessary parameters and constants essential for the program's functionality. This approach ensures consistency throughout the application and streamlines the process of adjusting the application's behavior. 
This file contains the following values:
* **Colors values**: this section lists constants containing various color codes used throughout the program.
	* **BLACK**: A string containing the hex code for the color black.
	* **WHITE**: A string containing the hex code for the color black.
	* **CLOSE_RED**: A string containing the hex code for a custom red color, used for the delete value button in the scrolling section.

* **Fonts**: This section contains settings for configuring the fonts implemented within the program.
	* **FONT**:  A string containing a font family name.
	* **FONT_STATUS**:  A string containing the font name used in the title labels.
	* **TITLE_FONT_SIZE**: An integer indicating the text size for the title labels.
	* **NORMAL_FONT_SIZE**: An integer indicating the text size for regular text.
	*  **SELECT_ALL_BUTTON_FONT_SIZE**: An integer indicating the text size inside the select all button.

* **Lists**: This section contains various constants lists used by the program.
	*   **IT_COURSES**: A list of pre-defined courses names used to populate the **courses** table when creating the database for the first time.
	* **PROFESSOR_NAMES**: A list of pre-defined professors names used to populate the **professors** table when creating the database for the first time.
	* **COURSES_TYPES**: A list of pre-defined courses types used to define the course type when creating a **Course** object. 

## Author: Mohamed Helali
