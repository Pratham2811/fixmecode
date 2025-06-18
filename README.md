🚀 What is this?
fixmecode is a simple CLI tool that:

Runs your JavaScript file
Captures any error from the terminal
Sends the code + error to Gemini AI
Replaces your file with a fixed version (and creates a .bak backup)
📦 Installation
npm install -g fixmecode

🔐 API Key Setup

To use this tool, you need a Gemini API key.

    Create a .env file in your project or home directory.

    Add your API key like this:

GEMINI_API_KEY=your-api-key-here

You can get a key from Google AI Studio.
🧪 Usage

fixmecode buggy.js

If buggy.js has errors, it will:

    Read the file

    Run it

    Catch errors (like syntax/runtime)

    Ask Gemini AI to fix them

    Overwrite the original file with a backup at buggy.js.bak

✅ Example

// buggy.js
function sayHello(name) {
  console.log("Hello, " + name)

sayHello("Luc"

fixmecode buggy.js

👨‍🔧 Gemini fixes it automatically:

function sayHello(name) {
  console.log("Hello, " + name);
}

sayHello("Luc");

💡 Behind the Scenes

    Uses child_process.spawn to run the file and capture stderr

    Reads the code with fs.promises

    Sends everything to Gemini via @google/generative-ai

    Rewrites the original file with Gemini’s fix

🧠 Why This Exists

Built while learning Node.js streams, stdin, stdout, stderr.
Thought: "Why not let AI clean up your messy dev code on the fly?"
So here we are — fixmecode 😄
🔒 Privacy & Safety

Your API key is kept locally via .env.
Never hardcoded. Safe to use & open to modify.
