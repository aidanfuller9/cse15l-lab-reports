# LAB REPORT TWO
---
# Chat Server - Part 1 
---
## Code
```
public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Welcome to ChatSever!");
        }
        else if (url.getPath().contains("/add-message")) {
            String query = url.getQuery();
            if (query != null) {
                String[] parameters = query.split("&");
                String s = null;
                String user = null;
                for (String parameter : parameters) {
                    String[] keyValue = parameter.split("=");
                    if (keyValue.length == 2) {
                        if (keyValue[0].equals("s")) {
                            s = keyValue[1];
                        } else if (keyValue[0].equals("user")) {
                            user = keyValue[1];
                        }
                    }
                }
            }
        }
        return "Error";
    }
```

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



