# Sales Lead Agent

A CrewAI-based AI agent that analyzes job candidates, scores them against a job description, allows human review, and generates personalized follow-up emails.

## Features

- Loads candidates from `leads.csv`
- Uses CrewAI to score candidates
- Shows the top 3 candidates for human review
- Allows re-scoring with additional feedback
- Generates personalized emails for every candidate
- Selected candidates receive an interview invitation
- Rejected candidates receive a polite rejection email
- Validates candidate names, job titles, company names, and email decisions
- Saves emails in the `email_responses/` folder

## Project Flow

```text
leads.csv
   ↓
Candidate Scoring
   ↓
Top 3 Candidates
   ↓
Human Review
   ↓
Personalized Email Generation
   ↓
email_responses/
````

## Requirements

* Python 3.11+
* CrewAI
* Ollama with the `llama3.2` model available

## Installation

From the project root, create and activate a virtual environment:

```bash
python -m venv .venv
```

On Windows PowerShell:

```bash
.\.venv\Scripts\Activate.ps1
```

Install dependencies:

```bash
python -m pip install -r requirements.txt
```

The agents use Ollama with the `llama3.2` model. Make sure Ollama is running and that this model is available before starting the app.

## Run

Run from the project root:

```powershell
python main.py
```

## Human Review

After scoring, the system displays the top 3 candidates:

```text
1. Quit
2. Redo lead scoring with additional feedback
3. Proceed with writing emails to all leads
```

Choose:

* `1` to exit
* `2` to provide additional scoring feedback
* `3` to generate emails

## Output

Generated emails are saved in:

```text
email_responses/
```

Example:

```text
email_responses/
├── Daniel Martinez.txt
├── Emily Davis.txt
├── James Wilson.txt
└── ...
```

Each email is personalized using the candidate's information and the hiring decision.
