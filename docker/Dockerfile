# syntax=docker/dockerfile:1
FROM ubuntu

#install git, FastAPI, uvicorn
RUN apt-get update && apt-get install -y git python3 python3-pip

RUN pip install fastapi uvicorn[standard]

# set user
RUN useradd deploy2022user

USER deploy2022user

# install app
RUN git clone --branch task-docker https://github.com/AlexProsh/First_Study.git

# final configuration
RUN chmod +x /bin/print_hello

CMD ["uvicorn", "--host 0.0.0.0", "--port 8898", main:app"]