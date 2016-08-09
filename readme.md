HSE VK Dataset
==============

This data set contains information aobut 20,684 students of National Research University Higher School of Economics along with information about XXX,XXX,XXX of their interactions on a popular social network VK since XX of XX, 20XX.

Data collection
---------------

Lists of students along with their GPA are publicly available on the university web site. This information is published for most of the university educational programs. The lists of students were downloaded, combined and then automatically matched with students' profiles on the social network site VK. VK provides API (application public interface) that allows to perform search requests and download information about its users if it is not hidden by privacy settings in JSON format. Students and profiles were matched by the first and the last names. A special dictionary was used to account for different forms of the same name in Russian, e.g. Ваня (Vanya) and Иван (Ivan). The search was performed among users who stated that they study in the university in their profiles and additionally among their friends. 91% of all students were found.

List of files
-------------

### master.csv
List of all students, contains following information  
id - student identifier used in other files. All VK identifiers and student names were removed from data set  
gender - gender of a student as stated on VK site, 1 is female, 2 is male, 0 for students whose profiles were not found  
stage - ba for bachelor, ma for master students  
year - year of studies, 1 for freshmen, 2 for sophomores, 3 for juniors, 4 for seniors. Note that values 1 and 2 for master students corresponds to the 5th and 6th years of university studies respectively  
campus - code for city campuses  
faculty - code for faculty  
program - code for educatoinal progamme  
gpa - grade point average for the last semester (second semester of 2015/16 academic year). The maximum value is 10, less than 4 is not passed  
total_friends - total number of VK friends, 0 if student was not found on VK or information was hidden by privacy settings  
inside_friends - number of VK friends who are present in this data set  

### code_book.xlsx
Full names of campuses, faculties and programmes corresponding to the codes from master.csv

### friends.json
Data about VK friendship in JSON format

### graph.png
Vizualization of friendship network. 4 main clusters correspond to 4 campuses, smaller clusters correspond to different educational programmes, different colors correspond to different years of studies