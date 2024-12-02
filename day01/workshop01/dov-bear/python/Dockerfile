FROM python:3.11
WORKDIR /usr/local/app

# Copy in the source code
COPY main.py .
COPY utils.py .
COPY requirements.txt .
COPY run.sh .
COPY templates templates
COPY public public

RUN pip install --upgrade pip
RUN pip install --progress-bar off -r requirements.txt

ENV PORT=3000
ENV INSTANCE_NAME='day01-app'
ENV INSTANCE_HASH='day01'
EXPOSE ${PORT}

# Setup an app user so the container doesn't run as the root user
CMD [“python”, “main.py”] 
