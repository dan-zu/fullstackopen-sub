```mermaid
sequenceDiagram

    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note right of browser: request payload contains the note content.<br/> Data is sent as the body of the POST request.<br/> The server can access the data by accessing the req.body, <br/>creates a new note object, and adds it to an array called notes
    activate server
    server-->>browser: HTML document
    Note left of server: The server responds with status code 201 created, <br/>the browser stays on the same page, and it sends no further HTTP requests[1^]
    deactivate server
    
```

[1^]: **Details:** The server executes the command behind the scenes without requesting a page reload JavaScript activates a method of adding an element to the page as part of a response to a click on the save control/element on the page
   




