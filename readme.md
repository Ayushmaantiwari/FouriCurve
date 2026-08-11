📋 System & Dependency Requirements
Before starting, ensure you have the following installed on your computer:

1. Required Software
Python: Version 3.8 or higher (Download from python.org)

VS Code: Visual Studio Code (Download from code.visualstudio.com)

Web Browser: Chrome, Edge, or Firefox (for rendering the real-time HTML5 interface)

2. Required Python Libraries
If you plan to run the Python/Matplotlib script version, you will need:

numpy (for mathematical DFT transformations)

matplotlib (for generating animated figures)

ipython (optional, for rendering notebook media)

🚀 Step-by-Step Setup Guide in VS Code
Step 1: Create a Project Directory
Open VS Code.

Go to File > Open Folder... (or Ctrl+K Ctrl+O on Windows/Linux, Cmd+O on macOS).

Create a new folder named fourier-epicycles and open it.

Step 2: Set Up a Python Virtual Environment
Creating a virtual environment ensures your project dependencies don't conflict with other Python projects.

Open the built-in terminal in VS Code:

Go to Terminal > New Terminal (or press Ctrl + ` / Cmd + `).

Run the following command to create a virtual environment:

Bash
python -m venv venv
Activate the virtual environment:

Windows (Command Prompt):

DOS
venv\Scripts\activate
Windows (PowerShell):

PowerShell
.\venv\Scripts\Activate.ps1
macOS / Linux:

Bash
source venv/bin/activate
(You should see (venv) appear at the front of your terminal prompt line).

Step 3: Install Required Python Dependencies
Create a file named requirements.txt in your project folder.

Paste the following text inside requirements.txt:

Plaintext
numpy>=1.21.0
matplotlib>=3.5.0
ipython>=7.30.0
Install the packages using pip in your terminal:

Bash
pip install -r requirements.txt
💻 Running the Project in VS Code
Depending on whether you want to run the Python Animation or the Real-Time Dual-Screen Interface, follow the corresponding method below:

Method A: Running the Real-Time Dual-Screen App (HTML/JS)
The real-time drawing dual-screen app runs best via a browser or an interactive local server.

Install the Live Server extension in VS Code:

Click on the Extensions icon on the left sidebar (or press Ctrl+Shift+X / Cmd+Shift+X).

Search for Live Server (by Ritwick Dey) and click Install.
