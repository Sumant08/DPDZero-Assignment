FROM python:3.10-slim

ENV POETRY_VERSION=1.8.2

# Install system dependencies
RUN apt-get update && apt-get install -y curl

# Install Poetry
RUN curl -sSL https://install.python-poetry.org | python3 - && \
    ln -s /root/.local/bin/poetry /usr/local/bin/poetry

# Set working directory
WORKDIR /app

# Copy only pyproject.toml and lock file first for layer caching
COPY pyproject.toml uv.lock ./

# Configure Poetry to not use virtual environments
RUN poetry config virtualenvs.create false \
    && poetry install --no-interaction --no-ansi

# Now copy the rest of the app
COPY . .

# Expose Flask app port
EXPOSE 8082

# Run your Python app
CMD ["python", "app.py"]
