# Steel + Playwright Starter (Python)

This template shows you how to use Steel with Playwright in Python to run browser automations in the cloud. It includes session management, error handling, and a basic example you can customize.

## Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/steel-dev/steel-playwright-starter-python
cd steel-playwright-starter-python

# Create and activate virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

## Quick start

The example script in `main.py` shows you how to:
- Create and manage a Steel browser session
- Connect Playwright to the session
- Navigate to a website (Hacker News in this example)
- Extract data from the page (top 5 stories)
- Handle errors and cleanup properly
- View your live session in Steel's session viewer

To run it:

1. Create a `.env` file in the root directory:
```bash
STEEL_API_KEY=your_api_key_here
```

2. Replace `your_api_key_here` with your Steel API key. Don't have one? Get a free key at [app.steel.dev/settings/api-keys](https://app.steel.dev/settings/api-keys)

3. Run the script:
```bash
python main.py
```

## Writing your automation

Find this section in `main.py`:

```python
# ============================================================
# Your Automations Go Here!
# ============================================================

# Example automation (you can delete this)
page.goto('https://news.ycombinator.com')
# ... rest of example code
```

You can replace the code here with whatever automation scripts you want to run.

## Configuration

The template includes common Steel configurations you can enable:

```python
session = client.sessions.create(
    use_proxy=True,              # Use Steel's proxy network
    solve_captcha=True,          # Enable CAPTCHA solving
    session_timeout=1800000,     # 30 minute timeout (default: 15 mins)
    user_agent='custom-ua',      # Custom User-Agent
)
```

## Error handling

The template includes error handling and cleanup:

```python
try:
    # Your automation code
finally:
    # Cleanup runs even if there's an error
    if browser:
        browser.close()
    if session:
        client.sessions.release(session.id)
```

## Support

- [Steel Documentation](https://docs.steel.dev)
- [API Reference](https://docs.steel.dev/api-reference)
- [Discord Community](https://discord.gg/gPpvhNvc5R)