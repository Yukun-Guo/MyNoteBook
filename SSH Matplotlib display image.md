# Matplotlib display image via SSH on Windows

## Install Xming on Windows

1. Download and install Xming from [here](https://sourceforge.net/projects/xming/).
   
2. Start Xming.
   Open XLunch.exe -> multiple windows -> Start no client -> Check No Access Control -> next -> finish.

## Install tkinter on Ubuntu

```bash
sudo apt-get install python3-tk
```

## Example python code

```python
import matplotlib
matplotlib.use('TkAgg')
import matplotlib.pyplot as plt
import numpy as np
plt.figure()
plt.plot(np.random.rand(10))
plt.show(block=True)
```

## Run the python code

### On Windows Terminal

```bash
ssh -X xxxx@xx
python3 test.py
```

### On Vscode Terminal

```bash
export DISPLAY=localhost:10.0
python3 test.py
```

### set DISPLAY in .bashrc

```bash
echo "export DISPLAY=localhost:10.0" >> ~/.bashrc
source ~/.bashrc
```