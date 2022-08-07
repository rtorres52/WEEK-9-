# WEEK-9-
import os

# Ask the user to input the directory address
nameOfDirctry = input("Directory to store the new file: ")
# Ask the user to input the file name of the file to be created
nameOfFileToBeMade = input("Please enter the name of file to be created: ")
# Ask the user to input his/her name
inputName = input("Please enter your full name: ")
# Ask the user to input his/her address
inputAddr = input("Please enter your full address: ")
# Ask the user to input his/her phone no.
inputContactNum = input("Please enter your phone no.: ")

# Determine if the name of directory entered by user is there
if os.path.isdir(nameOfDirctry):

    # Make a new file with the name of "nameOfFileToBeMade" and open it in a write "w" mode
    fileToBeWrittenTo = open(os.path.join(nameOfDirctry, nameOfFileToBeMade), "w")

    # Write the information entered by the user in a comma seperated line to the file
    fileToBeWrittenTo.write(inputName + str(",") + inputAddr + str(",") + inputContactNum)

    # Close the opened file
    fileToBeWrittenTo.close()

    # Output or print the file data message
    print("The data in file is: ")

    # Now, Open the same file in read "r" mode
    fileToBeScanned = open(os.path.join(nameOfDirctry, nameOfFileToBeMade), "r")

    # Read the entire data of the file and print it in console
    print(fileToBeScanned.read())

    # Close the opened file
    fileToBeScanned.close()

# Otherwise print the error
else:
    # print the error that directory is non-existent
    print("The directory mentioned is non-existent, please try again!")
