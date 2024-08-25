FROM debian:latest

# Install dependencies
RUN apt-get update && apt-get install -y curl gnupg2

# Download Nessus
RUN curl -o Nessus.deb https://www.tenable.com/downloads/api/v1/public/pages/nessus/downloads/13147/download?i_agree_to_tenable_license_agreement=true

# Install Nessus
RUN dpkg -i Nessus.deb && apt-get install -f -y

# Expose necessary ports
EXPOSE 8834

# Start Nessus service
ENTRYPOINT ["/bin/bash", "-c", "/opt/nessus/sbin/nessusd; tail -f /dev/null"]
