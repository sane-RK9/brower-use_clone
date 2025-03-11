# Social Media Automator 🤖

[![Python](https://img.shields.io/badge/python-3.11+-blue.svg)](https://www.python.org/)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![Tests](https://github.com/sane-RK9/browser-use_clone/actions/workflows/tests.yml/badge.svg)](https://github.com/sane-RK9/browser-use_clone/actions/workflows/tests.yml) 
[![codecov](https://codecov.io/gh/sane-RK9/broswer-use_clone/branch/main/graph/badge.svg)](https://codecov.io/gh/sane-RK9/browser-use_clone) 
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

Automate tasks on various social media platforms using Python, Selenium, Beautiful Soup, and official APIs.

## ✨ Features

*   **Multi-Platform Support:** Automate actions on Twitter, Facebook, Instagram, and more (extendable to other platforms).
*   **API Integration:** Prioritizes using official APIs for reliable and efficient interaction with social media platforms.
*   **Web Scraping with Beautiful Soup:**  Extracts data from web pages when APIs are unavailable or for specific data not exposed through APIs.
*   **Selenium Web Browser Automation:** Handles complex UI interactions, login flows, and tasks that require emulating a user's actions.
*   **Proxy Support (Optional):** Use proxies to manage rate limits, access geo-restricted content, and improve privacy.
*   **Modular Design:** Easily extendable to new platforms and functionalities with a well-organized structure.
*   **Configuration Management:** Uses `config.ini` for storing API keys, user credentials, and other settings.
*   **Unit Tests:**  Includes comprehensive unit tests to ensure code quality and reliability.
*   **Asynchronous Operations (Optional):** Leverages `asyncio` and `aiohttp` for improved performance, especially when interacting with multiple APIs.

## 📦 Installation

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/YOUR_USERNAME/social-media-automator.git  # Replace YOUR_USERNAME
    cd social-media-automator
    ```

2.  **Create a virtual environment:**

    ```bash
    python3 -m venv .venv
    ```

3.  **Activate the virtual environment:**

    *   **Linux/macOS:**
        ```bash
        source .venv/bin/activate
        ```
    *   **Windows:**
        ```bash
        .venv\Scripts\activate
        ```

4.  **Install dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

## 🚀 Usage

```python
from platforms import twitter  # Example: using the Twitter module

# Initialize and authenticate the Twitter API client
tw = twitter.TwitterAPI()
tw.authenticate()

# Post a tweet
tw.post("Hello from my automation bot! #python #automation")

# Like a tweet by ID
tw.like("1234567890123456789")  # Replace with an actual tweet ID

# Follow a user
tw.follow("username") # Replace with the target username

# ... other automation tasks
```

See the [`examples`](/examples) directory for more detailed usage scenarios and examples for other platforms.  

## ⚙️ Configuration

1.  **Create a `data/config.ini` file:**

    ```ini
    [twitter]
    api_key = YOUR_TWITTER_API_KEY
    api_secret = YOUR_TWITTER_API_SECRET
    access_token = YOUR_TWITTER_ACCESS_TOKEN
    access_token_secret = YOUR_TWITTER_ACCESS_TOKEN_SECRET

    [facebook]
    app_id = YOUR_FACEBOOK_APP_ID
    app_secret = YOUR_FACEBOOK_APP_SECRET
    access_token = YOUR_FACEBOOK_ACCESS_TOKEN

    [instagram]
    username = YOUR_INSTAGRAM_USERNAME
    password = YOUR_INSTAGRAM_PASSWORD  # Use with caution; API preferred if available

    [selenium]
    headless = True  # Set to False to see the browser window

    [proxy] # Optional proxy settings
    use_proxy = False
    proxy_address = http://your_proxy_address:port
    proxy_username = your_proxy_username
    proxy_password = your_proxy_password

    # Add sections for other platforms as needed
    ```

2.  **Environment Variables (Recommended for API Keys):** Store sensitive API keys and other credentials as environment variables.  You can use a `.env` file and the `python-dotenv` library to load these variables into your application securely.  Do *not* commit the `.env` file to version control.

    Example `.env` file (add to `.gitignore`):

    ```
    TWITTER_API_KEY=YOUR_TWITTER_API_KEY
    TWITTER_API_SECRET=YOUR_TWITTER_API_SECRET
    # ... other environment variables
    ```

    In your code (e.g., `core/utils.py` or `core/social_apis.py`):
    ```python
    import os
    from dotenv import load_dotenv

    load_dotenv()

    twitter_api_key = os.getenv("TWITTER_API_KEY")
    ```

## 🤝 Contributing

Contributions are welcome!

1.  **Fork the repository.**
2.  **Create a new branch:** `git checkout -b feature/your-feature-name`
3.  **Make your changes and commit them:** `git commit -m "Add: Some amazing feature"`
4.  **Push to your branch:** `git push origin feature/your-feature-name`
5.  **Open a pull request.**

Please follow the coding style (Black) and ensure that your code includes unit tests.

## 🧪 Testing

Run the test suite:

```bash
pytest
```

Generate a test coverage report:

```bash
pytest --cov=core --cov=platforms
```

## 📄 Documentation

*   **API Reference:** (To be added - link to generated API documentation)
*   **Architecture Overview:** (To be added - describe the project's architecture)
*   **Examples:** See the `examples` directory for usage examples.


## 🌟 Acknowledgments

*   **browser-use:** Inspiration for the core automation approach.
*   **Tweepy:** Used for interacting with the Twitter API.
*   **Facebook SDK for Python:** Used for interacting with the Facebook Graph API.
*   **Selenium:** Used for web browser automation.
*   **Beautiful Soup:** Used for parsing HTML and XML.
*   **Requests:** Used for making HTTP requests.

## ⚠️ Disclaimer

This project is for educational and personal use only. Be responsible and respect the terms of service of all social media platforms you interact with.  Use this tool at your own risk.  The author(s) of this project are not responsible for any misuse or consequences resulting from the use of this software. Do not use this project for spamming, harassment, or any other malicious or unethical activities.  Automated actions should always comply with the platform's rules and guidelines.

