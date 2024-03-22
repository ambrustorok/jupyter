## Guide to Setting Up Jupyter on Windows

This guide outlines the process of setting up Jupyter on Windows, including installing extensions and configuring different kernels for various projects.

### Creating a Python Virtual Environment

To begin, create a Python virtual environment using the following command:

```cmd
python -m venv kernel_2024_03_22
```

### Activating the Virtual Environment

Activate the virtual environment in Windows using:

```cmd
.\kernel_2024_03_22\Scripts\activate
```

### Adding a New Kernel

Follow these steps to add your virtual environment to the Jupyter kernel:

- Refer to this guide: [How to Add Your Virtual Environment to the Jupyter Kernel in Windows](https://python.plainenglish.io/how-to-add-your-virtual-environment-to-the-jupyter-kernel-in-windows-ec9834153eb4)

### Removing a Kernel

To remove a kernel, follow these steps:

- See instructions: [Remove the Kernel on a Jupyter Notebook](https://stackoverflow.com/questions/42635310/remove-the-kernel-on-a-jupyter-notebook)

### Editing Default Terminal

Modify the default terminal by following these steps:

- Reference: [How to Change Jupyter Notebook Windows Shell to Bash](https://stackoverflow.com/questions/52330492/how-to-change-jupyter-notebook-windows-shell-to-bash)
  
  ```python
  c.ServerApp.terminado_settings = { 'shell_command': [r'C:\Program Files\Git\bin\bash.exe'] }
  ```

### Running Jupyter Notebook on Startup

To run Jupyter Notebook on startup, perform the following:

1. Press `Windows` + `R`.
2. Type `taskschd.msc` and hit Enter.
3. Click on `Task Scheduler Library`.
4. Click `Create Task`.
5. Set the name and configure triggers to "At log on" for your user.
6. Set actions to execute `D:\OneDrive\Projects\virtualenvs\start_jupyter.bat`.

### start_jupyter.bat File

The `start_jupyter.bat` file contains:

```bat
@echo off
cd D:\OneDrive\Projects\virtualenvs\kernel_2024_03_22
call D:\OneDrive\Projects\virtualenvs\kernel_2024_03_22\Scripts\activate
jupyter notebook
```

### Custom Location for Config File

You can specify a custom location for the Jupyter config file using an environment variable:

- Env variable: `JUPYTER_CONFIG_DIR`
- Path: `D:\OneDrive\Projects\virtualenvs`
