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
<img width="620" alt="Screen Shot 2023-02-13 at 10 25 31 PM" src="https://user-images.githubusercontent.com/22578356/218656594-153400ea-3693-4e2a-9690-85202edc5f62.png">

To run the server you have to specify a port number like so:
`java StringServer 4500`
Doing this starts the server and allows us to visit the webpage at: 
`http://localhost:4500/`

Our web server works by reading the string entered after `/add-message?s=` in the URL. This is done by the handleRequest method in the Handler class.
The strings are stored in an ArrayList and when the webpage is called again it displays every string in the ArrayList separated by a new line.
This is all done by the Handler class.


