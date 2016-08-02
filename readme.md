#Design Prototypes with a Real Database
This template enables you to quickly spin up a new application that is powered by a real database. This allows you to not only separate data from your design, but also gives you persistent data with which you can create multi-screen prototypes and workflows.

##Steps to Reproduce
+ Open terminal
+ Clone or download repo to your local machine
+ Navigate into your new repository via terminal
+ Start a simple server: `python -m SimpleHTTPServer 8000`

+ Spin up new Firebase Project : https://firebase.google.com/
+ Insert new Firebase Database URL into index.html placeholders for both read and write access.
+ Configure Firebase DB Rules to the following to allow read/write access: 
    ```
    {
      "rules": {
        ".read": "auth == null",
        ".write": "auth == null"
      }
    }
    ```

+ Test connection to DB by adding a new task and seeing the task inside your Firebase console