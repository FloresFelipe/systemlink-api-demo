# Test Monitor Client

## 📘 Description

This project connects to **SystemLink** via HTTP using the `nisystemlink-clients` Python API. It demonstrates how to interact with the **TestMonitor**, **File**, and **Product** APIs for failure analysis and visualization.

The Jupyter notebook included in this project is based on the example from the NI SystemLink Enterprise GitHub repository.

## 📁 Files Included

- `Failure_Points_Root_Analysis.ipynb` — Jupyter notebook for failure points root analysis.
- `requirements.txt` — List of required Python dependencies.

## 🧠 Script Overview

### `get_server_configuration()`

Retrieves the SystemLink server URL and API key from:

1. Environment variables (`SYSTEMLINK_HTTP_URI`, `SYSTEMLINK_API_KEY`)
2. `.env` file using the `dotenv` module
3. Fallback to `SystemLink_API_KEY.json` if not found

## 🖥️ Execution Environments

This example notebook is designed to run seamlessly in two environments:

1. **Local IDE on a Development Machine**  
   You can run the notebook using popular Python IDEs such as **VSCode**, **PyCharm**, or **Jupyter Notebook** installed locally. This allows you to take full advantage of development features like debugging, version control integration, and code navigation.

2. **SystemLink JupyterHub Kernel**  
   The same notebook can also be executed remotely on the **SystemLink JupyterHub** environment. This is particularly useful for accessing SystemLink-hosted data and services directly from within the SystemLink infrastructure.

> The goal is to demonstrate that developers can enjoy the flexibility and productivity of local development tools while still interacting with SystemLink APIs and services. This hybrid approach supports both rapid prototyping and scalable deployment.

## 📦 Requirements

- Python 3.x
- `python-dotenv`
- `nisystemlink-clients`
- `ipykernel`
- A SystemLink API Key

## 🛠️ Usage Instructions

1. Clone this repository.
2. Create and activate a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate  # On Windows use: .venv\Scripts\activate
```

3. Install dependencies with:

```bash
pip install -r requirements.txt
```

4. Create a .env file in the root directory with the following variables:

```env
SYSTEMLINK_HTTP_URI=<your_systemlink_http_uri>
SYSTEMLINK_API_KEY=<your_api_key>
```

5. (Optional) If you don't want to use an .env file, you can create a `SystemLink_API_KEY.json`file in the root directore with the following content:

```json
{
    "systemlink_http_uri": "https://systemlink.example.com",
    "systemlink_api_key": "your_api_key_here"
}
```

6. Collect a group of resultIds from SLE and populate the `result_ids` list variable.

7. Run the notebook `Failure_Pareto_Result_Analysis.ipynb` in Jupyter to explore failure analysis using SystemLink APIs.

## 🔗 References

- [nisystemlink-clients PyPI Package](https://pypi.org/project/nisystemlink-clients/)
- [SystemLink Python API Documentation](https://python-docs.systemlink.io/en/stable/index.html)
- [Original Example Notebook](https://github.com/ni/systemlink-enterprise-examples/blob/main/Script%20Analysis%20Examples/Test%20Data%20Analysis/Failure_Pareto_Result_Analysis.ipynb)
