# AI Emotion Detector 🌤️😠😢😱🤢  
Detect joy, anger, sadness, fear, and disgust in any piece of text using IBM Watson Natural Language Understanding (NLU).

---

## 1. What This App Does
1. You type or paste some text.
2. The app securely sends that text to IBM Watson’s NLU service.
3. Watson returns a score (0 – 1) for five emotions.
4. The web page shows a neat bar chart of those scores.

Everything runs **locally** on your computer—no data is stored.

---

## 2. Tech Stack (a.k.a. “What’s Under the Hood”)

| Purpose                        | Technology |
| ------------------------------ | ---------- |
| Web framework & routing        | **Flask** (Python) |
| Emotion analysis               | **IBM Watson NLU API** |
| Chart rendering (optional)     | **Chart.js** (served from CDN) |
| Dependency management          | **pip** & **requirements.txt** |
| Code quality                   | **PyLint** (target score 10/10) |
| Automated tests                | **pytest** |
| Error logging                  | Python `logging` module |

---

## 3. Quick‑Start Summary (30‑Second Version)

```bash
# 0) Install Python 3.10+ from python.org
# 1) Open a terminal (Command Prompt / PowerShell / macOS or Linux Terminal)
git clone https://github.com/srimaansri/emotion‑detector.git
cd emotion‑detector

# 2) Create and activate a virtual environment
python3 -m venv venv
#    Windows:
venv\Scripts\activate
#    macOS / Linux:
source venv/bin/activate

# 3) Install libraries
pip install -r requirements.txt

# 4) Add your IBM Watson API key & URL into .env (see section 4.6)

# 5) Launch!
python3 server.py
Then visit http://127.0.0.1:5000 in your browser.

If that’s enough for you, stop reading.
Otherwise, keep going for the full beginner walk‑through.

4. Full Beginner Walk‑Through
4.1 Install Python
OS	How to Install
Windows	1. Download Python ≥ 3.10 from python.org/downloads.<br/>2. Run the installer and check “Add Python to PATH”.
macOS	Open Terminal and run:<br/>brew install python<br/>(You need Homebrew; install it from https://brew.sh first.)
Linux	Most distros already include Python. If not:<br/>sudo apt install python3 python3-venv

Confirm installation:

bash
Copy
Edit
python3 --version
# → Python 3.10.x or newer
If python3 works, great. If only python shows the 3.x version, you can use python instead throughout.

4.2 Get the Code
If Git is already installed → simply run:

bash
Copy
Edit
git clone https://github.com/your‑username/emotion‑detector.git
If Git is not installed:

Download the ZIP from GitHub (“Code > Download ZIP”).

Right‑click → “Extract All…”.

Open the extracted folder in your File Explorer / Finder.

In that folder, hold Shift + Right‑click and choose “Open PowerShell window here” (Windows)
– or open Terminal and cd into the folder (macOS/Linux).

4.3 Create & Activate a Virtual Environment
Why? It keeps this project’s libraries separate from everything else on your PC.

bash
Copy
Edit
python3 -m venv venv          # create
# Windows:
venv\Scripts\activate
# macOS / Linux:
source venv/bin/activate
After activation, your terminal prompt will show (venv).

Tip: Any time you open a new terminal window you must re‑activate with the same command.

4.4 Install Python Libraries
All required libraries are listed in requirements.txt. Install them with:

bash
Copy
Edit
pip install -r requirements.txt
Common packages pulled in:

Flask

ibm‑watson

python‑dotenv

pytest

pylint

4.5 Get Free IBM Watson NLU Credentials
Create a free IBM Cloud account: https://cloud.ibm.com/registration

In the dashboard search bar, type “Natural Language Understanding”.

Click Create → choose the free “Lite” plan.

In the newly created service page, open API Keys. Copy:

API Key

URL (looks like https://api.us‑south.natural‑language‑understanding.watson.cloud.ibm.com/instances/…)

4.6 Store Your Secrets Locally
Create a plain‑text file named .env in the project root:

env
Copy
Edit
# .env
WATSON_API_KEY=your_real_key_here
WATSON_URL=https://api.us-south.natural-language-understanding.watson.cloud.ibm.com/instances/xxx
The app reads these at runtime; nothing is hard‑coded.

(Never commit .env to GitHub—.gitignore already excludes it.)

4.7 Launch the App
bash
Copy
Edit
python3 server.py
You’ll see:

csharp
Copy
Edit
 * Running on http://127.0.0.1:5000 (Press CTRL+C to quit)
Open that address in your browser, type some text, and hit Analyze.

5. Extra Commands (Optional but Useful)
Task	Command
Run unit tests	pytest
Check code style (PyLint)	pylint src/ (Score should be 10.00/10)
Stop the app	In the terminal, press CTRL + C

6. Directory Layout
pgsql
Copy
Edit
emotion‑detector/
│
├── src/                 # All Python code
│   ├── server.py        # Flask app entry‑point
│   ├── watson_client.py # API wrapper & error handling
│   └── utils.py         # Helper functions
│
├── templates/           # Jinja2 HTML files
│   └── index.html
│
├── static/              # CSS & optional JS (Chart.js)
│
├── tests/               # pytest unit tests
│   └── test_watson.py
│
├── requirements.txt
└── README.md
(Your actual file names may vary—adjust accordingly.)

7. Troubleshooting FAQ
Symptom	Fix
ModuleNotFoundError: No module named 'flask'	Activate your virtual environment (venv) and then run pip install -r requirements.txt again.
Browser can’t connect (ERR_CONNECTION_REFUSED)	Is the terminal still running the Flask server? Do you see “Running on http://127.0.0.1:5000”? If not, start it with python3 server.py.
Watson returns 401/403 errors	Double‑check you copied both WATSON_API_KEY and WATSON_URL exactly into .env.
PyLint score < 10	Run pylint src/ to see style warnings. They don’t break the app—only code quality.

8. Where to Go Next
Deploy to the web: Heroku, Render, Fly.io, or an AWS EC2 micro instance.
(Just make sure your .env variables are set in the host’s dashboard.)

Add more emotions: Watson can detect up to 9; you could also switch to large language‑model APIs for subtler moods.

Improve UI: Swap in a CSS framework like Tailwind or add real‑time charts.

Feel free to fork, tinker, and share! 😊
