# Lab Report 3
by Dylan Habecker

## Using `less` Command

Using the `less` as follows: `$ less skill-demo1-data/written_2/non-fiction/OUP/Berk/ch1.txt` displays the contents of the file `ch1.txt`.

![Screen Shot 2023-02-26 at 8.42.14 PM.png](https://github.com/HabeckerDev/cse15l-lab-reports/blob/main/Screen%20Shot%202023-02-26%20at%208.42.14%20PM.png)

As we can see this isn't super helpful since there is so much information. 

To make our life easier we'll use the `-N` option to add line numbers to the output:

<img width="1792" alt="Screen Shot 2023-02-26 at 9 03 54 PM" src="https://user-images.githubusercontent.com/22578356/221478682-f0d491b0-6b1e-45be-8b36-5f0d50bc88d3.png">

## `less` Commands

While both `less` and `cat` display the contents of a file, `less` allows us to search through the file contents using different commands.
The first command we will use is `/pattern`.

Here is the result when searching by `/children`:

<img width="1792" alt="Screen Shot 2023-02-26 at 9 22 04 PM" src="https://user-images.githubusercontent.com/22578356/221480992-81087a8f-32c1-41bf-94d7-24635414e042.png">

The pattern that we searched for is now highlited in the terminal allowing us to locate specific strings more easily.

Here is another example searching the file `skill-demo1-data/written_2/non-fiction/OUP/Castro/chA.txt` for `/Mexican`:

<img width="1792" alt="Screen Shot 2023-02-26 at 9 26 31 PM" src="https://user-images.githubusercontent.com/22578356/221481686-23617f10-3535-4f59-9dea-dda2b1ac543e.png">

If we know the line number of file that contains the information we want we can use the `Ng` command:
First we'll search the file `skill-demo1-data/written_2/non-fiction/OUP/Berk/ch1.txt` for the 100th line:

<img width="1792" alt="Screen Shot 2023-02-26 at 9 30 40 PM" src="https://user-images.githubusercontent.com/22578356/221482220-7f33b78f-e1e2-44f8-ab2b-fc345ab3eeb7.png">

And here we are searching for the 75th line of `skill-demo1-data/written_2/non-fiction/OUP/Castro/chA.txt`:

<img width="1792" alt="Screen Shot 2023-02-26 at 9 31 16 PM" src="https://user-images.githubusercontent.com/22578356/221482306-adfac5a3-a250-450a-881c-ca27deadfa28.png">







