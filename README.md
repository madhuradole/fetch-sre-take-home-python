# Fetch SRE Take Home Exercise (Python)

### Author: Madhura Dole

## 🖥️ Prerequisites

### 1. Install Python (if not already installed):
- Download & install Python 3.7 or higher from here:  https://www.python.org/downloads/.
- During installation:
  - On Windows, make sure to check "Add Python to PATH".
  - On macOS/Linux, Python 3 is usually pre-installed, however, you can upgrade it via homebrew if needed.
- To verify installation, in your terminal/command prompt run:
  - `python --version`


## ⚙️ Setup

### 2. Clone the repository
- In your terminal/command prompt, run below commands:
  - `git clone https://github.com/madhuradole/fetch-sre-take-home-python.git`
  - `cd 'your project directory'`

### 3. Create a virtual environment
- In your terminal/command prompt, run below commands:
  - `pythom -m venv venv`
  - `source venv/bin/activate`
- This will start a virtual environment.

### 4. Install dependencies
- In your terminal/command prompt, run below command:
  - `pip install -r requirements.txt`

### 5. YAML configuration
- Ensure each api request in your YAML file (sample.yaml) has the following structure and parameters:
  - ```
    - body: '' OR
        a: b
      method: POST
      url: https://example.com/api
      headers:
        content-type: application/json
      name: Sample Request
    ```

## ▶️ Run the Project
- In your terminal/command prompt (from your project directory), run below command:
  - `python main.py sample.yaml`
- This will kickstart check cycles that determined URL availability

## ✅ Issues Indetified and their Solutions
- Step #1
  - The request objects: `body, headers, method and name` were missing in the second and fourth request.
  - Added these request objects to the GET methods - `sample index up` and `sample error down` in the yaml config.
- Step #2
  - Fixed the 'body' json param structure in the first POST request aka `sample body up` from embedded string to YAML native.
- Step #3
  - Modified method name var in `check_health()` method to always store uppercase method name, by calling `.upper()` on `endpoint.get('method')`.
  - This ensures that the method name passed in the API request is always uppercase.
- Step #4
  - Added comments in `main.py` to explain each step as requested in the exercise pdf.

## 🛠️ Requirements
- Python 3.7+
- Packages
  - requests
  - PyYAML
- If needed, you can install each package manually by typing below command in your terminal/command prompt:
  - pip install requests pyyaml
  - Follow the instructions here if pip is not installed on your computer: https://pip.pypa.io/en/stable/installation/

## 📝 Notes
- Supports GET, POST HTTP methods.
- JSON bodies need to be defined directly as YAML objects.
