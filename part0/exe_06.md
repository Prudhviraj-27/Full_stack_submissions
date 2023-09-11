    Sequence Diagram
        Participant server
        Participant Browser

        browser --> server: GET request https://studies.cs.helsinki.fi/exampleapp/spa
        server activated
        server --> browser: Response HTML document
        server deactivated
    
        browser --> server: GET request https://studies.cs.helsinki.fi/exampleapp/main.css
        server activated
        server --> browser: Response CSS file
        server deactivated
    
        browser --> server: GET request https://studies.cs.helsinki.fi/exampleapp/spa.js
        server activated
        server --> browser: Response JavaScript file
        server deactivated
    
        Note: Browser executes JavaScript file. While executing it loads JSON file from server
    
        browser --> server: GET request https://studies.cs.helsinki.fi/exampleapp/data.json
        server activated
        server --> browser: Response JSON file
        server deactivated
    
        Note: Browser executes callback function from JavaScript file which renders notes

        Note: Submitting new note through form tag in HTML document

        browser --> server: POST request https://studies.cs.helsinki.fi/exampleapp/new_note_spa
        server activated
        server --> browser: response status 201 {"message":"note created"}
        server deactivated

        Note: SPA version websites executes JavaScript file which executes a callback function which adds new note and rerenders notes list

      
