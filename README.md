# Logstash_Docker_Image

This repository contains a custom Docker image to run a Logstash container with Filebeat and Metricbeat. The files included are saved in a directory with the following structure:

- Dockerfile
- elasticsearch-ca.pem
- filebeat/filebeat.yml
- filebeat/logstash.yml
- log4j2.properties
- metricbeat/logstash-xpack.yml
- metricbeat/metricbeat.yml;
- start-services.sh

This custom image lets you run Logstash containers to ingest data to your Elasticsearch cluster, with Filebeat and Metricbeat installed on the container to view logs and metrics of the Logstash instance using the pre-built dashboards and monitoring UI in Kibana.

Download the files and adjust the settings based on your environment: 

- Elasticsearch hosts
- Kibana hosts;
- Usernames;
- Passwords.

## How to build and run the container:

Use char "." at the end to point to the current directory where Dockerfile exists. Substitute `image_name` by the desired name:

`docker build -t image_name .`

After image build, run the image by command run below. Substitute `/path/to/your/logstash.conf` and `container_name` by location of logstash configuration file and desired container name:

`docker run -d -p 5044:5044/udp -v /path/to/your/logstash.conf:/usr/share/logstash/pipeline/logstash.conf --name container_name image_name`

## See also:

Check out the YouTube channel for the video tutorial:
https://youtube.com/@AliYounesGo4IT?si=N-zBH44bI_azvmTA
