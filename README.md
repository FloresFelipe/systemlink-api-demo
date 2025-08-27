# Test Monitor Client

## 📘 Description

This project connects to **SystemLink** via HTTP using the `nisystemlink-clients` Python API. It demonstrates how to interact with the **TestMonitor**, **File**, and **Product** APIs for failure analysis and visualization.

The Jupyter notebook included in this project is based on the example from the [NI SystemLink Enterprise](https://github.com/ni/systemlink-enterprise-examples/blob/main/Script%20Analysis%20Examples/Test%20Data%20Analysis/Failure_Pareto_Result_Analysis.ipynb) GitHub repository. The difference is that in this version we use the new nisystemlink-clients module.

## 📁 Files Included

- `Failure_Points_Root_Analysis.ipynb` — Jupyter notebook for failure points root analysis.
- `uv.lock` — List of required Python dependencies that can be installed using UV.
- `requirements.txt` - list of required python dependencies if you want to install them using pip.

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
- `matplotlib`
- `scrapbook`
- A SystemLink API Key

## 🛠️ Usage Instructions

1. Clone this repository.
2. Create a UV environment,
   1. If you're in **PyCharm**:
      1. Open the Settings dialog (**File >> Settings...)**
      2. Select **Python > Interpreter **
      3. Click **Add Interpreter >> Add Local Interpreter...**
      4. In the **Add Python Interpreter** dialog, select:
         1. **Generate New**
         2. In **Type:** select `uv`
         3. In **Base Python:** select the Python version you want to use.
         4. Click Ok.
      5. Click Ok to close the Settings dialog
      6. See that UV is now creating your virtual environment and adding the necessary dependencies to it.
    2. If you're in **VSCode**, you can create the environment using the following uv command

    ```bash
    uv sync
    ```

3. Create an empty file named `.env` in the root directory and add the following variables:

```env
SYSTEMLINK_HTTP_URI=<your_systemlink_http_uri>
SYSTEMLINK_API_KEY=<your_api_key>
```

4. **(Optional)** If you don't want to use an .env file, you can create a `SystemLink_API_KEY.json`file in the root directore with the following content:

```json
{
    "systemlink_http_uri": "https://systemlink.example.com",
    "systemlink_api_key": "your_api_key_here"
}
```

5. Collect a group of resultIds from SLE and populate the `result_ids` list variable.

6. Run the notebook `Failure_Pareto_Result_Analysis.ipynb` in Jupyter using a the virtual environment kernel. Notice that it will run fine and return valid results.
   1. Try using debugging tools such as breakpoints, watch variables, etc. They all should work fine.

7. Switch to the SLE pykernel from JupyterHub and run it. It should return the same results.

## 🔗 References

- [nisystemlink-clients PyPI Package](https://pypi.org/project/nisystemlink-clients/)
- [SystemLink Python API Documentation](https://python-docs.systemlink.io/en/stable/index.html)
- [Original Example Notebook](https://github.com/ni/systemlink-enterprise-examples/blob/main/Script%20Analysis%20Examples/Test%20Data%20Analysis/Failure_Pareto_Result_Analysis.ipynb)
