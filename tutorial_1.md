# Section 1 

The goal of the first section of the tutorial is to get some confidence in browsing your filesystem from the terminal.

The commands you'll likely need are :
- ls: list contents
- pwd: print working directory
- cd: change directory
- mkdir: make a new directory
- mv: move a file
- rm: remove a file

If you want more information on how to use a command you can type `man command_name` to see the manual page (press `q` to exit)
## Step 1
Open your terminal and create where you prefer a directory for this course named `LearningDataScience` and a subdirectory `Tutorial_1`.

Download the free version of the World Cities data as a CSV file at the following link:
[https://simplemaps.com/data/world-cities](https://simplemaps.com/data/world-cities)

unzip the folder from your terminal and move the csv file to your tutorial directory.

## Step 2
Look at the data using `cat`, `awk`, `less`, `head`, etc to familiarise yourself with the structure of the data.

- Create a new file `smaller.csv` where we you keep only the columns: `"city_ascii","lat","lng","country","population","id"`

- As you can see all the elements are double quoted, get rid of the double quotes creating a new file `clean.csv`. 


Could you obtain the `clean.csv` with a single command line?

## Step 3
- Compare the size of the `smaller.csv` and the original dataset size
- Find your favourite city using the grep command
- Find the five cities with the most number of inhabitants (use the `clean.csv` file )
-  Print the cities and population where population is > 10000000. If u see string like "minor", "admin" can u get what went wrong?



As you discussed in the lecture the unix tools are best for quick data manipulations, **but** for more serious processing you'll have to switch to some other tools/programming language. You can use any tool you like, and we will show you a few, including Python & Julia. This week's exercise focuses on Python, and we will have more on Julia a little later.

# Section 2 - Python 

Read through the lecture again to have a complete understanding, but I'll try to summarise few keys ideas for you.

You can install your desired *python version* on your computer from the official python [website](https://www.python.org/downloads/). 
Python has an included package manager (pip) that allows you to easily extend the capabilities of the language. 

For different project you can need different packages or different versions of the same package, to avoid to uninstall and install every time all the packages you can create different virtual environment.

pyenv-virtualenv: can easily manage multiple venvs without having them scattered across your computer 

<img width="1018" height="462" alt="image" src="https://github.com/user-attachments/assets/ae802baa-5611-41f5-967e-5029685e8448" />


**But your python has a fixed version !** 
If you want the ability to choose your python version you need an extra "python version manager". Possible choices are:
- pyenv
- conda
- pixi --> this is what I use!

### Step 1
Create 2 different folders, *numpy_old* and *numpy_new* with 2 different environments.
- *numpy old*: python=3.13, numpy = 2.4.6
- *numpy_new* : python=3.13, numpy= 2.5.0
You can choose the way you prefer to configure this two environments (install python 3.13 and then create virtual environments or  pyenv or  conda or Pixi). If you're lost and don't have strong opinions you can follow the brief instructions to use Pixi in section 3.

# Section 3 -  Pixi (extra)
Pixi is a **fast, modern, and reproducible** package management tool for developers of all backgrounds. We'll use it to set-up a python environment, but you could use it also for julia.

### Step 1
Install pixi following the instructions [here](https://pixi.prefix.dev/latest/installation/)

### Step 2
In your `Tutorial_1` folder this is the list of commands you have to type:

```
mkdir numpy_old
cd numpy_old

pixi init
pixi add python==3.13 numpy==2.4.6
pixi shell                    #activate the environment
```
You have your environment set up !
Few questions to push you a bit more what's happening:
- what are the pixi.lock and the pixi.toml files? are the only files created (use `ls -a`)
- where is the python installation? Can you find the python libraries and the site-package numpy?
