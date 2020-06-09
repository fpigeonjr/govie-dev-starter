# Chromium Setup

Taken from [this gist](https://gist.github.com/cvan/44a6d60457b20133191bd7b104f9dcc4)

Sometimes you need to use API Keys to use things like the Speech API. And then you Google a bit and follow all the instructions. But [the Chromium Project's API Keys](http://www.chromium.org/developers/how-tos/api-keys) page does a not-so-great of explaining how to do this, so I will.

1. Download [Chromium](https://www.chromium.org/getting-involved/download-chromium).
2. You'll notice a yellow disclaimer message appear as a doorhanger: `Google API Keys are missing. Some functionality of Chromium will be disabled.`  <u>`Learn More`</u>.
3. Clicking on that link takes you to the confusing [API Keys docs page](http://www.chromium.org/developers/how-tos/api-keys).
4. If you aren't already, subscribe to the [chromium-dev@chromium.org mailing list](https://groups.google.com/a/chromium.org/forum/?fromgroups#!forum/chromium-dev). (You can just subscribe to the list and choose to not receive any mail. FYI: the Chromium project restricts the APIs to those subscribed to that group - that is, Chromium devs.)
5. Make sure you are logged in with the Google account associated with the email address that you used to subscribe to chromium-dev.
6. Log in to the [Google Cloud Platform](https://console.cloud.google.com/), and [select an existing project](https://console.cloud.google.com/iam-admin/projects) or press the "Create Project" button.
7. From the project's [__API Manager__](https://console.cloud.google.com/apis/library), select the [__Credentials__](https://console.cloud.google.com/apis/credentials) tab in the sidebar.
8. Create a [__Browser API Key__](https://console.cloud.google.com/apis/credentials/key?type=CLIENT_SIDE).
9. You'll see a modal with an API key. Copy and paste that somewhere.
10. Now create an [__OAuth Client ID__](https://console.cloud.google.com/apis/credentials/oauthclient).
11. After you complete all the steps and the "content screen," you'll be presented with a modal with your Google Client ID and Client Secret.
12. You'll need to set three environment variables:

  **On Windows:**
  Launch `cmd.exe` and enter the following commands:
  ```bash
  setx GOOGLE_API_KEY your_key_goes_here
  setx GOOGLE_DEFAULT_CLIENT_ID your_client_id_goes_here
  setx GOOGLE_DEFAULT_CLIENT_SECRET your_client_secret_goes_here
  ```

  **On Mac OS X / Linux:**
  Plop these in your `~/.profile` file:
  ```bash
  export GOOGLE_API_KEY="your_key_goes_here"
  export GOOGLE_DEFAULT_CLIENT_ID="your_client_id_goes_here"
  export GOOGLE_DEFAULT_CLIENT_SECRET="your_client_secret_goes_here"
  ```

13. Now launch Chromium:

    **On Windows:**
    Launch Chromium normally.

    **On Mac OS X:**
    ```bash
    /Applications/Chromium.app/Contents/MacOS/Chromium
    ```