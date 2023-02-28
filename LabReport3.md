# Lab Report 3
by Dylan Habecker

## Using `less` Command

Using the `less` as follows: `$ less skill-demo1-data/written_2/non-fiction/OUP/Berk/ch1.txt` displays the contents of the file `ch1.txt`.

<img width="1792" alt="Screen Shot 2023-02-26 at 8 42 14 PM" src="https://user-images.githubusercontent.com/22578356/221770676-9f3f917e-5f01-461e-8c07-2d068583b2bd.png">

As we can see this isn't super helpful since there is so much information. 

To make our life easier we'll use the `-N` option to add line numbers to the output:

<img width="1792" alt="Screen Shot 2023-02-26 at 9 03 54 PM" src="https://user-images.githubusercontent.com/22578356/221478682-f0d491b0-6b1e-45be-8b36-5f0d50bc88d3.png">

## `less` Commands

### `/pattern` command

While both `less` and `cat` display the contents of a file, `less` allows us to search through the file contents using different commands.
The first command we will use is `/pattern`.

Here is the result when searching by `/children`:

<img width="1792" alt="Screen Shot 2023-02-26 at 9 22 04 PM" src="https://user-images.githubusercontent.com/22578356/221480992-81087a8f-32c1-41bf-94d7-24635414e042.png">

The pattern that we searched for is now highlited in the terminal allowing us to locate specific strings more easily.

Here is another example searching the file `skill-demo1-data/written_2/non-fiction/OUP/Castro/chA.txt` for `/Mexican`:

<img width="1792" alt="Screen Shot 2023-02-26 at 9 26 31 PM" src="https://user-images.githubusercontent.com/22578356/221481686-23617f10-3535-4f59-9dea-dda2b1ac543e.png">

### `Ng` Command

If we know the line number of file that contains the information we want we can use the `Ng` command:
First we'll search the file `skill-demo1-data/written_2/non-fiction/OUP/Berk/ch1.txt` for the 100th line:

<img width="1792" alt="Screen Shot 2023-02-26 at 9 30 40 PM" src="https://user-images.githubusercontent.com/22578356/221482220-7f33b78f-e1e2-44f8-ab2b-fc345ab3eeb7.png">

And here we are searching for the 75th line of `skill-demo1-data/written_2/non-fiction/OUP/Castro/chA.txt`:

<img width="1792" alt="Screen Shot 2023-02-26 at 9 31 16 PM" src="https://user-images.githubusercontent.com/22578356/221482306-adfac5a3-a250-450a-881c-ca27deadfa28.png">

### Piping to `less`

The less command can also be piped to making it easier to navigate other commands such as the `ls` command.
Let's try `ls -l | less`:

<img width="600" alt="Screen Shot 2023-02-27 at 9 49 25 PM" src="https://user-images.githubusercontent.com/22578356/221765641-2fcabf4b-b6ee-44a0-85ae-2b9922eb61f8.png">

Here we can see the output of the `ls` command from our home directory. With large directories this could be a very useful tool.
Now we will pipe a list of all `.txt` files in our directories to less using `find . -name *.txt | less`:

<img width="561" alt="Screen Shot 2023-02-27 at 9 52 58 PM" src="https://user-images.githubusercontent.com/22578356/221766421-e2651f42-0e1f-4b8c-9be9-31e402a02622.png">

Using the commands we learned about earlier we'll have an easier time navigating through this long list of `.txt` files.

### `less -X` Command

Say we want to view the contents of a file but don't want to keep opening and closing it everytime we need to take a look. 
Luckily for us `less` has an option we can use to keep the contents of the file on the screen after we exit `less`. 

Here we'll use `ls -l | less -X` to display the current home directory on the ternimal:

<img width="673" alt="Screen Shot 2023-02-27 at 9 59 35 PM" src="https://user-images.githubusercontent.com/22578356/221767991-f920e42d-9980-4792-854f-2d73c3ee1fed.png">

This is handy if we need to constantly know this information.

We can also add the `-N` option to add numberlines to our terminal output. `find . -name *.txt | less -X -N`:

<img width="516" alt="Screen Shot 2023-02-27 at 10 01 00 PM" src="https://user-images.githubusercontent.com/22578356/221768197-ac0dd164-671f-4448-9982-ff17d06f19fb.png">

### Sources

I used the `man less` command to view all of the options and commands associated with `less`. 
I also utilized ChatGPT to give me a description and use cases for the `less` command.

Here are my prompts and answers from ChatGPT

Prompt: "how do you use the mark feature of the less command in linux"
Response: 

<img width="576" alt="Screen Shot 2023-02-27 at 10 11 55 PM" src="https://user-images.githubusercontent.com/22578356/221769494-7a9d05bc-6239-4879-927e-f5e684da775b.png">

Prompt: "what else can the less command do?"
Response:

<img width="584" alt="Screen Shot 2023-02-27 at 10 12 33 PM" src="https://user-images.githubusercontent.com/22578356/221769517-768d7233-c500-4aa8-bb3e-d826088301d4.png">

Prompt: "how to find all txt files in a directory"
Response: 

<img width="586" alt="Screen Shot 2023-02-27 at 10 12 52 PM" src="https://user-images.githubusercontent.com/22578356/221769530-e54fe55c-a5f8-4951-b01d-1fd6a81cd4b3.png">

For each of ChatGPT's responses I took the code example it gave and used that as a foundation to write my commands in terminal. 


