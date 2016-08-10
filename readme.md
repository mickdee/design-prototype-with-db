#Design Prototypes with a Database
This template enables you to quickly spin up a new application that is powered by a real database. This allows you to not only separate data from your design, but also gives you persistent data with which you can create multi-screen prototypes and workflows.

### Notes for hosting on Cloud Foundry
- This prototype does not have database authentication, which means that anyone with access to your Firebase Database URL can read and write to your entire database. This makes prototyping quick and easy, but be wary of using sensitive data without adding additional DB access rules, which can be done via the Firebase Web Console after your project is created (see steps below).
- This prototype uses basic authentication via Staticfile.auth. The default user/password is admin/admin. To generate your own encrypted password, use http://www.htaccesstools.com/htpasswd-generator

##Getting Started
+ Open terminal
+ Clone or download repo to your local machine
+ Navigate into your new repository via terminal
+ Start a simple server: `python -m SimpleHTTPServer 8000`
+ Spin up new Firebase Project : https://firebase.google.com/
+ Insert new Firebase Database URL into `index.html` placeholders for both read and write access. This URL can be found in the Firebase Console's Database section (within your newly created project page).
+ Configure Firebase DB Rules to the following to allow read/write access -- change `!=` to `==` as shown below: 
    ```
    {
      "rules": {
        ".read": "auth == null",
        ".write": "auth == null"
      }
    }
    ```
+ With your python server running, open `localhost:8000/index.html` in your browser and add your first new task!