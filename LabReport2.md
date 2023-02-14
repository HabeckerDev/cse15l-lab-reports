# Lab Report 2
by Dylan Habecker

## StringServer Web Server
Implementation of a Web Server that adds strings to an ArrayList and displays the Strings on the webpage.

The following is the source code for StringServer.java

```

import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    ArrayList<String> message = new ArrayList<>();
    
    public String handleRequest(URI url) throws IOException{
        StringBuilder result = new StringBuilder();
        if(url.getPath().equals("/")){
            return "add-message?s=<string>";
        }
        if(url.getPath().contains("/add-message")){
            String[] parameters = url.getQuery().split("=");
            if(parameters[0].equals("s")){
                
                message.add(parameters[1]);

                for(int i = 0; i < message.size(); i++){
                    result.append(message.get(i).toString() + "\n");
                }
                return result.toString();
            }
            else {
                return "Couldn't find query parameter s";
            }
        }
        else {
            return "Don't know how to handle that path!";
        }
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }
        
        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}


```
Here is a screenshot of inpututing 3 separate strings in the URL.

<img width="585" alt="Screen Shot 2023-02-13 at 10 24 38 PM" src="https://user-images.githubusercontent.com/22578356/218656577-75da5537-8d45-4634-95fd-4f0686d87604.png">


And this is the continuation.

<img width="585" alt="Screen Shot 2023-02-13 at 10 25 31 PM" src="https://user-images.githubusercontent.com/22578356/218656594-153400ea-3693-4e2a-9690-85202edc5f62.png">

To run the server you have to specify a port number like so:
`java StringServer 4500`
Doing this starts the server and allows us to visit the webpage at: 
`http://localhost:4500/`

Our web server works by reading the string entered after `/add-message?s=` in the URL. This is done by the handleRequest method in the Handler class.
The strings are stored in an ArrayList and when the webpage is called again it displays every string in the ArrayList separated by a new line.
This is all done by the Handler class.

## Lab 3 Bugs

Testing the `ReverseInPlace` method:

```

@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);

    int[] input2 = new int[]{1,2,3};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{3,2,1}, input2); 
    
	}

```
The JUnit test failed with the following information:
`There was 1 failure:`
`1) testReverseInPlace(ArrayTests)
arrays first differed at element [2]; expected:<1> but was:<3>`

The input `{3}` passed while the input `{3,2,1}` failed.

Here is a screenshot of the JUnit test running:

<img width="1440" alt="Screen Shot 2023-02-13 at 11 16 35 PM" src="https://user-images.githubusercontent.com/22578356/218665905-eb2bdb3a-9143-4637-bb19-eccf0e7cdef1.png">

Here is the buggy code:

```
// Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
  
```

And here is the fixed code:

```

 static void reverseInPlace(int[] arr) {
    int[] temp = new int[arr.length];
      for(int i = 0; i < arr.length; i++){
        temp[i] = arr[i];
      }
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = temp[temp.length - i - 1];
    }
  }
  
```

The fixed code copies the original array into a temporary array of the same size. 
Then the second for loop copies the temporary array back into the original array in reverse order. 
This allows us to reverse the array while maintaining every value in the original array.


## What I learned

My biggest accomplishment for the last 2 labs has been making a working webserver. 
While I've written plenty of code that manipulates strings and other objects, I have never created a way for others to use it outside of the terminal.
I also learned how to use JUnit more efficiently when writing test for my code.
This will come in handy while I work on my CSE12 PAs.
