FROM python:3.9.13

# set the working directory in the container
WORKDIR /code

# copy the dependencies file to the working directory
COPY requirements.txt .

# install dependencies
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# copy the content of the local code directory to the working directory
COPY code/ .



