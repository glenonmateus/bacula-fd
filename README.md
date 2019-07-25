# Bacula File Daemon

Serviço File Daemon do Bacula em container. Esse daemon é executado nos clientes para a realização de backup programados pelo Bacula Director.

# Environment

Nenhuma variável é obrigatória pois nelas são atribuídas valores default.

### BACULA_FDNAME

Nome do File Daemon (default **bacula**)

### BACULA_FDPASSWORD

Password do File Daemon usado pelo Bacula Director (default **password**)

### BACULA_DIRNAME

Nome do Director que irá conectar no File Daemon (default **bacula**)

### BACULA_MONNAME

Nome do Monitor (default **BACULA_DIRNAME-mon**)

### BACULA_MONFDPASSWORD

Password do Monitor (default **BACULA_FDPASSWORD**)

### BACULA_DEBUG

Nível de debug do serviço do File Daemon (default **50**)

# Running

Para rodar a image:

`docker container run --name bacula-fd -e BACULA_FDPASSWORD=senha glenonmateus/bacula-fd`
