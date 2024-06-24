FROM python:3.8

# set a key-value label for the Docker image
LABEL maintainer="modani130484"

## Step 1:
# Create a working directory
WORKDIR /app
## Step 2:
# Copy source code to working directory
COPY . /app
COPY ./techtrends/schema.sql /app
## Step 3:
#RUN pip install -i https://pypi.org/simple flask
RUN pip install -r techtrends/requirements.txt

## Step 4:
# Ensure that the database is initialized with the pre-defined posts in the init_db.py file
RUN python techtrends/init_db.py

# Expose port 80
EXPOSE 3111

## Step 5:
# Run app.py at container launch
CMD ["python", "techtrends/app.py"]