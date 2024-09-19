FROM apache/beam_python3.8_sdk:2.52.0

# Install Python
#RUN apt-get update -y && \
#apt-get install -y python3 python3-pip python3-dev && \
#rm -rf /var/lib/apt/lists/*

# Ensure python command points to python3
#RUN ln -s /usr/bin/python3 /usr/bin/python

#WORKDIR /opt/beam
#COPY requirements.txt .
#RUN pip install -r requirements.txt

# Install SDK. (needed for Python SDK)
RUN pip install --no-cache-dir apache-beam[gcp]==2.52.0

# Copy files from official SDK image, including script/dependencies.
COPY --from=apache/beam_python3.8_sdk:2.52.0 /opt/apache/beam /opt/apache/beam

# Set the entrypoint to Apache Beam SDK launcher.
ENTRYPOINT ["/opt/apache/beam/boot"]