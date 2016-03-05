FROM debian:latest
RUN apt-get update -y
RUN apt-get install python -y
RUN apt-get install python-pip -y
RUN apt-get install build-essential python-dev -y
RUN pip install neo4j-doc-manager --pre
RUN apt-get install mongodb-clients -y
ENV NEO4J_AUTH neo4j:neo4j2
