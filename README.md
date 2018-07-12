# Oficial Saiku Community Docker Image
[Oficial Saiku Community][1] Docker Image https://hub.docker.com/r/buggtb/saikuce/

## Docker
Baixe uma [buggtb/docker-saikuce][2] imagem e execute-a com o comando abaixo:
```bash
docker pull buggtb/saikuce
docker run -d -p 8080:8080 --name docker-saiku buggtb/saikuce
```

## Saiku
Você pode acessar seu host pelo browser para iniciar o uso da aplicação. As credenciais padrões (username/password) são admin/admin.
```
http://seuhostname:8080
```

## Lembrete:
Crie uma conta e acesse o painel da [Comunidade Meteorite][3] e gere uma licença gratuita para utilização da ferramenta.
Após executar o contêiner, acesse o endereço `http://seuhostname:8080/upload.html` e faça o upload da licença gerada no site.

[1]: http://saiku-documentation.readthedocs.io/en/latest/installation_guide.html
[2]: https://hub.docker.com/r/buggtb/saikuce/
[3]: https://licensing.meteorite.bi/login
