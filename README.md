# sumas-deep-learning

This repo contains codes for getting started with deep learning in PyTorch.

## Prerequisites

Before starting, ensure you have:

- [Git](https://git-scm.com/downloads) installed on your system
- [Anaconda](https://www.anaconda.com/products/distribution) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html) installed on your system. I recommend using Miniconda for a lightweight setup.

## Setup Instructions

### 1. Clone the Repository

First, clone this repository to your local machine:

**Linux/macOS/Windows:**

```bash
git clone https://github.com/Ezecc/sumas-deep-learning.git
cd sumas-deep-learning
```

Alternatively, if you prefer using SSH:

```bash
git clone git@github.com:Ezecc/sumas-deep-learning.git
cd sumas-deep-learning
```

### 2. Update Conda (Optional but Recommended)

It's a good practice to update conda to the latest version before creating new environments:

**Linux/macOS:**

```bash
conda update -n base -c defaults conda -y
```

**Windows (Command Prompt or PowerShell):**

```cmd
conda update -n base -c defaults conda -y
```

### 3. Create Virtual Environment

Create a conda virtual environment with Python 3.11:

**Linux/macOS:**

```bash
conda create -n ml_env_p311 python=3.11 -y
```

**Windows (Command Prompt or PowerShell):**

```cmd
conda create -n ml_env_p311 python=3.11 -y
```

### 4. Activate the Environment

**Linux/macOS:**

```bash
conda activate ml_env_p311
```

**Windows (Command Prompt or PowerShell):**

```cmd
conda activate ml_env_p311
```

> **Note:** If you're using Windows PowerShell and encounter an activation error, you may need to initialize conda for PowerShell first:
>
> ```powershell
> conda init powershell
> ```
>
> Then restart your PowerShell terminal and try activating again.

### 5. Install Dependencies

Once the environment is activated, install all required packages for deep learning:

**Linux/macOS/Windows:**

```bash
pip install -r requirements.txt
```

This will install all necessary dependencies including:

- PyTorch and TorchVision (for deep learning)
- Jupyter Lab and Notebook (for interactive development)
- NumPy, Matplotlib (for numerical computing and visualization)
- And other supporting libraries

### 6. Verify Installation

To verify that PyTorch is installed correctly and can access GPU (if available):

```python
python -c "import torch; print(f'PyTorch version: {torch.__version__}'); print(f'CUDA available: {torch.cuda.is_available()}')"
```

## Getting Started

You can work with your deep learning projects in two ways:

### Option 1: Using VS Code

VS Code provides an excellent integrated development environment for Jupyter notebooks and Python scripts with the conda environment.

#### Setup VS Code for Jupyter and Python

1. **Install Required VS Code Extensions:**
   - [Python extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python) (by Microsoft)
   - [Jupyter extension](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter) (by Microsoft)

   You can install these from the Extensions marketplace in VS Code (Ctrl+Shift+X or Cmd+Shift+X on macOS).

2. **Select the Conda Environment in VS Code:**

   **For Python Files (.py):**
   - Open any Python file in VS Code
   - Look at the bottom-right corner of the window for the Python interpreter indicator
   - Click on it (it may show the current Python version or interpreter path)
   - Select `ml_env_p311` from the list of available interpreters
   - If you don't see it, choose "Enter interpreter path..." and navigate to your conda environment

   **For Jupyter Notebooks (.ipynb):**
   - Create or open a Jupyter notebook in VS Code (File → New File → Jupyter Notebook)
   - Click on "Select Kernel" in the top-right corner of the notebook
   - Choose "Python Environments..."
   - Select `ml_env_p311` from the list

3. **Working with Jupyter Notebooks in VS Code:**
   - Create a new notebook: File → New File → Jupyter Notebook
   - Run cells using Shift+Enter
   - Add cells using the +Code or +Markdown buttons
   - View variables in the Variables explorer
   - Use IntelliSense for code completion
   - Debug cells with breakpoints

4. **Working with Python Scripts in VS Code:**
   - Create a new Python file (.py)
   - Write your code with full IntelliSense support
   - Run the file by clicking the Run button (▷) in the top-right corner
   - Or use the integrated terminal: `python your_script.py`
   - Debug using VS Code's powerful debugger (F5)

### Option 2: Using Standalone Jupyter

If you prefer the traditional browser-based Jupyter interface, then use any of the following commands after activating your conda environment to start Jupyter Lab or Notebook:

1. **Launch Jupyter Lab:**

   ```bash
   jupyter lab
   ```

2. **Launch Jupyter Notebook:**

   ```bash
   jupyter notebook
   ```

## Deactivating the Environment

When you're done working, you can deactivate the environment:

**Linux/macOS/Windows:**

```bash
conda deactivate
```

## Troubleshooting

### VS Code-specific Issues

- **Conda environment not showing in VS Code:**
  - Reload VS Code window (Ctrl+Shift+P / Cmd+Shift+P → "Developer: Reload Window")
  - Ensure the Python extension is installed and enabled
  - Check that conda is in your system PATH
  - Try running `conda info --envs` in VS Code's integrated terminal to verify the environment exists

- **Jupyter kernel not starting:**
  - Ensure `ipykernel` is installed in your conda environment: `pip install ipykernel`
  - Restart VS Code after installing the Jupyter extension
  - Check Output panel (View → Output) and select "Jupyter" to see error logs

- **Import errors in notebooks:**
  - Verify you've selected the correct kernel (`ml_env_p311`)
  - Check that all packages are installed in the active conda environment
  - Restart the kernel: Click "Restart" button in the notebook toolbar

### Windows-specific Issues

- If you encounter issues with `pywinpty`, ensure you're using a compatible terminal (Command Prompt, PowerShell, or Windows Terminal).
- For GPU support on Windows, you may need to install CUDA Toolkit separately from [NVIDIA's website](https://developer.nvidia.com/cuda-downloads).

### Linux-specific Issues

- If you encounter permission errors, avoid using `sudo` with pip. Instead, ensure your conda environment is properly activated.
- For GPU support on Linux, ensure you have the appropriate NVIDIA drivers and CUDA toolkit installed.

### General Issues

- If packages fail to install, try updating pip first:

  ```bash
  pip install --upgrade pip
  ```

- If you encounter conflicts, you can remove and recreate the environment:

  ```bash
  conda deactivate
  conda env remove -n ml_env_p311
  # Then follow steps 3-5 again
  ```
