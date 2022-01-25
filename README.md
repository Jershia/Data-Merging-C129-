# Data Merging
* We took two different datasets, merged them together and processed the data.

## Steps To Scrape data
  * *Observe that the headers have 11 items while the data has 13 items.*
  * *Find the missing headers and add them*
  * *Observe the two datasets and try to find a pattern in order to merge them.*
  * *Conclude that both the datasets are arranged in alphabetical order.*
  * *Observe that the second dataset has all the lowercase planet names at the bottom of the list separately*
  * *Create a script that can arrange the second dataset alphabetically irrespective of them being lowercase or uppercase.*
  * *Create a new directory and create a virtual environment.*
  * *Move the downloaded CSV to this new folder and rename it to dataset_1.csv.*
  * *we conclude that we will convert all planet names (3rd column of the CSV) into either uppercase or lowercase and then sort the data **(Code given below)**.*
  * *Move the CSV of the data we scraped and rename it to dataset_1.csv.*
  * *Write a script to merge the two datasets and create a final.csv **(Code given below)**.*
  
## Code is given below
### *Code for merging datasets:* 
````
import csv

dataset_1 = [] 
dataset_2 = []

with open("dataset_1.csv", "r") as f:
csvreader = csv.reader(f) for row in csvreader:
dataset_1.append(row)

with open("dataset_2_sorted.csv", "r") as f:
csvreader = csv.reader(f) 
for row in csvreader:
 dataset_2.append(row)

headers_1 = dataset_1[0] 
planet_data_1 = dataset_1[1:]

headers_2 = dataset_2[0] 
planet_data_2 = dataset_2[1:]

headers = headers_1 + headers_2 
planet_data = []
for index, data_row in enumerate(planet_data_1): 
 planet_data.append(planet_data_1[index] + planet_data_2[index])

with open("final.csv", "a+") as f: 
csvwriter = csv.writer(f) 
````
### *Code to covert planet names to lowercase:*
````
import csv
data = []
with open("dataset_2.csv", "r") as f:
csvreader = csv.reader(f)
for row in csvreader:
data.append(row)

headers = data[0] planet_data = data[1:]

##Converting all planet names īo lowercase
for data_point in planet_data:
data_point[2] = data_point[2].lower()

#Sorting planet names in alphabeīical order
planet_data.sort(key=lambda planet_data: planet_data[2])


with open("dataset_2_sorted.csv", "a+") as f: 
csvwriter = csv.writer(f) 
csvwriter.writerow(headers) 
csvwriter.writerows(planet_data)

````
### *Code for activating venv*
````
python -m venv venv
#open venv in integrated terminal
cd Scripts
.\activate.bat
````
## New Terms :
 * *Beautiful soup targets html tags.html.parser the data.
 * *enumerate add index numbers.*
 * *xpath is used to navigate through elements in xml document.*
 * *BeautifulSoup(bs4):- used for parsing text as html and performing actions in it like finding specific html tags with a particular id,class,ul,il tag etc..*
 * *Selenium:-used for browsing over websites.*

## Facts :
* *All the lowercase letters have a higher ASCII value (lowercase a
has an ASCII value of 97) and all the uppercase letters have a lower ASCII
value (uppercase A has an ASCII value of 65).*
