::: mermaid
sequenceDiagram
    Alice->>Bob: Hello Bob, how are you?
    alt is sick
        Bob->>Alice: Not so good :(
    else is well
        Bob->>fa:fa-coffee
    end
    opt Extra response
        Bob->>Alice: Thanks for asking
    end
:::

# Project 0
Create a similar diagram depicting the situation where the user creates a new note on the page https://studies.cs.helsinki.fi/exampleapp/notes by writing something into the text field and clicking the Save button. If necessary, show operations on the browser or on the server as comments on the diagram.