# Lab 5: Intro to Python

## This lab uses the Pycharm IDE - you are free to use whatever IDE you prefer - or none

In this lab we will create our first project using the PyCharm IDE and we'll also have a quick look at finding our way around. We'll then create some basic python scripts to start our python coding.

___

## Lab Contents

1. Creating a project in PyCharm.
2. Adding our first python file.
3. Exploring the Windows
    - Run Window
    - Terminal Window
    - Python Console
4. Passing Arguments to Python
    - Using sys.argv
6. CA coding assignment.

___

### Creating a Project in PyCharm

I'm assuming you each have PyCharm educational edition installed and have completed the intro to python course and exercises. (If not you will want to catch up on them this week)

PyCharm (and most programming IDEs) deal with projects. Every file you create will be part of a project. To create our first project, first click on 'File' then 'New Project' from the main menu.

PyCharm will first ask you to create a default home folder for your project, I suggest you create a labs folder or similar and don't use the suggested 'PyCharm Projects' folder which is the default.

There is also an option to set your virtual project environment in the dropdown section below the project name. We will just use the default options for now and ignore these settings. 


### Adding our first python file

So once you have created your project folder we need to add some files to it. In the project explorer on the left hand you can simply right-click and select 'new' - 'python file'.

Name/Save our new file as hello.py

This should create a new blank file for us and we can start editing straight away in the main editor window.

So lets add the essential programming goto first line of code

```python
print ('Hello World!')
```
On the left of our main editor window you should see a small green arrow/triangle, you can click this to execute your code. Once you execute your code a run window should appear in the bottom section of your IDE, with the output or any error messages from the python script that we just tried to execute.

Hopefully everything went OK and you have the code output as shown below and no errors or warnings.

```python
Hello World!
Process finished with exit code 0
```

### Exploring the Windows

After running your code you should have seen the run window open up with the outputs of your code. However if you look closely at the very bottom of that run window you will notice a couple of other very useful windows. These are the Terminal window and the Python console, both of which can be extremely useful.

#### Terminal Window

If you click on the terminal window you will see a familiar terminal environment that will open within your project folder allowing you to run the standard terminal commands and interact with your project files, this can be very helpful so remember it.

From the terminal window with your PyCharm type the following commands: 
```bash
$ python --version
Python 3.6.7
```

and then try run our script from earlier, but this time from the command line. 

```bash
$ python hello.py
Hello World!
```

and finally let's just check what files are in our project folder.

```bash
$ ls
hello.py venv
```

What is this 'venv' folder that has been created inside our project? We'll come back to this and talk about it again later.

#### Python Console

The other window that is available along with our run and terminal windows is the Python Console. This a a powerful interact python environment where we can type python commands directly and check their results or just perform quick calculates etc without the need to create and run a full script. Once you get use the Python console you'll look the simple and quick power it offers you.

open the Python Console and try some of the following commands:

```python
>>> print ('Hello World!')
Hello World!

>>> 123 * 456
56088
```

### Passing arguments to Python

One of the most useful features of a program/function is the ability to pass arguments in to it. Allowing us to reuse the code for multiple values rather than single just hard coded instances. In this section we'll have a quick look at how to pass arguments to a python program.

python uses the 'sys.argv' function for processing arguments passed into the code. To use it we need to import he sys library. The file name and any other parameters are passed into the program for processing.

Create a new python file called inputs.py and copy the code below into it. Once finished run the code from with PyCharm.

```python
import sys
print ('This is the name of the script: ' + sys.argv[0])
print ('Number of arguments: ' +  str(len(sys.argv)))
print ('The arguments are: ' + str(sys.argv))
```
Hopefully your code should execute and you should see the script returning some details.

sys.argv is essentially an array of each of the inputs. The first element of that array 'sys.argv[0]' is the filename itself, each argument passed in after that would be referenced as 'sys.argv[1]', 'sys.argv[2]' etc.

Open up the terminal window (from with PyCharm) and try the following command:

```bash
$ python inputs.py 'hello' 1 A 
This is the name of the script: inputs.py
Number of arguments: 4
The arguments are: ['inputs.py', 'hello', '1', 'A']
```

#### Using sys.argv 

Create a new python file to try solve each of the following:

1. Create a script that reads in three numbers a,b,c and then computes the results of (a+b)*c 
2. Create a python script that check if the number of arguments passed into it = 4, else print a usage instructions to the user.
3. Create a script that reads in an integer and prints the result out as binary

> Hint: Try using bin(str(number))[2:]    

### Continuous Assessment assignment for submission

In the previous labs we looked at using the tr command to create some basic rotational ciphers. Well lets step it up a notch and see if we can can create a single universal rotational cipher brute forcing tool.

Your cipher should read in the character sets you wish to use (dec for rot5, alpha for rot13 or caesar,all for rot47) and then the ciphertext you wish to brute force. Your cipher should then print out all possible decodings of the ciphertext given.

In the example command line below "dec" and "'1'" are example arguments
"dec" means that you want to use a decimal character set (i.e. rot5)
'1' is the ciphertext

```bash
$ python brute.py dec '1' 
1
2
3
4
5
6
7
8
9
0 
```
