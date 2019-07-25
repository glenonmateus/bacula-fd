# Bacula File Daemon

Bacula File Daemon container. This daemon runs on clients for Bacula Director scheduled backup.

# Environment

No variable are required to run the container. All have a default value.

### BACULA_FDNAME

File Daemon Name (default **bacula**)

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

`docker container run --name bacula-fd -e BACULA_FDPASSWORD=senha glenonmateus/bacula-fd`
