# Aggietime Troubleshooting

## Setting up container for the first time:

1. Get files from Bitwarden & add to root folder
   1. `aggietime-api.tar.gz`
   2. Unzip `env_files.zip` and add all `.env` files
   3. `auth-bypass.diff`
2. Unzip `aggietime-api.tar.gz`:

```
tar -xzf aggietime-api.tar.gz
```

3. Apply `auth-bypass.diff`

```
git apply auth-bypass.diff
```

4. Go to `docker-compose-devl.yml` and make sure the following are commented out or removed, and that there is no `:ro` after the bullet points under `volumes`:

```
read_only: true
tmpfs:
    - /tmp
```

```
cas:
  image: harbor.usu.edu/base-images/devl-cas-server:6.4.2
  network_mode: service:aggietime-api
  volumes:
    - ./cas.properties:/etc/cas/config/cas.properties:ro
```

5. Get on the staff VPN ([instructions here](https://usu.service-now.com/aggies?id=kb_article_view&sysparm_article=KB0015561) - you will have to sign in to ServiceNow to see the article!)
6. Start docker container!

```
docker compose -f docker-compose-devl.yml up
```

## Problems I've had and how to fix

- Insomnia says JWT not found bc user not logged in:
  - Need `auth-bypass.diff` (in Bitwarden)
  - Make sure to apply diff - should see changes to `/API/Controllers/Auth.py` near the end of the file
  - `git apply auth-bypass.diff`
- Error - dev.env file missing:
  - Move all files from the `env_files.zip` folder into main folder of aggietime
  - There are 6 files- are they all there?
- Other insomnia errors
  - Insomnia needs the Insomnia JSON file to work
  - Grab it from bitwarden and stick it in the root folder
- API shuts down with error- `Oracle database listener: no listener, worker exiting, reason: worker failed to boot`
  - bestie you are not on the VPN
- API shuts down with error- `Error response from daemon: failed to create shim task`; mentions a path to `cas.properties`
  - Last chunk of the `docker-compose-devl.yml` file needs to be commented out- `cas:` down
- Frontend says something is already running on port 3000
  - u prolly shut down ur terminal window without ending the process
  - Shutting down computer and turning it back on again works but there's probably an easier way too
- `Error response from daemon: Ports are not available: exposing port TCP 0.0.0.0:5000 -> 0.0.0.0:0: listen tcp 0.0.0.0:5000: bind: address already in use`
  - Specifically a Mac issue
  - AirPlay receiver is on and listening on port 5000
  - Go to System Settings -> General -> AirDrop & Handoff and turn off AirPlay Receiver
- `Error response from daemon: failed to create shim task: OCI runtime create failed: runc create failed: unable to start container process: error mounting "..." to rootfs at "...": mkdir /.../: read-only file system: unknown`
  - comment out 'read_only: true' and 'tmpfs: - /tmp' in docker-compose-devl file
  - remove :ro in both bullet points under 'volumes'
- Error about a python module not found:
  - Rebuild the docker container - just deleting in docker desktop and composing again will not do the trick!
  - Do this by adding `--build` to the end of the regular compose command
  - `docker compose -f docker-compose-devl.yml up --build`