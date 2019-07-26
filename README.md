# Bacula File Daemon

Bacula File Daemon container. This daemon runs on clients for Bacula Director scheduled backup.

# Environment

No variable are required to run the container. All have a default value.

### BACULA_FDNAME

File Daemon Name (default **bacula-fd**)

### BACULA_FDPASSWORD

Bacula File Daemon Password (default **password**)

### BACULA_DIRNAME

Bacula Director Name (default **bacula**)

### BACULA_MONNAME

Monitor Name (default **BACULA_DIRNAME-mon**)

### BACULA_MONFDPASSWORD

Monitor Password (default **BACULA_FDPASSWORD**)

### BACULA_DEBUG

Bacula File Daemon Debug Level (default **50**)

# Running

To run the container:

```
docker container run -d --name bacula-fd \
  -e BACULA_FDPASSWORD=password \
  --mount type=volume,src=bacula-fd,dst=/etc/bacula/ \
  -p 9102:9102 \
  glenonmateus/bacula-fd
```

# Docker Compose

```
version: 3.7

services:

  bacula-fd:
    image: glenonmateus/bacula-fd
    volumes:
     - bacula-fd:/etc/bacula
    environment:
     - BACULA_FDPASSWORD=password
    networks:
     - bacula
    ports:
     - 9102:9102
    deploy:
     mode: global
     restart_policy:
      condition: on-failure

networks:
  bacula:

volumes:
  bacula-fd:

```
