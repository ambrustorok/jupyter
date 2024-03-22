## Setting Up Jupyter on Windows

This guide provides step-by-step instructions for setting up Jupyter on Windows, including installing extensions and configuring different kernels for various projects.

### 1. Creating a Python Virtual Environment

First, create a Python virtual environment with the following command:

```cmd
python -m venv kernel_2024_03_22
```

### 2. Activating the Virtual Environment

Activate the virtual environment in Windows using:

```cmd
.\kernel_2024_03_22\Scripts\activate
```

### 3. Adding and Removing Kernels

#### Adding a New Kernel

To add your virtual environment to the Jupyter kernel, follow these steps:

- Reference: [How to Add Your Virtual Environment to the Jupyter Kernel in Windows](https://python.plainenglish.io/how-to-add-your-virtual-environment-to-the-jupyter-kernel-in-windows-ec9834153eb4)

#### Removing a Kernel

If you need to remove a kernel, follow these instructions:

- Reference: [Remove the Kernel on a Jupyter Notebook](https://stackoverflow.com/questions/42635310/remove-the-kernel-on-a-jupyter-notebook)

### 4. Editing Default Terminal

Modify the default terminal as follows:

- Reference: [How to Change Jupyter Notebook Windows Shell to Bash](https://stackoverflow.com/questions/52330492/how-to-change-jupyter-notebook-windows-shell-to-bash)
  
  ```python
  c.ServerApp.terminado_settings = { 'shell_command': [r'C:\Program Files\Git\bin\bash.exe'] }
  ```

### 5. Running Jupyter Notebook on Startup

Configure Jupyter Notebook to run on startup by following these steps:

1. Press `Windows` + `R`.
2. Type `taskschd.msc` and press Enter.
3. Click on `Task Scheduler Library`.
4. Click `Create Task`.
5. Set the name and configure triggers to "At log on" for your user.
6. Set actions to execute `start_jupyter.bat`.

### `start_jupyter.bat` File

The `start_jupyter.bat` file contains:

```bat
@echo off
cd D:\OneDrive\Projects\virtualenvs\kernel_2024_03_22
call D:\OneDrive\Projects\virtualenvs\kernel_2024_03_22\Scripts\activate
jupyter notebook
```

### 6. Custom Location for Config File

Specify a custom location for the Jupyter config file using an environment variable:

- Env variable: `JUPYTER_CONFIG_DIR`
- Path: `D:\OneDrive\Projects\virtualenvs`


This command exports the environment variable `JUPYTER_CONFIG_DIR` with the specified path.
```cmd
setx JUPYTER_CONFIG_DIR D:\OneDrive\Projects\virtualenvs
```

### 7. Syntax Highlighting Issues
- Reference: [Text editor syntax highlighting does not work](https://discourse.jupyter.org/t/text-editor-syntax-highlighting-does-not-work/13843)

