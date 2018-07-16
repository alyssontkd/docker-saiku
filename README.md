# Imagem Oficial Saiku Community Docker
[Oficial Saiku Community][1] Docker Image https://hub.docker.com/r/buggtb/saikuce/

## Docker
Baixe uma [buggtb/docker-saikuce][2] imagem e execute-a com o comando abaixo:
```bash
$ docker pull buggtb/saikuce
$ docker run -d -p 8080:8080 --name docker-saiku buggtb/saikuce
```
Para subir o conteiner mapeando um volume entre sua máquina local e o contêiner utilize o comando:
```
$ docker run -d -p <porta_host>:<porta_conteiner> --name <nome_conteiner> -v <caminho_host>:<caminho_imagem> <nome_imagem>

Exemplo:
$ docker run -d -p 8080:8080 --name docker-saiku -v /usr/share/saiku/saiku-server:/saiku-server buggtb/saikuce:3.17
```

Para acessar o conteiner use o comando `docker exec`
```
docker exec -it <id-conteiner> /bin/bash

Exemplo:
docker exec -it b955c868b4e1 /bin/bash
```

Para verificar os contêiners que estão criados, basta o comando:
```
docker ps -a
```
Para verificar as imagens já baixadas no host, basta o comando:
```
docker images
```

## Saiku
Você pode acessar seu host pelo browser para iniciar o uso da aplicação. As credenciais padrões (username/password) são `admin/admin`.
```
http://seuhostname:8080
```

# Lembrete:
Crie uma conta e acesse o painel da [Comunidade Meteorite][3] e gere uma licença gratuita para utilização da ferramenta.
Após executar o contêiner, acesse o endereço `http://seuhostname:8080/upload.html` e faça o upload da licença gerada no site.

## Tratando possíveis erros ao executar o contêiner
### Erro do Docker quando o encaminhamento IPv4 está desativado (CentOs 7)
Quando o daemon do docker não pode se conectar ao mundo externo para baixar qualquer coisa durante o tempo de compilação um erro é gerado. Normalmente este erro é encontrado quando você está tentando criar uma imagem docker: **"[Warning] IPv4 forwarding is disabled. Networking will not work."**. Esta mensagem está nos informando será necessário habilitar o encaminhamento IPV4.

Para resolver acesso o arquivo `/usr/lib/sysctl.d/99-docker.conf` com seu editor favorito a adicione, edite ou crie as seguiintes entradas para o arquivo para que o docker possa acessar o mundo externo a sua infraestrutura:
```
fs.may_detach_mounts=1
net.ipv4.ip_forward=1
```
Feito isso basta reiniciar o serviço docker da sua máquina e prosseguir com suas atividades.
```
[mbacchi@centos7 ~]$ sudo systemctl restart docker
[mbacchi@centos7 ~]$
```

[1]: http://saiku-documentation.readthedocs.io/en/latest/installation_guide.html
[2]: https://hub.docker.com/r/buggtb/saikuce/
[3]: https://licensing.meteorite.bi/login
