HSE VK Dataset
==============

This data set contains information about 20,684 students of National Research University Higher School of Economics along with information about 1,460,470 of their interactions on a popular social network VK since the 27th of October, 2007 and until the 1st of September, 2016.

Data collection
---------------

Lists of students along with their GPA are publicly available on the university web site. This information is published for most of the university educational programs. The lists of students were downloaded, combined and then automatically matched with students' profiles on the social networking site VK. VK provides API (application public interface) that allows to perform search requests and download information about its users in JSON format if it is not hidden by privacy settings. Students and profiles were matched by the first and the last names. A special dictionary was used to account for different forms of the same name in Russian, e.g. Ваня (Vanya) and Иван (Ivan). The search was performed among users who stated that they study in the university in their profiles and additionally among their friends. 91% of all students were found. Data was downloaded in August, 2016.

Anonymization
-------------

All VK identifiers and student names were removed from the data set. It is possible to reconstruct them based on information about group subscriptions or history of likes included in the data set. However the further obfuscation of the data would not make sense as it is easier to collect the same data from scratch (all information is publicly available) than to deanonymize it in this way. 

List of files
-------------

### master.csv
List of all students, contains following information  
id - student identifier used in other files.
gender - gender of a student as stated on VK site, 1 is female, 2 is male, 0 for students whose profiles were not found  
stage - ba for bachelor, ma for master students  
year - year of studies, 1 for freshmen, 2 for sophomores, 3 for juniors, 4 for seniors. Note that values 1 and 2 for master students corresponds to the 5th and 6th years of university studies respectively  
campus - code for city campuses  
faculty - code for faculty  
program - code for educational programme  
gpa - grade point average for the last semester (second semester of 2015/16 academic year). The maximum value is 10, less than 4 is not passed  
total_friends - total number of VK friends, 0 if student was not found on VK or information was hidden by privacy settings  
inside_friends - number of VK friends who are present in this data set  

### code_book.xlsx
Full names of campuses, faculties and programmes corresponding to the codes from master.csv.

### friends.json
Data about VK friendship in JSON format. 

### groups.json
File contains VK ids of the groups to which students are subscribed

### groups_info.json
Basic information about groups. group_id corresponds to id from groups.json. members_count is total number of subscribers, hse_count is number of subscribers who are present in this dataset. If is_closed is equal to 1 it means that membership requires confirmation from group's administrators. If is_closed is equal to 2 it means that list of group's members is hidden, members_count in this case is equalt to 0. There are two types of groups on VK roughly corresponding to Facebook groups and Facebook pages. We made no distinction between them in this data set.

### graph.png
Visualization of friendship network. 4 main clusters correspond to 4 campuses, smaller clusters correspond to different educational programmes, different colors correspond to different years of studies.

### info.json
Additional information from VK about gender, privacy settings and time of last visit.

### likes.json
Data about about 1,460,470 `likes`. Each entry contains id of a student who posted a content, id of a student who liked the content and corresponding timestamp.

### history.pdf
Vizualization of changes in number of interaction between students from the same cohort with time.