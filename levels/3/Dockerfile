FROM ubuntu

COPY ./ /usr/share/level03
WORKDIR /usr/share/level03

RUN apt-get update && apt-get install -y \
  python-pip

RUN pip install flask flup
CMD ["python", "secretvault.py"]
EXPOSE 5000
