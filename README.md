# ![DevSuperior logo](https://raw.githubusercontent.com/devsuperior/bds-assets/main/ds/devsuperior-logo-small.png) Semana Spring React
## Ferramentas Utilizadas no projeto:

- Curl
- Git
- Java JDK 11 ou 17
- Maven
- STS
- Postman
- Postgresql e pgAdmin
- Heroku CLI
- NodeJS 16.x 
- VS Code

[![DevSuperior no Instagram](https://raw.githubusercontent.com/devsuperior/bds-assets/main/ds/ig-icon.png)](https://instagram.com/devsuperior.ig)
[![DevSuperior no Youtube](https://raw.githubusercontent.com/devsuperior/bds-assets/main/ds/yt-icon.png)](https://youtube.com/devsuperior)

## Objetivos do projeto 
- Implementar o back end
- Modelo de domínio
- Acesso a banco de dados
- Estruturar o back end no padrão camadas
- Criar endpoints da API REST
- Implantação na nuvem

    
#### Modelo conceitual
![Image](https://raw.githubusercontent.com/devsuperior/bds-assets/main/sds/dsmovie-dominio.png "Modelo conceitual")

#### Padrão camadas adotado

![Image](https://github.com/devsuperior/bds-assets/raw/main/sds/padrao-camadas.png "Padrão camadas")

- Criar repository
- Criar DTO
- Criar service
- Criar controller
- **COMMIT: Find movies**

### Passo: Salvar avaliação

#### Lógica:

1) Informar email, id do filme e valor da avaliação (1 a 5).

2) Recuperar usuário do banco de dados pelo email. Se o usuário não existir, insira no banco.

3) Salvar a avaliação do usuário para o dado filme.

4) Recalcular a avaliação média do filme e salvar no banco de dados.

![Image](https://raw.githubusercontent.com/devsuperior/bds-assets/main/sds/dsmovie-objs.png "Padrão camadas")


### Passo: Implantação no Heroku
- Criar app no Heroku
- Provisionar banco Postgres
- Definir variável APP_PROFILE=prod
- Conectar ao banco via pgAdmin
- Criar seed do banco

```bash
heroku -v
heroku login
heroku git:remote -a <nome-do-app>
git remote -v
git subtree push --prefix backend heroku main
```


### Passo: implantação no Netlify
- Deploy básico
  - Base directory: frontend
  - Build command: yarn build
  - Publish directory: frontend/build

- Arquivo _redirects
```
/* /index.html 200
```

- Configurações adicionais
  - Site settings -> Domain Management: (colocar o nome que você quiser)
  - Deploys -> Trigger deploy
