# VPS Setup

This repo provides a basis for my VPS setup, with a variety of SSL-secured services routed through a Traefik reverse proxy.
 
## Installation

1. Clone this repo and cd into it.

2. Cd into the `traefik` dir, copy the `.env.dist` file to `.env` and fill in the environment variables. 
    > To create the password hash, install `apache2-utils` and run `echo $(htpasswd -nb <username> <password>)`.
   > 
   > If you intend to use the hash directly in the `docker-compose.yml` file, make sure you double all dollar signs (`$` => `$$`).

3. Up the `traefik` stack with `docker-compose up -d`. If your DNS is correctly set up, you should now be able to authenticate against it.

4. Initialize and update submodules for the services your need: `git submodule update --init <module-name>` and go through their own setup process.