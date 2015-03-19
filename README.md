# pessoal.inf.ufg.br

[![Build Status](https://travis-ci.org/acfreitas/pessoal.inf.ufg.br.svg)](https://travis-ci.org/acfreitas/pessoal.inf.ufg.br)

O [Jekyll](http://jekyllrb.com) é um gerador de códigos estáticos. A ideia é você criar páginas estáticas, usando HTML, CSS e JavaScript, pronto para serem publicados. Ele é baseado em vários formatos como [Markdown](http://daringfireball.net/projects/markdown/) para formatação de textos e posts, [Liquid](http://liquidmarkup.org/) para templates e [YAML](http://yaml.org/) para exibir e guardar os dados das variáveis. 

### Dependências

* [Ruby](https://www.ruby-lang.org/)
* [Bundler](http://bundler.io/)
* [Git](http://git-scm.com/)

### Fork

Primeiramente, faça fork do [projeto](https://github.com/acfreitas/pessoal.inf.ufg.br)  para sua conta do GitHub. Se você ainda não conhece o git, você pode conferir a documentação [aqui](https://help.github.com/articles/fork-a-repo/)

### Codeship

Acesse o [Codeship](https://codeship.com/documentation) com sua conta do GitHub e crie projeto para o repositório que você fez fork no passo anterior. 

### Configurando o Codeship

#### Test

##### Setup Commands

```bundle install```

##### Configure Test

```bundle exec jekyll build --trace```

#### Deployment

Seleciona o opção Custom Script. 

```rsync -ravzup  -e "ssh" ~/clone/_site/* <sigadocurso><matricula>@home.inf.ufg.br:/home/alunos/<sigadocurso>/<sigadocurso><matricula>/public_html/
```

#### General

Acesse a aba "General" e copie sua "SSH public key". Feito isso, adicione a chave em ".ssh/authorized_keys" na sua home do INF. 

### Clone

Faça clone do projeto para seu repositório local e execute o Bundler para instalar as dependências.

    $ git clone https://github.com/<username>/pessoal.inf.ufg.br.git
    $ cd pessoal.inf.ufg.br
    $ bundle install

### _config.yml

O Jekyll possui um arquivo _config.yml que guarda as configurações do seu projeto. Ele deve estar sempre na raiz do seu projeto. 

    # Site settings
    title: <Seu Nome>
    email: <Seu Nome>@inf.ufg.br
    description: <Seu Curso>
    baseurl: "inf.ufg.br/~<Seu Nome>/" 
    url: "inf.ufg.br/~<Seu Nome>/" 
    twitter_username:
    github_username:
    lattes_id:
    nome_citacoes: 
    linkedin_username:
    stackoverflow_username: 
    stackoverflow_id: 

### Deploy 

Para fazer deploy, basta fazer commit no GitHub que o Travis CI irá publicar o projeto automaticamente. 

    $ git add .
    $ git commit -m "Descrição" 
    $ git push origin master

### Teste

Acessa a URL ```inf.ufg.br/~<sigladocurso><matricula>/```

### Referências 

* [Jekyll](http://jekyllrb.com/) 
* [Markdown](http://daringfireball.net/projects/markdown/)
* [Liquid](http://liquidmarkup.org/) 
* [YAML](http://yaml.org/)
* [Git](http://git-scm.com/)
* [GitHub](https://github.com/)
* [Ruby](https://www.ruby-lang.org/)
* [Bundler](http://bundler.io/)
* [Travis CI](https://travis-ci.org/) 
* [Servindo sites estáticos com Jekyll](http://tableless.com.br/jekyll-servindo-sites-estaticos/)
* [Deploy a Jekyll page with Travis to your own server](http://jens-na.github.io/2014/01/22/jekyll-deploy-own-server/)