# Jenkins Docker

Primeira execução para carregar a imagem, iniciar o container e realizar a configuração inicial:
```
docker run -p 8080:8080 -p 50000:50000 --restart=on-failure --name jenkins -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts-jdk17
```

Resultou em:
http://127.0.0.1:8080
admin / password

# Dependencias

Para esta pipeline vamos utilizar alguns comandos que não estão na imagem original. Para instalá-las:

```
docker exec -it -u root jenkins apt update
docker exec -it -u root jenkins apt install rsync nano
```

# Pipeline 1

Jenkinsfile

Realiza uma sequencia de passos para atualizar um sistema hospedado no IIS em TARGET, deixando o sistema Offline, copiando os novos dados de SOURCE e voltado o sistema para Online.

# Pipeline 2

<implementar os conceitos de CI/CD automatizado do github>

# Pipeline 2

Jenkinsfile.CopyDeploy

Realiza uma comparação prévia da diferença de arquivos, para copiar no passo seguinte apenas os arquivos listados anteriormente.

Objetivo: reduzir o tempo de deploy

