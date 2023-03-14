# Lab Report 4
### By Dylan Habecker

## Step 4: Log into ieng6 server
Open up a terminal and type `ssh cs15lwi23atm@ieng6.ucsd.edu`. Press `<enter>`.

<img width="680" alt="Screen Shot 2023-03-12 at 6 29 19 PM" src="https://user-images.githubusercontent.com/22578356/224593017-471d64b2-a66e-4eac-aa2b-70693a21d297.png">

## Step 5: Clone your fork of the repository from your Github account
Type `git clone git@github.com:HabeckerDev/lab7.git`. Press `<enter>`.

<img width="553" alt="Screen Shot 2023-03-12 at 6 34 38 PM" src="https://user-images.githubusercontent.com/22578356/224592981-40f39ab2-d6d1-423c-98e3-59ad88ca7994.png">

## Step 6: Run the tests from `ListExamplesTests.java` and demonstrate that they fail
Type `cd la` and press `<tab>` to autocomplete to `cd lab7/`. Press `<enter>`.
I have thes commands saved to a seperate file so I highlight the command and press `<command><c>` and `<command><v>` in the terminal to paste: `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`. They should execute automatically after pasting into the terminal.

<img width="650" alt="Screen Shot 2023-03-12 at 6 55 54 PM" src="https://user-images.githubusercontent.com/22578356/224592948-093eb065-d9f5-4d12-9cf8-40be647bacd5.png">

## Step 7: Edit `ListExamples.java` so that it passes the tests
Type `nano ListExamples.java` and press `<enter>` in the terminal. 
Too fix the code I had to navigate with the arrow keys down to line 43 containing the code `index1 += 1;` and switch the `1` to a `2`.

Keys pressed: `<down>` 42 times. `<right>` 12 times. `<delete>` once, and type `2`.
Press `<control><X>` to exit nano. When prompted type `y` and press `<enter>`. This will save the changes and close out nano.

<img width="644" alt="Screen Shot 2023-03-12 at 7 06 08 PM" src="https://user-images.githubusercontent.com/22578356/224592908-57e65ed1-99c3-40e2-b452-170d19c02a52.png">

## Step 8: Run the tests again and demonstrate that the code passes
Press `<up><up><up><enter>` to run the command `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` that we ran earlier. 
Press `<up><up><up><enter>` to run the command `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` that we ran earlier. Since both of these commands are stored in the terminal's memory we can access them using the `<up>` key.

<img width="641" alt="Screen Shot 2023-03-12 at 7 11 55 PM" src="https://user-images.githubusercontent.com/22578356/224592868-902b1fc5-ef82-4290-829d-ea7db9f370b7.png">

## Step 9: Commit and push the resulting change to your Github acount (Pick a commit message)
Type `git commit -a -m fixed` and press `<enter>`. Type `git push` and press `<enter>`. The git message we chose was `fixed`. 

<img width="585" alt="Screen Shot 2023-03-12 at 7 13 56 PM" src="https://user-images.githubusercontent.com/22578356/224592846-0a5e1d44-e69f-41ff-98a1-4c7283038f3f.png">


