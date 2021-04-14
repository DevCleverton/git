# git
primeiros passos
<html lang="pt-br">
  <head>

     
<header class="intro-header" style="background-image: url('/img/git_start/header.png'); ">
    <div class="container">
        <div class="row">
            <div class="col-lg-8 col-lg-offset-2 col-md-10 col-md-offset-1">
            
                
                    
                   


























               
</header>

<!-- Post Content -->


				<p>Este rápido tutorial é pra você que já tem um conhecimento básico sobre ferramentas de controle de versão ou precisa de um guia rápido para Git com linha de comando.
Também pode ser muito útil se você está apenas acostumado a usar outras ferramentas de desenvolvimento com Git e não sabe os comandos que são executados por trás dela. Aprenda os comandos e não ficará dependente de nenhum outro software.
Veremos os comandos mais usados para se trabalhar com Git. Vou assumir que você já possui cadastro no <a href="https://github.com/">GitHub</a> e já tem Git instalado em seu computador.</p>

<h2 id="configure-seu-usuário">Configure seu Usuário</h2>

<p>O controle de versão controla quem faz as alterações num projeto. Então você deve configurar seu usuário:</p>

<div class="language-sh highlighter-rouge"><div class="highlight"><pre class="highlight"><code>git config <span class="nt">--global</span> user.name <span 
git config <span class="nt">--global</span> user.email <span class="s2">"Seu_meu.email@gmail.com"</span>
</code></pre></div></div>

<p>Substitua com seu Usuário e E-mail da sua conta no GitHub.</p>

<h2 id="crie-um-repositório">Crie um Repositório</h2>

<p>O repositório é onde estarão os arquivos versionados, no servidor Git e no seu computador em uma pasta.
Crie uma pasta, já com o nome do seu repositório e execute o comando dentro dela:</p>

<div class="language-sh highlighter-rouge"><div class="highlight"><pre class="highlight"><code>git init
</code></pre></div></div>
<p>No meu exemplo a pasta se chama <strong>Tutorial</strong></p>

<h2 id="crie-o-commit">Crie o Commit</h2>

<p>Um Commit é um pacote de alterações feitas no repositório. Cada commit possui arquivos alterados, autor e uma mensagem de resumo.</p>

<p>Vamos criar o primeiro commit criando um arquivo especial para o GitHub chamado <strong>README.md</strong>. Dentro deste arquivo escreva:</p>

<div class="language-markdown highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="gu">Meu repositório Git
====================
</span>
Apenas repositório Git

</code></pre></div></div>

<p>Salve o arquivo e agora você irá usar o comando mais usado em Git:</p>

<div class="language-sh highlighter-rouge"><div class="highlight"><pre class="highlight"><code>git status
</code></pre></div></div>

<p>O resultado deve ser:</p>

<div class="language-sh highlighter-rouge"><div class="highlight"><pre class="highlight"><code>On branch master

Initial commit

Untracked files:
  <span class="o">(</span>use <span class="s2">"git add &lt;file&gt;..."</span> to include <span class="k">in </span>what will be committed<span class="o">)</span>

        README.md

nothing added to commit but untracked files present <span class="o">(</span>use <span class="s2">"git add"</span> to track<span class="o">)</span>
</code></pre></div></div>

<p>O comando <code class="highlighter-rouge">git status</code> sempre vai retornar o estado atual do repositório e explicar o que você pode fazer em seguida. 
Neste caso não há commits criados ainda então você pode criar o primeiro com o arquivo <code class="highlighter-rouge">README.md</code>.
Devemos primeiro adicionar o arquivo a um commit com o comando:</p>

<div class="language-sh highlighter-rouge"><div class="highlight"><pre class="highlight"><code>git add README.md
</code></pre></div></div>

<p>Agora o arquivo está pronto para ser empacotado em um commit.
Escreva o comando de commit incluindo uma mensagem que explique o que sua alteração faz no repositório.</p>

<div class="language-sh highlighter-rouge"><div class="highlight"><pre class="highlight"><code>git commit <span class="nt">-m</span> <span class="s2">"Adiciona arquivo README.md"</span>
</code></pre></div></div>

<p>Pronto, você fez o primeiro commit. Pode listar os commits mais recentes com o comando:</p>

<div class="language-sh highlighter-rouge"><div class="highlight"><pre class="highlight"><code>git log
</code></pre></div></div>

<h2 id="suba-seus-commits">Suba seus Commits</h2>

<p>Agora você precisa sincronizar o seu repositório com o GitHub, mas ainda não fizemos nenhuma conexão entre eles.
Acesse seu GitHub e na página inicial você encontrará o botão <img src="/img/git_start/newrepo.png" class="inline img-responsive" width="130px"></p>

<p>Crie o repositório com o nome que desejar, neste exemplo vou usar <strong>Tutorial</strong>.
Após criado, o repositório já exibirá os comandos necessários para iniciar e configurar o seu repositório localmente.
Como já criamos o repositório localmente e queremos subí-lo no GitHub seguiremos com a opção <em>“push an existing repository from the command line”</em>.
Primeiro devemos configurar qual o repositório remoto. Execute usando a URL do seu repositório:</p>

<div class="language-sh highlighter-rouge"><div class="highlight"><pre class="highlight"><code>git remote add origin <a class="vglnk" href="https://github.com/BrOrlandi/Tutorial.git" rel="nofollow"><span>https</span><span>://</span><span>github</span><span>.</span><span>com</span><span>/</span><span>BrOrlandi</span><span>/</span><span>Tutorial</span><span>.</span><span>git</span></a>
</code></pre></div></div>
<p>Com isso você configurou o remote <code class="highlighter-rouge">origin</code> para o GitHub. Você já pode subir seus commits para lá usando <code class="highlighter-rouge">git push</code>, mas na primeira vez o comando deve ser executado para configurar a branch <code class="highlighter-rouge">master</code> para o GitHub. Opa, logo falarei sobre branchs em outro post. Ao executar o comando será solicitado o usuário e senha para autenticar no GitHub.</p>

<div class="language-sh highlighter-rouge"><div class="highlight"><pre class="highlight"><code>git push <span class="nt">-u</span> origin master
</code></pre></div></div>

<p>Olhe o repositório no GitHub e verá seu arquivo <strong>README.md</strong> lá e exibido na página inicial do repositório.
Pronto, você aprendeu os principais comandos para se trabalhar com Git. Git é uma ótima ferramenta para se trabalhar em equipe também mas apenas estes comandos não são suficientes.</p>

<h2 id="sincronize-o-repositório">Sincronize o repositório</h2>

<p>Você pode editar os arquivos de texto direto no GitHub. Vamos editar o README.md lá, clique nele e sem seguida clique no botão de editar <i class="fa fa-pencil"></i>.
Ao final da tela de edição você deverá preencher uma mensagem de commit. Sim, você está fazendo um commit direto pelo GitHub.</p>

<p>Agora o repositório possui dois commits no GitHub e no seu computador apenas um. Para sincronizar o seu repositório você deve puxar as atualizações.</p>

<div class="language-sh highlighter-rouge"><div class="highlight"><pre class="highlight"><code>git pull
</code></pre></div></div>
<p>Você verá que seu repositório local foi atualizado com o novo commit.</p>

body></html>
