sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    server-->>browser: HTML document
    deactivate server
    Note right of browser: request payload contains the note content. 
    The server responds with status code 201 created, the browser stays on the same page, and it sends no further HTTP requests.
    The command document.getElementById('notes_form') instructs the code to fetch a reference to the HTML form element on the page
    that has the ID "notes_form" and to register an event handler to handle the form's submit event. The event handler immediately 
    calls the method e.preventDefault() to prevent the default handling of form's submit ( new GET request).
    Then the event handler creates a new note, adds it to the notes list with the command notes.push(note), rerenders the note list
    on the page and sends the new note to the server.

