# LAB REPORT TWO
---
## Chat Server - Part 1 
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
## Part 2 
---
Absolute Path to Local Private Key: 

Absolute Path to ieng6 Public Key:

Terminal Interaction Without Password: 

---
## Part 3
---




