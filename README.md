# Slackipy

Slackipy é um pequeno servidor web que ajuda você a automatizar os convites do usuário para sua equipe Slack. Está escrito usando [Flask] (http://flask.pocoo.org) e, para modelar, usa [Jinja2] (http://jinja.pocoo.org), portanto, é muito fácil personalizar e adicionar novos recursos como captcha, requisito de senha etc, além disso.

## Funcionalidades

1. Muito fácil de instalar, configurar e customizar.
2. Instalações de um único clique em Heroku ou Openshift.
3. É responsivo e utiliza [Material Design](http://materializecss.com)
4. Funciona sem javascript

## Instalação

Você precisa seguir:

1. ID da equipe Slack (SLACK_TEAM_ID): O ID da equipe ou sub domínio. Por exemplo, em superheroes.slack.com, os super-heróis são o ID da equipe Slack.

2. Slack API Token (`SLACK_API_TOKEN`): Você precisa gerar o API token com a Conta Admin. Acesse https://api.slack.com/web para gerar um.

3. Flask Secret Key (`FLASK_SECRET_KEY`): Algum string aleatória, será usada para proteger de ataques CSRF. Também será útil se você quiser assinar cookies.

# Heroku 

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/totalvoice/slackipy/tree/master)

# Openshift 

Depois de instalar [setup `rhc`](https://developers.openshift.com/en/managing-client-tools.html), execute o seguinte:

    rhc create-app slackipy python-3.3 --from-code https://github.com/totalvoice/slackipy SLACK_API_TOKEN="your-token-here" SLACK_TEAM_ID="team-id" FLASK_SECRET_KEY="some-random-key"

# Instalação customizada

Check [Flask Deployment](http://flask.pocoo.org/docs/0.10/deploying) se você quiser fazer a implantação personalizada. Você pode atender o aplicativo de `wsgi.py`:

    from wsgi import application

`SLACK_TEAM_ID`, `SLACK_API_TOKEN` e `FLASK_SECRET_KEY` devem ser definidas como variáveis de ambiente.

# Screenshots 

![landing](screenshots/landing.png)
![success](screenshots/success.png)

# Desenvolvimento

Para instalar localmente, clone o repositório, instale as dependências e rode `wsgi.py`:

    $ git clone https://github.com/avinassh/slackipy
    $ cd slackipy
    $ pyvenv venv
    $ source venv/bin/activate
    $ pip install -r requirements.txt
    $ python wsgi.py

A aplicação estará rodando em [localhost:8051](http://localhost:8051)

# Creditos
Este reposítório é um Fork de [slackpy](https://github.com/avinassh/slackipy)
Desenvolvido por [avinassh](https://github.com/avinassh)