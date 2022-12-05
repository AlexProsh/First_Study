# syntax=docker/dockerfile:1
FROM ubuntu

#install git, FastAPI, uvicorn
RUN apt-get update && apt-get install -y git python3 python3-pip

RUN pip install fastapi uvicorn[standard]

#WORKDIR /app

# install app
RUN git clone --branch task-docker https://github.com/AlexProsh/First_Study.git
RUN echo "Hello world" > /bin/print_hello
RUN echo "Tortue" > /README.md
RUN mv /First_Study/main.py /main.py
RUN chmod ugo+x /bin/print_hello

# set user
RUN useradd deploy2022user
USER deploy2022user


CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8898"]