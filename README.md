# Generates a self-signed SSL/TLS certificate

This image generates a self-signed SSL/TLS certificate.

> This project is based on the repo: https://github.com/jacoelho/docker-generate-certificate

The certificate server name is specified using the commandline option to set the SERVER environment variable.

The certificate subject organization is specified using the commandline option to set the SUBJECT environment variable.

An example of generating a certificate for server "server.example.com" using the standard CA organization (assuming you tag the image as robsonrg/genearate-certificate):

- ```docker run --rm -v $(pwd):/certificates -e "SERVER=server.example.com" robsonrg/generate-certificate```

Or if you want to set, for example an organization:

- ```docker run --rm -v $(pwd):/certificates -e "SERVER=server.example.com" -e "SUBJECT=/C=CA/ST=Canada/L=Canada/O=IT" robsonrg/generate-certificate```

for the specified server will generate:

  * cacert.pem
  * server.key
  * server.pem
