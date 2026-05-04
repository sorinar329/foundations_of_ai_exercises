FROM python:3.11-slim

LABEL maintainer="University of Bremen – Institute for Artificial Intelligence"
LABEL description="FAI SS2026 – Exercises"

WORKDIR /home/jovyan/work

# Install dependencies
# Build context is the repo root, so requirements.txt is at the top level
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy all exercises into the container
COPY exercises/ ./exercises/

EXPOSE 8888

# --allow-root   : required when running as root inside Docker
# --IdentityProvider.token='' : disables token auth (new config key for JupyterLab 4+)
CMD ["jupyter", "lab", \
     "--ip=0.0.0.0", \
     "--port=8888", \
     "--no-browser", \
     "--allow-root", \
     "--IdentityProvider.token=", \
     "--notebook-dir=/home/jovyan/work"]

