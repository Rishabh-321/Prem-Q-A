# Prem-Q-A
In this Project I took a Pdf in which there are 15 Question.
I took screen shot of each question and created a file.
File Name As Q Contain Png image of all the question.
File Name As A Contain Png image for answer.
import os :- An operating system is system software that manage computer hardware, Software resources, and provides various service for Computer program.
import cv2 :- OpenCV (Open Source Computer Vision Library) is an open source computrt vision and machine learning software library. It provide a wide range of function and tools for image and video processing, computer vision task and machine leaening applications.
import random :- it is a python module that provides function for generating random number and making random selectios. it is often used in programming for task like shuffling data, generating random values, or creating random simulations.
import pandas :- it provide data structure and data analysis tools for working with structured data. it is used in handling and analyzing data in tabular or dpreadsheet-like format  making it a powerful tool for data manipulation and exploration.
def display_image(image_path):- function named dispaly_image' that take argument, 'image_path', which should be a string representing the path to an image fil.
img = cv2.imread(image_path) :- 'cv2.imshow()' function is used to display the image as output. 2 arugument are taken:- first is a string ('image' in this case) that specifies the name of the image in file. second argumrent ('img') is the image data.
cv2.waitKey(0) :- This code wait for user to enter answer using keybord and press enter.
cv2.destroyAllWindows() :- after any key is press this code close all windows with specified title.
while true :- this is an ifinite loop till user enter corret input from a,b,c,d.
user_input = input("Enter your answer (a/b/c/d): ").strip().lower() :- this line ask user to give input by displaying "Enter your answer (a/b/c/d):" strip removes blank space. lower convert input in form of lower case alphabet.
if user_input in ('a', 'b', 'c', 'd'): - if the user input is any letter b/w a-d the input is valid. else code move to next steps.
return user_input :- if user input is valid. it stored as result of get_user_input().
else :- if the user input is not valid. then it print "invalid input. Please enter valid option.
options = ['a', 'b', 'c', 'd'] :- provide option 
q_folder = 'Q' = question file location.
a_folder = 'A' = answer file location.
question_images = [os.path.join(q_folder, image) for image in os.listdir(q_folder) if image.endswith(('.jpg', '.png'))] :- this line create a list of image in that folder. os.listdir(q_folder) retrive list of all files contained within q_folder. if image.endswith(('.jpg', '.png')) this segment of code tell to select the file extension of jpg, png. os.path.join(q_folder, image) :- tell about full path of folder.
for question_image in question_images: this segment of code iniciate a loop and go through each items in the " question image " list. display_image(question_image) it take question image as argument.user_answer = get_user_input() after displaying image this line of code take user answer and print descritive message. print(f"Your answer: {user_answer}\n") this statment print user answer.
user_answers[question_image] = user_answer :- store user answer
print("\nCorrect Answers:") :- print header for displaying answer.
for question_image, user_answer in user_answers.items() :- this loop go throgh user answer dictionary. it print question image with user answer.
csv = 'answer.csv :- this line tells about name of csv. which contains answer of question.
if os.path.exists(csv): - this conditional line of code checks whether the csv is specified by csv.
df = pd.read_csv(csv) : - read the content of csv.
print(df) :- this code read its content into a pandas Data frame named df.
print("\nContent of the csv file:") :-  print content of header indicating that the output will display csv.

print("All questions answered!") :- this line tells about ends of  the program.

