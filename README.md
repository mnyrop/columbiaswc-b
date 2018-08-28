


# Columbia University x Software Carpentries<br>  Python Group B

__Bootcamp Site:__ https://columbiaswc.github.io/2018-08-27-Columbia-B/

__Instructors:__

- Cesar Arias – ca2783@columbia.edu
- Marii Nyröp – m.nyrop@columbia.edu | [@mnyrop](https://github.com/mnyrop) | [marii.info](http://marii.info)

__Helpers:__
- Jochen Weber
- Parixit Davé
- Yanchen Liu

# Contents
- [Schedule](#schedule)
- [Setup](#setup)
- [1: The Unix Shell](#section-1--the-unix-shell)
  + [Introducing the Shell](#introducing-the-shell)
  + [Navigating Files and Directories](#navigating-files-and-directories)
  + [Working with Files and Directories](#working-with-files-and-directories)
  + [Pipes and Filters](#pipes-and-filters)
  + [Loops](#loops)
- [2: Version Control with Git](#section-2--version-control-with-git)
  + [Automated Version Control](#automated-version-control)
  + [Creating a Repository](#creating-a-repository)
  + [Tracking Changes](#tracking-changes)
  + [Ignoring Things](#ignoring-things)
  + [Remotes in GitHub](#remotes-in-github)
  + [Collaborating](#collaborating)
  + [Conflicts](#conflicts)
  + [Open Science](#open-science)
  + [Licensing](#licensing)
  + [Citation](#citation)
  + [Hosting](#hosting)
  + [Exploring History](#exploring-history-at-the-end-if-theres-time)
- [3: Programming with Python](#section-3--programming-with-python)
  + [Analyzing Patient Data](#analyzing-patient-data)
  + [Repeating Actions with Loops](#repeating-actions-with-loops)
  + [Storing Multiple Values in Lists](#storing-multiple-values-in-lists)
  + [Analyzing Data from Multiple Files](#analyzing-data-from-multiple-files)
  + [Making Choices](#making-choices)
  + [Creating Functions](#creating-functions)
  + [Errors and Exceptions](#errors-and-exceptions)
  + [Defensive Programming](#defensive-programming)
  + [Debugging](#debugging)
  + [Command-Line Programs](#command-line-programs)


# Schedule


| Day 1   | | Day 2|
|---------|-|------|
| 09:00   | Automating tasks with the Unix shell | Building programs with Python |
| 10:30   | Break | Break |
| 12:00   | Lunch break | Lunch break |
| 01:00   | Version control with Git | Building programs with Python, Continued |
| 02:30   | Break | Break |
| 04:00   | Wrap-up | Wrap-up & post-workshop survey |
| 04:30   | END | END |


# Setup

__Setup check in:__

- [ ] Do you have the necessary software (Bash, Git, and Python) installed?
- [ ] Do you have [Jupyter notebooks](https://jupyter.org/install) installed? (You can check by opening a Terminal and entering the command `jupyter notebook`. This should open a browser.)
- [ ] Do you have the demo data for [bash](http://swcarpentry.github.io/shell-novice/setup.html) and [python](https://swcarpentry.github.io/python-novice-inflammation/setup/) downloaded?
- [ ] Do you have a [GitHub account](https://github.com/join)?
- [ ] Do you have 2 color post-its?

__Setup resources:__
- <https://columbiaswc.github.io/2018-08-27-Columbia-B/#setup>
- <http://swcarpentry.github.io/shell-novice/setup.html>
- <http://dhbox.org/> ~> instructions: <https://gist.github.com/mnyrop/4f6ff1b8a3737782c12fcedbb8da8966>


# Section 1 :: The Unix Shell

## Introducing the Shell


#### Questions:
- What is a command shell and why would I use one?

#### Notes:
- Graphical User Interface (GUI) versus Command Line Interface (CLI)
- Read-evaluate-print-loop (REPL)
- Command, flag, argument
- Flexibility and automation

#### Try

- [ ] `pwd`
- [ ] `ls -F /`

## Navigating Files and Directories

#### Questions:
- How can I move around on my computer?
- How can I see what files and directories I have?
- How can I specify the location of a file or directory on my computer?

#### Notes:
- File system hierarchy
- Current working directory
- Root directory
- Home directory
- `man` and `--help`
- Abosulute vs Relative path

#### Try:

- [ ] `ls`
- [ ] `ls -F`
- [ ] `ls --help`
- [ ] `man ls`
- [ ] `ls -j`
- [ ] `ls -l`
- [ ] `ls -R`
- [ ] `ls -F Desktop`
- [ ] `pwd`
- [ ] `cd desktop` or `cd Desktop`
- [ ] `cd data-shell`
- [ ] `cd data`
- [ ] `cd ..`
- [ ] `cd ~/desktop/data-shell/data` or `cd ~/Desktop/data-shell/data`
- [ ] `cd /`
- [ ] `cd ~`
- [ ] `cd -`

#### Activity:

- [ ] move into `data-shell` directory
- [ ] enter the command `ls north-pacific-gyre/2012-07-03/` using tab completion

### Working With Files and Directories


#### Questions:
- How can I create, copy, and delete files and directories?
- How can I edit files?

### Notes
- Naming conventions for files and directories
- The Nano text editor
- Deleting with `rm` is forever

### Try
- [ ] Go back to `data-shell` by checking where you are `pwd`and using `cd`
- [ ] Check what's in `data shell` with `ls -F`
- [ ] Make a new directory called 'thesis' `mkdir thesis`
- [ ] Check what's in the directory again `ls -F`
- [ ] Nothing is in `thesis` because it's brand new. Check with `ls -F thesis`
- [ ] Move into `thesis` with `cd thesis`
- [ ] Use Nano to add and edit a file `nano draft.txt`. Add some lines of text, then use __Ctrl-X__ to exit.
- [ ] Go to your home directory and make a file using touch. `cd ~` followed by `touch my_file.txt`
- [ ] Use `ls -l` to inspect the files. How large is `my_file.txt`? Why?
- [ ] Move back into `thesis` in `data-shell` with `cd` and remove the draft file with rm `rm draft.txt` using tab completion. But be careful!
- [ ] Run `ls` to see if the file is still there.
- [ ] Re-add the file and move back into `data-shell` with `nano draft.txt`, `ls`, and `cd ..`
- [ ] Try removing `thesis` with `rm thesis`. What happens?
- [ ] Type out `rm -r thesis` for removing the directory recursively. But don't hit enter! We're not ready to delete it yet.
- [ ] Instead try removing the directory safely with `rm -r -i thesis`. Type `y` for each file to delete.
- [ ] Make the `thesis` directory in `data-shell`again by checking where you are `pwd`and using `mkdir thesis`
- [ ] Remake the file `draft.txt` with nano `nano thesis/draft.txt`
- [ ] Change the filename of `draft.txt` to `quotes.txt` using `mv thesis/draft.txt thesis/quotes.txt`
- [ ] Check what happened with `ls thesis`
- [ ] Move `quotes.txt` into the current working directory with `mv thesis/quotes.txt .`
- [ ] See what's in `thesis` with `ls thesis`
- [ ] Find `quotes.txt` in the current working directory with `ls`



## Pipes and Filters


#### Questions:
- How can I combine existing commands to do new things?


#### Notes:
- Redirect output to a file with `command > filepath`
- Use pipes `|` to chain output between commands
- `cat` to display contents
- `head` to display first 10 lines
- `tail` to display last 10 lines
- `sort` to sort alphabetically, `sort -n` to sort numerically
- `wc` to count lines, words, and characters

#### Try:
- [ ] Make sure you are in `data-shell` using `pwd` and `cd` if necessary
- [ ] See what's in `molecules` with `ls molecules`
- [ ] Change directory into `molecules` and run a word count on the `.pdb` files with `cd molecules` and `wc *.pdb`
- [ ] Only count the lines with `wc -l *.pdb`
- [ ] Output the results to a file using the `>` symbol `wc -l *.pdb > lengths.txt`
- [ ] Check that `lengths.txt` was created with `ls`
- [ ] Print out the contents of the file with `cat lengths.txt`
- [ ] Sort the contents of the file with the `-n` flag (sorts numerically instead of alphabetically) `sort -n lengths.txt`
- [ ] Redirect the sorted results to a new file `sort -n lengths.txt > sorted-lengths.txt`
- [ ] Print out the first sorted line `head -n 1 sorted-lengths.txt`

#### Activity:
- [ ] `cd` into `north-pacific-gyre/2012-07-03`
- [ ] Get a line count on the `.txt` files `wc -l *.txt`. All the files should be the same length. Are they?
- [ ] Check to see if any files are larger than 300 lines `wc -l *.txt | sort -n | tail -n 5`
- [ ] Find other out of place files ending in 'Z' (they should be 'A' or 'B') `ls *Z.txt`

## Loops


#### Questions:
- How can I perform the same actions on many different files?

#### Notes:
- Use a variable with $variable-name or ${variable-name}
- Indent your for loop


#### Try:
- [ ] Move into `~/Desktop/data-shell/creatures` and run `ls`
- [ ] Try creating backups of the `.dat` files with `cp *.dat original-*.dat`. What happens?
- [ ] Try using a loop instead, and print the beginning of the file instead of copying it just yet
      ```sh
      for filename in basilisk.dat unicorn.dat
      do
        head -n 3 $filename
      done
      ```
- [ ] Try rewriting the for loop with a wildcard pattern and actually copy the files
      ```sh
      for filename in *.dat
      do
        cp $filename original-$filename
      end
      ```

#### Activity:
- [ ] Move back into `~/Desktop/data-shell/north-pacific-gyre/2012-07-03`
- [ ] Start a new for loop for the backing up the correct data (starting with 'NENE' and ending in 'A' or 'B' .txt), outputting each file to the console.
      ```sh
      for datafile in NENE*[AB].txt
      do
        echo $datafile
      done
      ```
- [ ] Modify the loop to print the current datafile and the name it will output as after running the `goostats` program
  ```sh
  for datafile in NENE*[AB].txt
  do
    echo $datafile stats-$datafile
  end
  ```

- [ ] Rewrite the loop and actually run the `goostats` program on each file, exporting the results to a new file `stats-$filename`
  ```sh
  for datafile in NENE*[AB].txt
  do
    bash goostats $datafile stats-#datafile
  done
  ```

- [ ] One last time, rewrite the loop to run `goostats` and log useful output as it runs to the console
  ```sh
  for datafile in NENE*[AB].txt
  do
    echo $datafile
    bash goostats $datafile stats-$datafile
  end
  ```




> __Full Tutorial:__ <https://swcarpentry.github.io/shell-novice/>




# Section 2 :: Version Control with Git


## Automated Version Control


#### Questions:
- What is version control and why should I use it?

#### Notes:
- Version control – keeps track of changes and allows for greater control over them
- Manages collaboration and change conflicts


## Setting Up Git


#### Questions:
- How do I get set up to use Git?

#### Notes:
- Git is the software, GitHub is a popular *service* for hosting content that is version controlled by Git
- Your local Git needs to be configured to work with your GitHub account

#### Activity:
- [ ] Configure Git to use your user name with `git config --global user.name "your-username"`
- [ ] Configure Git to use your email with `git config --global user.email "your@email.address"`
- [ ] Configure your Git to use Nano as its text editor with `git config --global core.editor "nano -w"`
- [ ] Check your Git configuration with `git config --list`
- [ ] Check possible config commands with `git config -h`


## Creating a Repository


#### Questions:
- Where does Git store information?

#### Notes:
- A repository is where your Git project files and the history of all your project’s commits live
- `git init` initializes a repository (and everything in it!)
- `git status` shows the repository's current status
- The Git repository history and info lives in a directory called `.git`

#### Activity:

- [ ] `cd ~/Desktop`
- [ ] `mkdir planets`
- [ ] `cd planets`
- [ ] `git init` initializes the `planets` repository


## Tracking Changes

#### Questions:
- How do I record changes in Git?
- How do I check the status of my version control repository?
- How do I record notes about what changes I made and why?

#### Notes:
- Adding and committing
- Commit messages
- Reading the commit history

#### Activity:

- [ ] Check current directory with `pwd`
- [ ] Make sure you are in `~/Desktop/planets` using `cd`
- [ ] Use Nano to make a file `nano mars.txt` and add the sentence 'Cold and dry, but everything is my favorite color' to it before saving
- [ ] Use `ls` to list the directory contents
- [ ] Use `cat mars.txt` to print out the file's content
- [ ] Try `git status` again
- [ ] Tell Git to track our new file with `git add mars.txt`
- [ ] Try `git status` again
- [ ] Commit the changes and give a message about what the changes are with `git commit -m 'start notes on mars as a base'`
- [ ] Try `git status` again
- [ ] Look at the commit history with `git log`
- [ ] Add some additonal info to `mars.txt` with `nano mars.txt`, for example 'The two moons may be a problem for Wolfman'
- [ ] Try `git status` again
- [ ] Try `git diff`
- [ ] Try committing the new changes with `git commit -m 'add concerns about the moons and wolfman'`
- [ ] Try `git status` again
- [ ] Add the file with `git add mars.txt` then retry the commit `git commit -m 'add concerns about the moons and wolfman'`
- [ ] Add a third piece of info to the file with `nano mars.txt`, e.g., 'The mummy will appreciate the lack of humidity'
- [ ] Print it with `cat mars.txt`
- [ ] Try `git diff`
- [ ] Add the file with `git add mars.txt`
- [ ] Commit the changes with `git commit -m 'add mummy climate concerns'`
- [ ] Try `git status` again
- [ ] Look at the commit history with `git log`
- [ ] Try `git log -1`. What happens?
- [ ] Try `git log --oneline`
- [ ] Try `git log --oneline --all --decorate`




## Ignoring Things

#### Questions:
- How can I tell Git to ignore files I don’t want to track?

#### Notes:
- There will often be files you don't want Git to track, for security or efficiency reasons
- Ignored files, directory, and file patterns are listed in a `.gitignore` file

#### Activity:
- [ ] Make sure we're still in `~/Desktop/planets` with `pwd`
- [ ] Make a new directory with `mkdir results`
- [ ] Add a few files with `touch a.dat b.dat results/a.out results/b.out`
- [ ] Run `git status`
- [ ] Make a `.gitignore` file with `nano .gitignore` with `*.dat` on the first line and `results/` on the second line.
- [ ] Print out the file's content with `cat .gitignore`
- [ ] Run `git status` again
- [ ] Add and commit the `.gitignore` file with `git add .gitignore` and `git commit -m 'ignore data files and results folder'`
- [ ] Run `git status again`
- [ ] Try running `git add a.dat`. What happens?
- [ ] Run `git status --ignored`

## Remotes in GitHub

#### Questions:
- How do I share my changes with others on the web?

#### Notes:
- Repository remotes (origin)
- Git Push
- Git Pull

#### Activity:
- [ ] Log into [GitHub](https://github.com)
- [ ] Add a new public repository called 'planets'
- [ ] Copy the 'quick setup' link (it should be 'https://github.com/YOUR_USERNAME/planets.git')
- [ ] And paste it into your terminal for the command `git remote add origin 'https://github.com/YOUR_USERNAME/planets.git'`
- [ ] Run `git remote -V`
- [ ] Run `git push -u origin master` and enter your GitHub password when prompted
- [ ] Try `git pull origin master`
- [ ] Refresh your repository page on GitHub. What do you see?

## Collaborating

#### Notes:
- Collaborator permissions
- Git clone

#### Questions:
- How can I use version control to collaborate with other people?

#### Activity:
- [ ] Pair up with a neighbor and decide who will start as the 'owner' and who will start as the 'collaborator'
- [ ] __Owner:__ click on the 'Settings' tab on your `planets` repository in GitHub, navigate to 'Collaborators' and add your partner's GitHub username.
- [ ] __Collaborator:__ Go to <https://github.com.notifications> and accept the owner's request to collaborate on their repository
- [ ] __Collaborator:__ clone the owner's `planets` repository onto your computer as `OWNER_USERNAME-planets` with `git clone 'https://github.com/OWNER_USERNAME/planets.git' ~/Desktop/OWNER_USERNAME-planets`
- [ ] __Collaborator:__ Change directory into the newly cloned repository with `cd`
- [ ] __Collaborator:__ Add a new file `nano pluto.txt` with the content 'It is so a planet!'
- [ ] __Collaborator:__ Run `cat pluto.txt`
- [ ] __Collaborator:__ Add the file with `git add pluto.txt`
- [ ] __Collaborator:__ Commit the changes and add a commit message `git commit -m 'add notes about Pluto'`
- [ ] __Collaborator:__ Push the changes to the owner's remote repository on GitHub with `git push origin master`
- [ ] __Owner:__ Refresh the repository page on GitHub
- [ ] __Owner:__ Back in the bash terminal, make sure you are in `planets` with `pwd` and `cd` if necessary
- [ ] __Owner:__ Pull in the new changes from the remote repository on GitHub with `git pull origin master`
- [ ] __Owner and Collaborator:__ switch roles and add another planet



## Conflicts

#### Questions:
- What do I do when my changes conflict with someone else’s?

#### Notes:
- When working on the same files, collaborators can create content conflicts.
- Version control with Git provides means for managing and reconciling conflicts
- Use `git fetch` and `git pull` often to avoid/preempt conflicts

#### Activity:
- [ ] __Collaborator:__ Create a conflict by adding another line to `mars.txt` with `nano`: "This is a new line in OWNER_USERNAME's copy"
- [ ] __Collaborator:__ Push the change to GitHub with `git add mars.txt`, `git commit -m 'add a line to OWNER_USERNAME copy'`, and `git push origin master`
- [ ] __Owner:__ Make a change in your own copy of `mars.txt` with `nano`: 'this is a different line added'
- [ ] __Owner:__ Push the change to GitHub with `git add mars.txt`, `git commit -m 'add a line in my copy'`, and `git push origin master`. What happens?
- [ ] __Owner:__ Pull in collaborator's changes with `git pull origin master`
- [ ] __Owner:__ Look at the conflict with `cat mars.txt`
- [ ] __Owner:__ Use `nano mars.txt` to reconcile the conflict.
- [ ] __Owner:__ Merge the changes by committing them with `git add mars.txt`, `git status`, `git commit -m 'merge in changes from GitHub'`, and finally `git push origin master`
- [ ] __Collaborator:__ Pull in the newly reconciled change with `git fetch` and `git pull origin master`
- [ ] __Collaborator:__ Check the results with `cat mars.txt`


## Open Science

#### Questions:
- How can version control help me make my work more open?




## Licensing

#### Questions:
- What licensing information should I include with my work?




## Citation

#### Questions:
- How can I make my work easier to cite?




## Hosting

#### Questions:
- Where should I host my version control repositories?


## Exploring History (at the end, if there's time)

#### Questions:
- How can I identify old versions of files?
- How do I review my changes?
- How can I recover old versions of files?


> __Full Tutorial:__ <https://swcarpentry.github.io/git-novice/>





# Section 3 :: Programming with Python


## Analyzing Patient Data

#### Questions:
- How can I process tabular data files in Python?

#### Notes:
- Variable assignment `variable = value`
- Int, Float, and String types `1`, `1.0`, `'1'`
- Arrays and N-Arrays `[0, 1, 2]` and `[[1, 0],[0, 1],[1, 2]]`
- Print `print(variable)`
- Python libraries (e.g., numpy) `import numpy`
- CSV file (Comma-separated values)
- Indexing and slicing `data[0, 0]` and `data[:3, 10:]`
- IPython mystery functions (`.function`, and `.function?`)
- Add comments with '#' `# this is what this line does`
- Get stats with `numpy.mean(array)`, `numpy.max(array)`, `numpy.min(array)`
- Get stats for a given axis with `numpy.mean(axis=0)` or `numpy.mean(axis=1)`
- Plot and visualize with `matplotlib.pyplot`

#### Activity 1: Variables
- [ ] Make sure you have the [demo data](https://swcarpentry.github.io/python-novice-inflammation/setup/) downloaded
- [ ] Move into the `data` folder with `cd ~/Desktop/swc-python/data`
- [ ] Start a Jupyter notebook with `jupyter notebook` and __New__ > __Python 3__ (Notebook)
- [ ] Enter `3 + 5 * 4` into a cell and press __Shift+Enter__ to run it.
- [ ] Set a variable `weight_kg = 60`
- [ ] Change it to a __float__ with `weight_kg = 60.0`
- [ ] Set a variable `weight_kg_text` to the __string__ 'weight in kilograms: ' with `weight_kg_text = 'weight in kilograms:'`
- [ ] Print out the weight in kilograms with `print(weight_kg)`
- [ ] Print out both the text and the weight with `print(weight_kg_text, weight_kg)`
- [ ] Print out the weight in pounds as a sentence with `print('weight in pounds: ', 2.2 * weight_kg)`
- [ ] Try `print(weight_kg)`. Did the `weight_kg` variable change?
- [ ] Try `weight_kg = 65.0` and `print('weight in kilograms is now: ', weight_kg)`. Did the variable `weight_kg` change?
- [ ] Set `weight_lb = 2.2 * weight_kg` the run `print(weight_kg_text, weight_kg, 'and in pounds:', weight_lb)`
- [ ] Reassign `weight_kg = 100.0` and run `print('weight in kilograms is now:', weight_kg, 'and weight in pounds is still:', weight_lb)`. Why isn't `weight_lb` updated?

#### Activity 2: Loading and Printing Data
- [ ] Clear the notebook and at the top, run `import numpy`
- [ ] Next, load the first sample data file with `numpy.loadtxt(fname='inflammation-01.csv', delimiter=',')`
- [ ] Save the loaded file to a variable called __data__ with `data = numpy.loadtxt(fname='inflammation-01.csv', delimiter=',')`
- [ ] Print out the data `print(data)`
- [ ] Print out the data type for the variable `data` with `print(type(data))`
- [ ] Print out the data's `dtype`, or the data type of the *items* within `data` using `print(data.dtype)`
- [ ] Get the shape of the data (rows, columns) with `print(data.shape)`
- [ ] Get the first value in the data using the index of [0, 0]: `print('the first value in data:', data[0, 0])`
- [ ] Print out the middle value of `data` with `print('middle value in data:', data[30, 20])`
- [ ] Select the first 10 days (columns) from the first 4 patients (rows) with `print(data[0:4,0:10])`
- [ ] Shift the slice to the 5th day with `print(data[5:10, 0:10])`
- [ ] You can drop the first number for a short-hand way to slice from the beginning, and drop the second number to slice through the end. Try `small = data[:3, 36:]`, then `print('small is:')` and `print(small)`. (This selects rows 0-2 and columns 36-end)

#### Activity 3: N-Array Arithmetic/Stats
- [ ] Try
  ```py
  doubledata = data * 2.0
  print('original:')
  print(data[:3, 36:])
  print('doubledata:')
  print(doubledata[:3, 36:])
  ```

- [ ] Try
  ```py
  tripledata = doubledata + data
  print('tripledata')
  print(tripledata[:3, 36:])
  ```

- [ ] Get the mean of the original data with  `print(numpy.mean(data))`
- [ ] Try a function without an input: `import time` then `print(time.ctime())` to get the current time
- [ ] Get the maximum value, minimum value, and standard deviation with
  ```py
  maxval, minval, stdval = numpy.max(data), numpy.min(data), numpy.std(data)

  print('maximum inflammation:', maxval)
  print('minimum inflammation:', minval)
  print('standard deviation', stdval)
  ```

- [ ] Set patient zero to its own variable and print it out

  ```py
  patient_0 = data[0, :]
  print('maximum inflammation for patient 0:', patient_0.max())
  ```
- [ ] Skip storing patient 0 as its own variable and do it in one line

  ```py
  print('maximum inflammation for patient 0:', numpy.max(data[2, :]))
  ```

- [ ] Get the average across the 0 axis (rows) with `print(numpy.mean(data, axis=0))`
- [ ] Get the shape to double check it's doing what we'd expect `print(numpy.mean(data, axis=0).shape)`
- [ ] Print out the average inflammation per patient across all days with the 1 axis (columns) `print(numpy.mean(data, axis=1))`


#### Activity 4: Visualizing Data
- [ ] Get a plot started for the data

  ```py
  import matplotlib.pyplot
  %matplotlib inline
  image = matplotlib.pyplot.imshow(data)
  matplotlib.pyplot.show
  ```
- [ ] Try a plot with the average inflammation over time

  ```py
  ave_inflammation = numpy.mean(data, axis=0)
  ave_plot = matplotlib.pyplot.plot(ave_inflammation)
  matplotlib.pyplot.show()
  ```

  Is this expected?

- [ ] What about the maximum value along the first axis (0)?

  ```py
  max_plot = matplotlib.pyplot.plot(numpy.max(data, axis=0))
  matplotlib.pyplot.show()
  ```

- [ ] What about the minimum value along the first axis (0)?

  ```py
  min__plot = matplotlib.pyplot.plot(numpy.min(data, axis=0))
  matplotlib.pyplot.show()
  ```
- [ ] Group the plots together in one figure to compare, and start from scratch at the top of your notebook

  ```py
  import numpy
  import matplotlib.pyplot

  %matplotlib inline

  data = numpy.loadtxt(fname='inflammation-01.csv', delimiter=',')

  fig = matplotlib.pyplot.figure(figsize=(10.0, 3.0))

  axes1 = fig.add_subplot(1, 3, 1)
  axes2 = fig.add_subplot(1, 3, 2)
  axes3 = fig.add_subplot(1, 3, 3)

  axes1.set_ylabel('average')
  axes1.plot(numpy.mean(data, axis=0))

  axes2.set_ylabel('max')
  axes2.plot(numpy.max(data, axis=0))

  axes3.set_ylabel('min')
  axes3.plot(numpy.min(data, axis=0))

  fig.tight_layout()

  matplotlib.pyplot.show()
  ```

## Repeating Actions with Loops

#### Questions:
- How can I do the same operations on many different values?

#### Notes:
- Loop with
  ```py
  for variable in collection:
    do things with variable
  ```
- Body of the loop must be indented
- Use `len(variable)` to get the length of an array or string

#### Try:
- [ ] Print out the characters in the word 'lead':
  ```py
  word = 'lead'
  print(word[0])
  print(word[1])
  print(word[2])
  print(word[3])
  ```

- [ ] Try with 'tin'. What happens?
  ```py
  word = 'tin'
  print(word[0])
  print(word[1])
  print(word[2])
  print(word[3])
  ```

- [ ] Try printing the characters with a loop instead:
  ```py
  word = 'lead'
  for char in word:
    print(char)
  ```

- [ ] Switch the word to 'oxygen'. Does it work?
  ```py
  word = 'oxygen'
  for char in word:
    print(char)
  ```

- [ ] Swap out the variable name. What happens?
  ```py
  word = 'oxygen'
  for banana in word:
    print(banana)
  ```
- [ ] Make a loop that updates a variable:
  ```py
  length = 0
  for vowel in 'aeiou':
    length = length + 1
  print('There are', length, 'vowels')   
  ```

- [ ] Try another loop. Does it do what you'd expect?
  ```py
  letter = 'z'
  for letter in 'abc':
    print(letter)
  print('after the loop, letter is', letter)
  ```

- [ ] Use a shortcut to count the vowels:
  ```py
  print(len('aeiou'))
  ```



## Storing Multiple Values in Lists

#### Questions:
- How can I store many values together?

#### Notes:
- Mutable vs. immutable data (lists and arrays vs strings and numbers)
- In-place modifications can be tricky
- Lists use bracket notation `list = [item, item2, item3]`, and can be indexed `list[0]` and sliced `list[:2]`

#### Try:

- [ ] Make a list
  ```py
  odds = [1, 3, 5, 7]
  print('odds are', odds)
  ```

- [ ] Select items from the list by index
  ```py
  print('first and last', odds[0], odds[-1])
  ```

- [ ] Loop over items in the list
  ```py
  for number in odds:
    print(number)
  ```

- [ ] Change an item in a list (fix a typo)
  ```py
  names = ['Curie', 'Darwing', 'Turing']
  print('names is originally', names)
  names[1] = 'Darwin'
  print('final value of names:', names)
  ```
- [ ] Now try changing a character in a string. What happens?
  ```py
  name = 'Darwin'
  name[0] = 'd'
  ```

- [ ] Modify a list based on a list. Does it do what you'd expect?
  ```py
  salsa = ['peppers', 'onions', 'cilantro', 'tomatoes']
  my_salsa = salsa
  salsa[0] = 'hot peppers'
  print('Ingredients in my salsa:', my_salsa)
  ```

- [ ] Try making an independent copy of a list instead
  ```py
  salsa = ['peppers', 'onions', 'cilantro', 'tomatoes']
  my_salsa = list(salsa) # list() makes a copy
  salsa[0] = 'hot peppers'
  print('Ingredients in my salsa:', my_salsa)
  ```

- [ ] Try making a list of lists
  ```py
  x = [['pepper', 'zucchini', 'onion'],
      ['cabbage', 'lettuce', 'garlic'],
      ['apple', 'pear', 'banana']]
  ```
- [ ] Print the first line as a list within a list
  ```py
  print([x[0]])
  ```
- [ ] Print the first line as a list
  ```py
  print(x[0])
  ```
- [ ] Make a heterogeneous list
  ```py
  sample_ages = [10, 12.5, 'Unknown']
  ```

- [ ] Add an item to a the list `odds`
  ```py
  odds.append(11)
  print('odds after adding a value:', odds)
  ```

- [ ] Remove an item from the list `odds` by index
  ```py
  del odds[0]
  print('odds after removing the first element', odds)
  ```

- [ ] Reverse the list
  ```py
  odds.reverse()
  print('odds after reversing', odds)
  ```

 - [ ] Try modifying a list in place. (Remember, it's immutable!) What happens?
  ```py
  odds = [1,3, 5, 7]
  primes = odds
  primes.append(2)
  print('primes:', primes)
  print('odds:', odds)
  ```

- [ ] Try again by making a copy with `list()`
  ```py
  odds = [1,3, 5, 7]
  primes = list(odds)
  primes.append(2)
  print('primes:', primes)
  print('odds:', odds)
  ```



## Analyzing Data from Multiple Files

#### Questions:
- How can I do the same operations on many different files?

#### Notes:
- Use the `glob` library for working with files, directories, and file paths.
- Use `glob/glob(pattern)` to create a list of files that match the pattern
- Use `*` in a pattern to match 0 or more characters (of any kind) and `?` to match a single character


#### Activity:
- [ ] Import the `glob` library
  ```py
  import glob
  ```

- [ ] Use `glob.glob` to list the inflammation data files in the current directory
  ```py
  print(glob.glob('inflammation*.csv'))
  ```

- [ ] Make inline graphs for the first 3 inflammation data files
  ```py
  import numpy
  import matplotlib.pyplot

  %matplotlib inline

  filenames = sorted(glob.glob('inflammation*.csv'))
  filenames = filenames[0:3]

  for f in filenames:
    print(f)

    data = numpy.loadtxt(fname=f, delimiter=',')
    fig = matplotlib.pyplot.figure(figsize=(10.0, 3.0))

    axes1 = fig.add_subplot(1, 3, 1)
    axes2 = fig.add_subplot(1, 3, 2)
    axes3 = fig.add_subplot(1, 3, 3)

    axes1.set_ylabel('average')
    axes1.plot(numpy.mean(data, axis=0))

    axes2.set_ylabel('max')
    axes2.plot(numpy.max(data, axis=0))

    axes3.set_ylabel('min')
    axes3.plot(numpy.min(data, axis=0))

    fig.tight_layout()
    matplotlib.pyplot.show()
  ```


## Making Choices

#### Questions:
- How can my programs do different things based on data values?


#### Notes:
- `if`, `elif`, and `else` are conditionals for __control flow__
- You can combine conditionals with `and` and `or`
  ```py
  if (a > 1) and (b == 5):
    # do something
  ```
- `True` and `False` have the data type __boolean__. They are the only __booleans__.

#### Try:

- [ ] Try out an `if / else`
  ```py
  num = 37
  if num > 100:
    print('greater')
  else:
    print('not greater')
  print('done')
  ```
- [ ] Try without an `else`
  ```py
  num = 53
  print('before conditional...')
  if num > 100:
    print(num, 'is greater than 100')
  print('... after conditional')
  ```

- [ ] Chain several tests with `elif`
  ```py
  num = -3
  if num > 0:
    print(num, 'is positive')
  elif num == 0:
    print(num, 'is zero')
  else:
    print(num, 'is negative')
  ```

- [ ] Combine tests with `and`
  ```py
  if (1 > 0) and (-1 < 0):
    print('both parts are true')
  else:
    print('at least one part is false')
  ```

- [ ] Try with `or`
  ```py
  if (1 < 0) or (-1 < 0):
    print('at least one test is true')
  ```

#### Activity

- [ ] Use conditionals to check for suspicious features in the inflammation data. Start by checking the maximum inflammation at the beginning (on day 0) and in the middle (day 20) of the study to see if they're equal to their corresponding day numbers.
  ```py
  max_inflammation_0 = numpy.max(data, axis=0)[0]
  max_inflammation_20 = numpy.max(data, axis=0)[20]

  if max_inflammation_0 == 0 and max_inflammation_20 == 20:
    print('Suspicious looking maxima!')
  ```

- [ ] Also check if a healthy person snuck into the data set by looking for minima per day that were all zero
  ```py
  elif numpy.sum(numpy.min(data, axis=0)) == 0:
    print('Minima add up to zero!')
  ```

- [ ] Lastly, add an else to print if everything looks okay
  ```py
  else:
    print('Seems OK!')
  ```

- [ ] Run the whole conditional with `inflammation-01.csv`
  ```py
  data = numpy.loadtxt(fname='inflammation-01.csv', delimiter=',')

  max_inflammation_0 = numpy.max(data, axis=0)[0]
  max_inflammation_20 = numpy.max(data, axis=0)[20]

  if max_inflammation_0 == 0 and max_inflammation_20 == 20:
    print('Suspicious looking maxima!')
  elif numpy.sum(numpy.min(data, axis=0)) == 0:
    print('Minima add up to zero!')
  else:
    print('Seems OK!')
  ```

- [ ] And again with `inflammation-03.csv`
  ```py
  data = numpy.loadtxt(fname='inflammation-03.csv', delimiter=',')

  max_inflammation_0 = numpy.max(data, axis=0)[0]
  max_inflammation_20 = numpy.max(data, axis=0)[20]

  if max_inflammation_0 == 0 and max_inflammation_20 == 20:
    print('Suspicious looking maxima!')
  elif numpy.sum(numpy.min(data, axis=0)) == 0:
    print('Minima add up to zero!')
  else:
    print('Seems OK!')
  ```

## Creating Functions

#### Questions:
- How can I define new functions?
- What’s the difference between defining and calling a function?
- What happens when I call a function?

#### Notes:
- Define a __function__ with
  ```py
  def function_name(parameter):
    # do or return something
  ```
- Document functions with __doctrings__ `'''Example'''`
- Utilize parameter __defaults__
- Use `help(function_name)` to look at the documentation for a function

### Try:
- [ ] Define a function for converting Fahrenheit to Celsius
  ```py
  def fahr_to_celsius(temp):
    return ((temp - 32) * (5/9))
  ```

- [ ] Run the function you defined
  ```py
  fahr_to_celsius(32)
  ```

- [ ] Call the function and print it
  ```py
  print('freezing point of water:', fahr_to_celsius(32), 'C')
  print('boiling point of water:', fahr_to_celsius(212), 'C')
  ```

- [ ] Define a new function to convert Celsius to Kelvin
  ```py
  def celsius_to_kelvin(temp_c):
    return temp_c + 273.15

  print('freezing point of water in Kelvin:', celsius_to_kelvin(0.0))
  ```

- [ ] Use our existing conversion functions to define one for Fahrenheit to Kelvin
  ```py
  def fahr_to_kelvin(temp_f):
    temp_c = fahr_to_celsius(temp_f)
    temp_k = celsius_to_kelvin(temp_c)
    return temp_k

  print('boiling point of water in kelvin:', fahr_to_kelvin(212.0))
  ```

#### Activity:
- [ ] Turn the inflammation plotting analysis into a reusable function:
  ```py
  def analyze(filename):
    data = numpy.loadtxt(fname=filename, delimiter=',')
    fig = matplotlib.pyplot.figure(figsize=(10.0, 3.0))

    axes1 = fig.add_subplot(1, 3, 1)
    axes2 = fig.add_subplot(1, 3, 2)
    axes3 = fig.add_subplot(1, 3, 3)

    axes1.set_ylabel('average')
    axes1.plot(numpy.mean(data, axis=0))

    axes2.set_ylabel('max')
    axes2.plot(numpy.max(data, axis=0))

    axes3.set_ylabel('min')
    axes3.plot(numpy.min(data, axis=0))

    fig.tight_layout()
    matplotlib.pyplot.show()
  ```

- [ ] Write a fuction to detect problems in the data
  ```py
  def detect_problems(filename):
    data = numpy.loadtxt(fname=filename, delimiter=',')

    if numpy.max(data, axis=0)[0] == 0 and numpy.max(data, axis=0)[20] == 20:
      print('Suspicious looking maxima!')
    elif numpy.sum(numpy.min(data, axis=0)) == 0:
      print('Minima add up to zero!')
    else:
      print('Seems OK!')
  ```

- [ ] Put the functions `analyze` and `detect_problems` together in a loop that goes through the first 3 of the inflammation files
  ```py
  filenames = sorted(glob.glob('inflammation*.csv'))

  for f in filenames[:3]:
    print(f)
    analyze(f)
    detect_problems(f)
  ```
- [ ] Write a function to offset the mean to a user-defined value
  ```py
  def offset_mean(data, target_mean_value):
    return (data - numpy.mean(data)) + target_mean_value
  ```

- [ ] Test the function on a small sample set of data to make sure it does what we'd expect
  ```py
  z = numpy.zeros((2,2
  print(z)
  print(offset_mean(z, 3))
  ```

- [ ] Test `offset_mean` on the real inflammation data
  ```py
  data = numpy.loadtxt(fname='inflammation-01.csv', delimiter=',')
  print(offset_mean(data, 0))
  ```

- [ ] Write some checks to see if the result is feasible
  ```py
  print('original min, mean, and max are:', numpy.min(data), numpy.mean(data), numpy.max(data))
  offset_data = offset_mean(data, 0)
  print('min, mean, and max of offset data are:', numpy.min(offset_data), numpy.mean(offset_data), numpy.max(offset_data))
  ```
- [ ] Check to make sure the standard deviation hasn't changed
  ```py
  print('std dev before and after:', numpy.std(data), numpy.std(offset_data))
  ```
- [ ] Make a more precise check by outputing the difference in standard deviations
  ```py
  print('difference in standard deviations before and after:', numpy.std(data) - numpy.std(offset_data))
  ```
- [ ] Add documentation to explain the function with `# comments`
  ```py
  # offset_mean(data, target_mean_value):
  # return a new array containing the original data with its mean offset to match the desired value
  def offset_mean(data, target_mean_value):
    return (data - numpy.mean(data)) + target_mean_value
  ```

- [ ] Redo the documentation with multiline __docstring__ `'''`
  ```py
  def offset_mean(data, target_mean_value):
    '''Return a new array containing the original data
      with its mean offset to match the desired value.
     Example: offset_mean([1, 2, 3], 0) => [-1, 0, 1]'''
    return (data - numpy.mean(data)) + target_mean_value
  ```

- [ ] Show the docstring with
  ```py
  help(offset_mean)
  ```

- [ ] Try using `numpy.loadtxt()` without labelling the filename with `fname`. Does it work?
  ```py
  numpy.loadtxt('inflammation-01.csv', delimiter=',')
  ```

- [ ] Try using `numpy.loadtxt()` without labelling the `delimiter`. Does it work?
  ```py
  numpy.loadtxt('inflammation-01.csv', ',')
  ```

- [ ] Redefine `offset_mean` to have a default `target_mean_value`
  ```py
  def offset_mean(data, target_mean_value=0.0):
    '''Return a new array containing the original data with its mean offset
       to match the desired value (0 by default)
    Example: offset_mean([1, 2, 3], 0) => [-1, 0, 1]```
  ```

- [ ] Call the new version of `offset_mean` with two parameters, as before
  ```py
  test_data = numpy.zeros((2, 2))
  print(offset_data(test_data, 3))
  ```

- [ ] Call the new version of `offset_mean` with only one parameter (the data) on a new set
  ```py
  more_data = 5 + numpy.zeros((2,2))
  print('data before offset:')
  print(more_data)
  print('offset data:')
  print(offset_mean(more_data))
  ```

- [ ] Write a new function with multiple defaults
  ```py
  def display(a=1, b=2, c=3):
    print('a:', a, 'b:', b, 'c:', c)

  print('no parameters:')
  display()
  print('one parameter:')
  display(55)
  print('two parameters:')
  display(55, 66)
  ```

- [ ] Try by explicitly setting the value of `c`
  ```py
  print('only setting the value of c:'
  display(c=77)
  ```

- [ ] Look carefully at the documentation for `numpy.loadtxt` and its defaults. Notice that `fname` does not have a default (a specific filename is required) and eight other parameters that do have defaults (can be omitted)
  ```py
  help(numpy.loadtxt)
  ```
- [ ] Try running `numpy.loadtxt` without labelling the `delimiter` again. Without the label, what value does the function think `','` is for?
  ```py
  numpy.loadtxt('inflammation-01.csv', ',')
  ```

## Errors and Exceptions

#### Questions:
- How does Python report errors?
- How can I handle errors in Python programs?

#### Try:
- [ ] Write out the following function, which has an intentional error:
  ```py
  # This
  ```


## Defensive Programming

#### Questions:
- How can I make my programs more reliable?






## Debugging

#### Questions:
- How can I debug my program?





## Command-Line Programs

#### Questions:
- How can I write Python programs that will work like Unix command-line tools?
