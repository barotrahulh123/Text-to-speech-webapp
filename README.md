# Text-to-Speech Web App

This is a simple web application that converts text into speech using the `gtts` (Google Text-to-Speech) library in Node.js. The app provides a web interface where users can input text, and the server generates an audio file (in MP3 format) that can be played directly in the browser.

## Features

- Convert text to speech dynamically using the Google Text-to-Speech (gtts) library.
- Simple and clean web interface.
- Displays a loading message while the audio is being generated.
- Supports playback of the generated speech in the browser.
- Add download button for downlaod audio file

## Prerequisites

- [Node.js](https://nodejs.org/) installed on your machine.
- Basic knowledge of Express.js and JavaScript.

## Getting Started

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/barotrahulh123/text-to-speech-webapp.git
    cd tts-web-app
    ```

2. Install the required dependencies:
    ```bash
    npm install
    ```

### Running the Application

1. Start the server:
    ```bash
    node app.js
    ```

2. Open your browser and navigate to:
    ```
    http://localhost:3000
    ```

3. Enter the text you want to convert to speech, then click the "Synthesize" button. The generated audio will be available for playback in the browser.

### Project Structure

- `app.js`: The main server file where Express is configured, and routes are defined.
- `public/`: Directory that serves static files like the generated audio.
- `index.html`: The main HTML file containing the web interface.
- `package.json`: Contains project metadata and dependencies.

### How It Works

- The server listens for POST requests at `/synthesize` with a JSON body containing the text to be converted.
- The `gtts` library is used to convert the provided text into speech, and the audio file is saved in the `public` directory.
- The server then responds with the URL of the generated audio file, which the browser can play.

### Example Usage

```json
POST /synthesize
{
    "text": "Hello, world!"
}

Response:
{
    "audioUrl": "/output.mp3"
}
