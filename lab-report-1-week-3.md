```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String string = "";
    ArrayList<String> string2 = new ArrayList<>();
    ArrayList<String> searchResults = new ArrayList<>();
    
    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("String: %s", string2.toString());
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    string2.add(parameters[1]);
                    return String.format("%s was added to list!", parameters[1]);
                } 
            }
            else {
                String[] parameters2 = url.getQuery().split("=");
                for (int i = 0; i < string2.size(); i++){
                    if (string2.get(i).contains(parameters2[1])){
                        searchResults.add(string2.get(i));
                    }
                }
                return String.format("String: %s", searchResults.toString());
            }
            return "404 Not Found!";
        }
    }
}

class NumberServer {
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