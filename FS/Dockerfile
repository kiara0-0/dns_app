FROM python:3.9

RUN apt-get update \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*


RUN groupadd -g 799 nyu && \
    useradd -r -u 999 -g nyu nyu

# Set up a working folder and install the pre-reqs
WORKDIR /app

COPY . /app

RUN pip install Flask
RUN pip install requests
RUN pip install docker

USER nyu

COPY --chown=nyu:nyu . .

CMD [ "python", "./FS.py" ]