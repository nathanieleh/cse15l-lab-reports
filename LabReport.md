# Lab Report 2 - Servers and Bugs
## Part 1
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String serverString = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return serverString;
        } else if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                serverString += parameters[1] + "\n";
                return serverString;
            }
        }
        return "404 Not Found!";
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if (args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```

### /add-message #1

![Image](First_Saved_Message%20(2).png)

Relevant methods called in the program

`handleRequest(URI url)`

* Returns:
`message number 1`
* value of url: `localhost:4000/add-message?s=message%20number%201`
* url remains constant throughout the program since this parameter is only set once at the beginning of the method
* this method will modify `serverString` throughout the process whenever the user uses `/add-message` as the path

`getPath()`

* Return value: `/add-message`
* since this is ran under the previous method, url will call this method throughout the program which means it will return url's path every time
* no values will be modified when using this method since it is only meant to return the path of the URI object

`equals(Object o)`

* Return value: true if the object calling this method and the object in the parameter are equal, false otherwise
* Input: this method is used twice where it compares the url path to `/` (which is false) and the first query of url to `s` (which is true)
* no values will be modified when using this method since it is only meant to return whether or not the two objects are equal

`contains(Object o)`

* Return value: true if the object calling this method contains the object in the parameter
* Input: this method is only used once to see if url's path contains the String `/add-message` (which is true)
* no values will be modified when using this method since it is only meant to return whether or not the first object contains the input object

`getQuery()`

* Return value: `s=message%20number%201`
* since this is ran under the first method, url will be calling this method which means it will return url's query every time
* no values will be modified when using this method since it is only meant to return the query of the URI object

`split(String s)`

* Return value: { s, message%20number%201 }
* when this method is called, it saves all values regarding the query of the url so the programmer can seperate the type of query with the inputs given
* `parameters` will be modified since the return value of this method is meant to return a String[]

### /add-message #2

![Image](Second_Saved_Message.png)

Relevant methods called in the program

`handleRequest(URI url)`

* Returns:

```
message number 1

another message saved
```

* value of url: `localhost:4000/add-message?s=another%20message%20saved`
* url remains constant throughout the program since this parameter is only set once at the beginning of the method
* this method will modify `serverString` throughout the process whenever the user uses `/add-message` as the path

`getPath()`

* Return value: `/add-message`
* since this is ran under the previous method, url will call this method throughout the program which means it will return url's path every time
* no values will be modified when using this method since it is only meant to return the path of the URI object

`equals(Object o)`

* Return value: true if the object calling this method and the object in the parameter are equal, false otherwise
* Input: this method is used twice where it compares the url path to `/` (which is false) and the first query of url to `s` (which is true)
* no values will be modified when using this method since it is only meant to return whether or not the two objects are equal

`contains(Object o)`

* Return value: true if the object calling this method contains the object in the parameter
* Input: this method is only used once to see if url's path contains the String `/add-message` (which is true)
* no values will be modified when using this method since it is only meant to return whether or not the first object contains the input object

`getQuery()`

* Return value: `s=another%20message%20saved`
* since this is ran under the first method, url will be calling this method which means it will return url's query every time
* no values will be modified when using this method since it is only meant to return the query of the URI object

`split(String s)`

* Return value: { s, another%20message%20saved }
* when this method is called, it saves all values regarding the query of the url so the programmer can seperate the type of query with the inputs given
* `parameters` will be modified since the return value of this method is meant to return a String[]

## Part 2
I will choose `reverseInPlace(int[] arr)` from the ArrayExamples.java file

```
public class ArrayExamplesTester {
    @Test
    public void reverseInPlaceTester() {
        // failure inducing input
        int[] input1 = { 0, 1, 2, 3 };
        ArrayExamples.reverseInPlace(input1);
        assertArrayEquals(new int[] { 3, 2, 1, 0 }, input1);

        // successful input
        int[] input2 = { 0 };
        ArrayExamples.reverseInPlace(input2);
        assertArrayEquals(new int[] { 0 }, input2);
    }
}
```

## Part 3
