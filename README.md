# pessoal.inf.ufg.br

[ ![Codeship Status for acfreitas/pessoal.inf.ufg.br](https://codeship.com/projects/e9bd1760-affe-0132-6024-0e5ba92aabbb/status)](https://codeship.com/projects/69450)

O [Jekyll](http://jekyllrb.com) é um gerador de códigos estáticos. A ideia é você criar páginas estáticas, usando HTML, CSS e JavaScript, pronto para serem publicados. Ele é baseado em vários formatos como [Markdown](http://daringfireball.net/projects/markdown/) para formatação de textos e posts, [Liquid](http://liquidmarkup.org/) para templates e [YAML](http://yaml.org/) para exibir e guardar os dados das variáveis. 

### Demo 

* [Antônio Carlos](http://inf.ufg.br/~msc20150217/)

### DependênciasCod

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

```rsync -ravzup  -e "ssh" ~/clone/_site/* <sigadocurso><matricula>@home.inf.ufg.br:/home/alunos/<sigadocurso>/<sigadocurso><matricula>/public_html/```

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

Para fazer deploy, basta fazer commit no GitHub que o Codeship irá publicar o projeto automaticamente. 

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
* [Codeship](https://codeship.com/documentation/continuous-deployment/deployment-with-ftp-sftp-scp/#continuous-deployment-with-rsync) 
* [Servindo sites estáticos com Jekyll](http://tableless.com.br/jekyll-servindo-sites-estaticos/)
