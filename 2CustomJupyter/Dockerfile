# Use the official JupyterLab image as the base image
FROM jupyter/datascience-notebook:latest

# Set the working directory
WORKDIR /home/jovyan

# Copy the requirements.txt file into the container
COPY requirements.txt .

# Install custom dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Expose the JupyterLab port
EXPOSE 8888

# Start JupyterLab
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root", "--NotebookApp.token=''", "--NotebookApp.password=''"]