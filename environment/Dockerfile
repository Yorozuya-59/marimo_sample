FROM ubuntu:22.04

WORKDIR /home/workdir

# Install Python3.10
RUN apt update 
RUN apt upgrade -y
RUN apt install -y python3.10 

# For initial setting of Python
RUN update-alternatives --install /usr/bin/python python /usr/bin/python3.10 1
RUN apt install -y python3-pip
RUN pip install -U pip

# Install Marimo
RUN pip install "marimo[recommend]"
COPY install_gh.sh /usr/local/bin/install_gh.sh
RUN bash /usr/local/bin/install_gh.sh
RUN pip install openai mcp
RUN apt install -y curl
RUN curl -fsSL https://deb.nodesource.com/setup_22.x | bash -
RUN apt install -y nodejs

