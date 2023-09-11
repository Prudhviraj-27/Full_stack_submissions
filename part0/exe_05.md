    sequence diagram
        Participant server
        Participant browser

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
