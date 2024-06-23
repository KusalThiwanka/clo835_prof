# Stage 1: Build
FROM python:3.11-slim as builder

# Set working directory
WORKDIR /app

# Install dependencies
COPY requirements.txt .
RUN pip install --user -r requirements.txt

# Copy application code
COPY app.py .

# Stage 2: Runtime
FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Copy dependencies from builder stage
COPY --from=builder /root/.local /root/.local

# Copy application code
COPY app.py .

# Set PATH for installed packages
ENV PATH=/root/.local/bin:$PATH

# Expose the application port
EXPOSE 3000

# Command to run the application
CMD ["python", "app.py"]