# Lab Report 4
### By Dylan Habecker

## Step 4: 
Open up a terminal and type `ssh cs15lwi23atm@ieng6.ucsd.edu`. Press `<enter>`.

## Step 5:
Type `git clone git@github.com:HabeckerDev/lab7.git`. Press `<enter>`.

## Step 6:
Type `cd la` and press `<tab>` to autocomplete to `cd lab7/`. Press `<enter>`.
I have thes commands saved to a seperate file so I highlight the command and press `<command><c>` and `<command><v>` in the terminal to paste: `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`. They should execute automatically after pasting into the terminal.

## Step 7:
Type `nano ListExamples.java` and press `<enter>` in the terminal. 
Too fix the code I had to navigate with the arrow keys down to line 43 containing the code `index1 += 1;` and switch the `1` to a `2`.

Keys pressed: `<down>` 42 times. `<right>` 12 times. `<delete>` once, and type `2`.
Press `<control><X>` to exit nano. When prompted type `y` and press `<enter>`. This will save the changes and close out nano.

## Step 8: 
Press `<up><up><up><enter>` to run the command `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` that we ran earlier. 
Press `<up><up><up><enter>` to run the command `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` that we ran earlier.

## Step 9:
Type `git commit -a -m fixed` and press `<enter>`. Type `git push` and press `<enter>`.



