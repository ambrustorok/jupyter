# jupyter
Guide to setup jupyter on windows with extensions and different kernels for different projects

#

Make a python virtualenv

```cmd
python -m venv kernel_2024_03_22
```

Activate it (Windows)

```cmd
.\kernel_2024_03_22\Scripts\activate
```

adding a new kernel: 
https://python.plainenglish.io/how-to-add-your-virtual-environment-to-the-jupyter-kernel-in-windows-ec9834153eb4

removing a kernel:
https://stackoverflow.com/questions/42635310/remove-the-kernel-on-a-jupyter-notebook

editing default terminal
https://stackoverflow.com/questions/52330492/how-to-change-jupyter-notebook-windows-shell-to-bash


run on startup:

Press `Windows` + `R`
`taskschd.msc`

Click `Task Scheduler Library`

Click `Create Task`

Set name

Set Triggers to "At log on", set your user

Set actions to: `D:\OneDrive\Projects\virtualenvs\start_jupyter.bat`

start_jupyter.bat:
```bat
@echo off
cd D:\OneDrive\Projects\virtualenvs\kernel_2024_03_22
call D:\OneDrive\Projects\virtualenvs\kernel_2024_03_22\Scripts\activate
jupyter notebook
```

Custom location for config file:
Env variable:
JUPYTER_CONFIG_DIR
D:\OneDrive\Projects\virtualenvs
