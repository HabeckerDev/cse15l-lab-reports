# Lab Report 5
### By Dylan Habecker

## Using `jdb` to gather information from `StringServer.java` while running

This command was tricky to learn. I first took a look at the Oracle command information to learn how to use it.

First attempt:

<img width="656" alt="Screen Shot 2023-03-13 at 10 48 38 PM" src="https://user-images.githubusercontent.com/22578356/224915190-49834a5f-d1f9-4540-808a-f85173a7eb1f.png">

Here I was running into issues because I hadn't locally compiled the `StringServer.java` file. I didn't think this was necessary because the git repository I cloned contained the `StringServer.class` file already.

Next I asked ChatGPT for some advice:

<img width="628" alt="Screen Shot 2023-03-13 at 10 55 12 PM" src="https://user-images.githubusercontent.com/22578356/224915481-1b042ec4-fe1e-4365-889e-9279815e0917.png">

It gave me some advice on how to run the the program while being able to specify a port number for the server. Unfortunetly these instructions weren't completely correct for my situation.

<img width="443" alt="Screen Shot 2023-03-13 at 10 56 57 PM" src="https://user-images.githubusercontent.com/22578356/224916003-137f119e-0b05-4616-a86e-2c04230417b4.png">

<img width="660" alt="Screen Shot 2023-03-13 at 11 08 57 PM" src="https://user-images.githubusercontent.com/22578356/224916090-146e0211-58b4-474c-92ac-2275496555bf.png">

After some trial and error I discovered that I needed to enter the port number when executing `jdb`.
So I tried running `jdb StringServer 4006`:

<img width="470" alt="Screen Shot 2023-03-13 at 11 16 47 PM" src="https://user-images.githubusercontent.com/22578356/224916189-4ae1d03a-e917-4660-8436-110009dae7a1.png">

Here I was successfully able to run the `jdb` command and start the `StringServer` program correctly.

Now it was time to gather some information about the server while it was running.
I discovered that in order to run the `locals` command that displays variable information, I needed to be in a `thread`. 
I used the command `threads` to display the list of threads:

<img width="603" alt="Screen Shot 2023-03-13 at 11 23 18 PM" src="https://user-images.githubusercontent.com/22578356/224916660-25357b3e-c6e7-4833-9252-1bc0607f8939.png">

After this I had to restart the server due to my connection with the UCSD wifi being interrupted. This time I ran the command `jdp StingServer 4008`. I also recompiled every `.java` file with `javac -g *.java` to compile with debuggin information. 

<img width="660" alt="Screen Shot 2023-03-13 at 11 29 10 PM" src="https://user-images.githubusercontent.com/22578356/224917087-0819fb54-8342-45ed-8e64-2cc329d29c85.png">

When trying to run `locals` I learned that I needed to suspend the thread inorder to extract data from it.
However, even after compiling with `-g` I still couldn't get the `locals` command to execute properly. 

Even though I wasn't able to complete all of my goals using `jdp` I learned a lot about how it interacts with servers and command-line arguments for programs we are debugging. 
