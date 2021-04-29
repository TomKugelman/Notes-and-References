Firebase allows for simple static and dynamic web application to be hosted using google servers and domains

## Setup:

1. Install firebase cli
- Download and run automated install script `curl -sL https://firebase.tools | bash`
- Login to firebase service `firebase login`
>// If running on a remote host add the `--no-localhost` flag
- Test CLI is properly installed with `firebase projects:list`
>// If using firebase in a headless CI environment follow below steps, otherwise skip.
- Install CLI as shown above
- Login to firebase `firebase login:ci` 
- Follow the provided link from the above command on a machine with access to a browser
- Generate new token and store as environment variable called `FIREBASE_TOKEN` OR run all commands with the `--token <token>` flag
>// Note: On any machine with the Firebase CLI installed, you can immediately revoke access for the specified token by running the following command: `firebase logout --token <token>`

