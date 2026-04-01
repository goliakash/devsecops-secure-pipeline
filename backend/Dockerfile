FROM python:3.9-alpine

# 🔐 Update system packages (fix vulnerabilities)
RUN apk update && apk upgrade

# 📁 Set working directory
WORKDIR /app

# 📦 Copy and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir --upgrade pip setuptools wheel \
    && pip install --no-cache-dir -r requirements.txt

# 📂 Copy application code
COPY . .

# 👤 Create non-root user
RUN adduser -D appuser

# 🔒 Switch to non-root user
USER appuser

# 🚀 Run application
CMD ["python", "app.py"]