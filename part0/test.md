::: mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: GET 200 https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET 200 https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET 200 https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET 200 https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes

    Note left of browser: User types message, clicks save

    browser-->>browser: The event handler creates a new note, adds it to the notes list with the command notes.push(note)

    browser->>server: POST 201 https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note right of browser: {"content":"Oh my!","date":"2024-07-30T13:20:55.185Z"}
    server-->>browser: {"message":"note created"}
    deactivate server

    browser-->browser: Test
:::





# Project 0
Create a similar diagram depicting the situation where the user creates a new note on the page https://studies.cs.helsinki.fi/exampleapp/notes by writing something into the text field and clicking the Save button. If necessary, show operations on the browser or on the server as comments on the diagram.