Phishing URL & Webpage Analyzer
This Python script is designed to detect common phishing indicators in URLs and web page content. It checks for suspicious elements such as specific keywords in URLs, IP addresses, unusual characters, and form fields that request sensitive information like passwords or credit card details.

Features
URL Phishing Detection: The script analyzes URLs for common phishing signs like suspicious keywords (e.g., login, verify, secure), the presence of IP addresses, and unusual characters.
HTTPS Validation: URLs without HTTPS are flagged as potentially insecure.
Webpage Content Analysis: The script fetches the web page and looks for suspicious forms that request sensitive information like passwords or credit card details.
Timeout Handling: The script prevents long waits by timing out the webpage fetch request after 5 seconds.
Prerequisites
Before running the script, ensure you have the following Python libraries installed:
pip install requests beautifulsoup4


Script Breakdown
check_url(url)
This function performs the following checks on the given URL:

Verifies that the URL starts with http:// or https://.
Looks for suspicious keywords like login, secure, verify, etc.
Flags URLs that contain IP addresses instead of domain names.
Detects unusual characters like @, %, or !.
Checks if the URL is using HTTPS for secure communication.
analyze_webpage(url)
This function fetches the content of the webpage and looks for suspicious forms:

Scans for forms that contain fields related to passwords or credit card information.
Uses a 5-second timeout to prevent delays in case of slow-loading or unresponsive websites.
main()
This is the entry point of the script. It takes user input for a URL, checks the URL for phishing indicators, and then analyzes the webpage content if the URL passes initial checks.

Limitations
The script only detects basic phishing indicators. More sophisticated phishing attacks might not be detected.
It requires internet access to fetch and analyze the webpage content.
It may produce false positives for URLs that contain certain keywords but are legitimate.
License
