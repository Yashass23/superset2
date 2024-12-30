# Use the official Apache Superset image as a base
FROM apache/superset:latest

# Install gevent
RUN pip install gevent

# Set the environment variables for Superset
ENV SUPERSET_HOME=/app/superset

# Copy your Superset configuration if any
# COPY superset_config.py $SUPERSET_HOME/superset_config.py

# Expose the necessary port
EXPOSE 8088

# Run Superset with Gunicorn
ENTRYPOINT ["gunicorn", "-w", "3", "-k", "gevent", "--timeout", "120", "-b", "0.0.0.0:8088", "superset.app:create_app()"]
