# dokku-rstudio
The way to install rstudio on dokku
  
## Install Rstudio on Dokku

1. Create Dokku app called "rstudio"

` dokku apps:create rstudio`

2. Pull image from Docker Hub

`docker pull rocker/rstudio`

## Update the port proxy
