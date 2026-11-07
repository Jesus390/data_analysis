FROM python:3.11-slim-bookworm

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# Instala dependencias del sistema esenciales para desarrollo, Git y clientes SQL
RUN apt-get update && apt-get install -y --no-install-recommends \
    git \
    curl \
    build-essential \
    libpq-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Crea el usuario no raíz para VS Code
RUN useradd -m -s /bin/zsh vscode

# Asegura que pip esté actualizado antes de cualquier instalación externa
RUN pip install --no-cache-dir --upgrade pip

USER vscode
