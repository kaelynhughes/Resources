# Aggietime Troubleshooting
* Insomnia says JWT not found bc user not logged in:
    * Need auth-bypass.diff (in Bitwarden)
    * RUN auth-bypass diff thingy- git apply auth-bypass.diff
* Error - dev.env file missing:
    * Move all files from the aggietime-api.tar.gz folder into main folder of aggietime
    * There are 6 files- are they all there?
* Insomnia needs the Insomnia JSON file
* API shuts down with error- Oracle database listener: no listener, worker exiting, reason: worker failed to boot
    * bestie you are not on the VPN
* API shuts down with error- Error response from daemon: failed to create shim task; mentions a path to cas.properties
    * Last chunk of the docker-compose-devl.yml file needs to be commented out- "cas:" down
* Frontend says something is already running on port 3000
    * u prolly shut down ur terminal window without ending the process
    * Shutting down computer and turning it back on again works but there's probably an easier way too

