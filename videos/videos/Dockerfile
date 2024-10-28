# Step 1: Use an official Python runtime as a parent image
FROM python:3.10-slim

# Step 2: Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Step 3: Set the working directory in the container
WORKDIR /app

# Step 4: Copy the requirements file to the working directory
COPY requirements.txt /app/

# Step 5: Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Step 6: Copy the current directory contents into the container at /app
COPY . /app/
# Copy entrypoint script and make it executable
COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh
# Step 7: Expose the port the app runs on
EXPOSE 8000

# Step 8: Use the exec form of CMD to avoid issues with /bin/sh
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]