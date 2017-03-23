# dokku-rstudio
The way to install rstudio on dokku
  
## Install Rstudio on Dokku

1. Create Dokku app called `rstudio`

`dokku apps:create rstudio`

2. Pull image from Docker Hub

`docker pull rocker/rstudio`

3. Retag the docker image `rocker/rstudio` to dokku app `rstudio`

`docker tag rocker/rstudio:latest dokku/rstudio`

4. Deploy rstudio.
`dokku tags:deploy rstudio`

At this point, the rstudio is running on dokku. But however, we cannot access it from outside.

## Update the port proxy

Update the port `80` to port `8787`
`dokku proxy:ports-add rstudio http:80:8787`

Remove the port `8787` from dokku
`dokku proxy:ports-remove rstudio http:8787:8787`

## Access Rstudio
You can now visit `rstudio.example.com` to access rstudio server.
With default username and password as `rstudio`
