Exercise A: User Manual Procedure

Pick the Python virtual environment task. You’ve already practiced it, so you won’t waste time researching. Use the checklist as your structure: prerequisites, one action per step, an expected result after each step, a screenshot description, and one troubleshooting note.

Model: Create and Activate a Python Virtual Environment (Windows)

Prerequisites

A Windows computer with internet access
Python 3.8 or later installed
Permission to create folders in your user directory

Steps

Press the Windows key, type cmd, and press Enter. Result: a black Command Prompt window opens.
Type python --version and press Enter. Result: Python prints its version, such as Python 3.12.1.
Type mkdir my_project and press Enter. Result: no message appears, but a new folder named my_project is created.
Type cd my_project and press Enter. Result: the prompt now ends with \my_project>.
Type python -m venv venv and press Enter. Result: after a few seconds the prompt returns, and a folder named venv appears inside my_project.
Type venv\Scripts\activate and press Enter. Result: (venv) appears at the start of the prompt.
Type pip install requests and press Enter. Result: the last line reads Successfully installed requests-….
Type pip list and press Enter. Result: a table of installed packages includes requests.
Type deactivate and press Enter. Result: (venv) disappears from the prompt.

Screenshot description (after step 6): A Command Prompt window showing the path C:\Users\YourName\my_project> with (venv) highlighted in front of it. A red box should circle (venv) to show that the environment is active.

Troubleshooting: If you see 'python' is not recognized as an internal or external command, Python isn’t added to your system PATH. Reinstall Python and tick “Add Python to PATH” on the first installer screen, then reopen Command Prompt and repeat from step 2.

macOS note: use python3 instead of python, and source venv/bin/activate in step 6.
