# LAB REPORT TWO
Aidan Fuller <br>
4/24/2024
---
# Chat Server - Part 1 
---
## Code
```
public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return "Welcome to ChatServer!";
        } else if (url.getPath().equals("/add-message")) {
            String query = url.getQuery();
            if (query != null) {
                String[] pairs = query.split("&");
                String user = null;
                String message = null;
                for (String pair : pairs) {
                    String[] keyValue = pair.split("=");
                    if (keyValue.length == 2) {
                        if (keyValue[0].equals("message") && keyValue[1].equals("user")) {
                            String.format(keyValue[0], ":", keyValue[1]);
                        }
                    }
                }
            } 
        }
        return "Error!";
    }
}

class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new ChatHandler());
    }
}
```
**I was unable to get a fully working server, but I have written samples for what my code intends to do.

## Message One
`/add-message?s=Howdy&user=aifuller` <br>
Expected to output ` aifuller: Howdy `
### Methods Called
getQuery - determine the query in the search bar <br>
query.split - divides the search bar query into two different sections, the user and the message text <br>
pair.split - splits each term in the search bar query into the query name and the value of the query 
### Relevant Arguments
the `message` is updated to the value "Howdy" <br>
the `user` is updated to the value "aifuller" <br>
the `URI` is also updated, as now the path to the webpage includes the `/add-message` portion with the specified `message` and `user`

## Message Two
`/add-message?s=Nice to see you!&user=jjfuller` <br>
Expected to output ` jjfuller: Nice to see you! ` <br>

Full page 
```  
aifuller: Howdy
jjfuller: Nice to see you!  `
```
### Methods Called
Same methods as before, as we are just calling the method again and adding a new message line <br>
getQuery - determine the query in the search bar <br>
query.split - divides the search bar query into two different sections, the user and the message text <br>
pair.split - splits each term in the search bar query into the query name and the value of the query 
### Relevant Arguments
The same arguments are used, but since it is a new line with a new message, different values are assigned to each of them <br>
the `message` is now updated to the value "Nice to see you!" <br>
the `user` is now updated to the value "jjfuller" <br>
the `URI` is also updated, as now the path to the webpage includes the `/add-message` portion with the specified `message` and `user`



---
# Part 2 
---
## Absolute Path to Local Private Key: 
![LocalKey](Screenshot_LocalKey) <br>

## Absolute Path to ieng6 Public Key:
![RemoteKey](Screenshot_RemoteKey) <br>

## Terminal Interaction Without Password: 
![Login](Screenshot_Login) <br>

---
# Part 3
---
One thing that was interesting to me is the use of keys to sign into the server. I know of websites using hashing to encrypt passwords and compare the encriptions to each other for extra levels of security but I didn't know about server logins like the `ieng6` one we are using and how it can generate key pairs to make signing into the server easier and more secure. 



