    sequence diagram
        participant server
        participant browser
        
        browser --> server: GET request https://studies.cs.helsinki.fi/exampleapp/notes
        server activated
        server --> browser: Response HTML Document
        server deactivated
    
        browser --> server: GET request GET https://studies.cs.helsinki.fi/exampleapp/main.css
        server activated
        server --> browser: Response CSS file
        server deactivated
    
        browser --> server: GET request https://studies.cs.helsinki.fi/exampleapp/main.js
        server activated
        server --> browser: Response javascript file
        server deactivated
    
        Note: Browser runs Javascript file which in turn loads JSON file 

        browser --> server: GET request GET https://studies.cs.helsinki.fi/exampleapp/data.json
        server activated
        server --> browser: response JSON file
        server deactivated

        Note: Browser executes callback function which renders JSON contents notes

        Note: adding a new note by HTML form tag

        browser --> server: POST request https://studies.cs.helsinki.fi/exampleapp/new_note
        server activated
        server --> browser: Status code 302 Found
        server deactivated

        Note: Above server asks a url redirect to the browser

        browser --> server: GET request https://studies.cs.helsinki.fi/exampleapp/notes
        server activated
        server --> browser: Response Reloads HTML Document
        server deactivated

        browser --> server: GET request GET https://studies.cs.helsinki.fi/exampleapp/main.css
        server activated
        server --> browser: Response Reloads CSS file
        server deactivated

        browser --> server: GET request https://studies.cs.helsinki.fi/exampleapp/main.js
        server activated
        server --> browser: Response Reloads javascript file
        server deactivated

        Note: Browser re-runs Javascript file which in turn loads JSON file

        browser --> server: GET request GET https://studies.cs.helsinki.fi/exampleapp/data.json
        server activated
        server --> browser: response Reloads JSON file
        server deactivated

        Note: Browser executes callback function which renders JSON contents containing new note created through HTTP POST

        
        
