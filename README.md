# sample_web_app

it's a docker image to create simple flask web app.

Every Dockerfile starts with "FROM"

      FROM ubuntu

it will download and install Ubuntu os on your docker host, after that need to perform the upadte and install the needed software and dependencies 

      RUN apt-get update

      RUN apt-get install -y python3 python3-pip

      RUN pip install flask

in my PC, i have written sample python program called aap.py. in the next step it will copy the app.py to the folder called /opt/app.py in the Docker Host.

      COPY app.py /opt/app.py

      ENTRYPOINT ["/usr/bin/python3", "/opt/app.py"] flask run --host=0.0.0.0

After building the Docker image from, we need to run the docker image to see the result. 

      docker build . -t my-custom-app

      docker run my-custom-app

RUN. Mainly used to build images and install applications and packages. Builds a new layer over an existing image by committing the results.

CMD. Sets default parameters that can be overridden from the Docker Command Line Interface (CLI) when a container is running.

ENTRYPOINT. Default parameters that cannot be overridden when Docker Containers run with CLI parameters.
