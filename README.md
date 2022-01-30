## 📚Desafio de Projeto sobre Git/Github da DIO
Repositório criado para o desafio de projeto

# 🔑Algumas Coisas Importantes
Comandos importantes do Prompt de Comando (também utilizado no Git):

cls(win), clear(git, linux) - para apagar todo o histórico de comandos do prompt;

cd(win, git, linux) - para se transitar entre as pastas dos diretórios, também há a variante "cd .." para retornar à pasta anterior;

dir(win), ls(git, linux) - para mostrar a lista de diretórios contidos na pasta em que estiver, também há a variante dir -a(win), ls -a(git, linux) para mostrar inclusive os diretórios ocultos ;

mkdir(win, git, linux) - para criar uma pasta no diretório;

echo(win, git, linux) - retorna o que for inserido, entretanto se utilizado como "echo > nome.extensão", ele cria o arquivo na extensão desejada, ótimo para criar um readme bem rápido sem sair do git em?! :happy:

start(win, git, linux) - inicia um arquivo executável de qualquer tipo;

TAB - Sim, a tecla TAB tem a incrível função de abreviar algo que você deseja escrever, extremamente útil e vai agilizar muito a sua vida!

# Comandos de iniciação do Git:

git init - inicia o versionamento na pasta em que estiver;

git config --global user.email "email" - configura o ambiente de versionamento para todos os repositórios, com essa identificação de e-mail; em caso da necessidade de alterar isso posteriormente, use git config --global unset user.email;

git config --global user.name "username" - configura o ambiente de versionamento para todos os repositórios, com essa identificação de usuário no github (é importante ressaltar que os dados aqui, devem refletir o usuário no Github); em caso da necessidade de alterar isso posteriormente, use git config --global unset user.name
git config --list - mostra todos os parâmetros da configuração atual do Git; para sair, use a tecla q;

git remote add nome (link) - direciona seu repositório local para um repositório na nuvem, o parâmetro NOME é apenas um apelido para que você possa referenciar o link sem tê-lo que mencionar novamente; você também pode posteriormente utilizar o comando git remote -v para consultar o repositório que está recebendo os arquivos locais.

# A configuração do ambient com Git/Github com chave SSH:

Use o código abaixo no Git, para gerar uma chave SSH;

$ ssh-keygen -t ed25519 -C "seu_email@example.com"
cat (chave gerada) - use esse comando (git, linux) para "ler" o conteúdo da chave, em seguida vá até a página principal no Github>settings>SSH and GPG keys>New SSH key em seguida insira o seu conteúdo da chave no campo "key".

Calma que ainda não acabou!😆 Agora no Git Bash, você precisa executar o agente para que gerencie suas chaves.

$ eval "$(ssh-agent -s)"
A saída do comando será "> Agent pid (número_qualquer)", o agente continuará executando em segundo plano. Agora como última etapa, você deve passar a chave privada para o agent com o seguinte código:

$ ssh-add "chave privada"
Pronto!🤝 Agora você pode usar todas as funcionalidades do git sem precisar se identificar o tempo todo.

# Comandos git:

git add .      - inserir os arquivos que você quer controlar. Normalmente a gente controla TUDO o que está no projeto.

git commit -m "Primeiro commit - Inserindo os arquivos iniciais do projeto"   - enviar uma alteração para o Git

git clone https://github.com/tableless/exemplos.git   - Para clonar um projeto você precisa ter a URL do Git daquele projeto em específico. 

git status  - você consegue ver quais arquivos estão fora do controle, quais foram modificados e estão esperando por uma descrição de modificação etc

git commit -a -m "Mensagem do commit" - Adicionando e comitando ao mesmo tempo

git log - Verificando o histórico de commits

git pull   - Sincronizando tudo que está no repositório remoto


### 📚Desafio de Projeto sobre Git/Github da DIO
##GIT - Primeiros passos
#Instalação e configurações básicas
1. Baixe e instale o Git

==================

2. Configurar chave de segunça

Permita copiar a chave RSA deles (Github, GitLab e etc) e copie a sua chave pública RSA no site que usará como repositório (Isto é feito apenas agora na configuração do git).

O arquivo da chave pública fica em: C:\Users\nomepc\.ssh
Copie o arquivo .pub
O arquivo pode ser gerado pelo Git GUI em: menu > ajuda > mostrar chave SSH
Cole o código da chave no site do repositório que você usa, isso geralmente fica localizado no perfil de configuração (no github e gitLab)
Caso não haja chave em seu computador, ela pode ser gerada pelo comando ssh-keygen. Mais informações aqui

==================

3. Abra o Git

Após a instalação, estará disponível duas formas de utilização do Git: O Git Bash e o Git GUI. O Git GUI é a forma gráfica de utilização do Git, o Git Bash é a forma por comando, como num prompt, e será esta a que utilizaremos. Para começar, abra o git bash:

Clique no logo do Git Bash
Entre com o caminho da pasta onde irá trabalhar: cd C:/caminho/caminho/nomepasta/
Ou, você pode abrir o Git Bash direto na pasta:

Entre na pasta que irá trabalhar
Clique com o botão direito do mouse e selecione a opção git bash
para facilitar, você pode deixar seu repositório local dentro da pasta www (do localhost). Assim, você poderá testar suas mudanças antes de enviar as mudanças.

==================

4. Inicialize o Git

Até aqui a pasta que você abriu no git é um diretótio como qualquer outro, o Git ainda não o reconhece como um repositório local. Para identificar a pasta como repositório local git, você precisa inicializar o git. No Git Bash, digite:

git init
Após isso, será criado um arquivo oculto .git em sua pasta. Este arquivo é o que guradará suas configurações, não o delete.

==================

5. Configure sua conta

Agora, você configurará seus dados de conta:

git config --global user.name "seuNomeDeUsuario"
git config --global user.email "meu_nome@email.com"
==================

6. Clonando um repositório

Neste ponto seu repositório local já está pronto para funcionar, porém ainda não sabe com o que irá sincronizar as informações que aqui estarão. Agora, iremos clonar um repositório já existente em algum site de versionamento (gitHub, GitLab..) para seu computador. Digite o link disponível no reporsitório sobre o seu projeto. Ex.:

git clone git@gitlab.com:nome/nomeProjeto.git
Isto deve ser feito apenas uma vez. Uma vez clonado, o todas as alterações estarão disponíveis para enviar para o site.

Quando o repositório tiver mais de um branch, e você não quiser clonar o principal, especifique o branch que deseje assim:

git clone endereco/do/repo --branch nomeDoBranch
Usando o Git: Comando básicos de utilização
1. Entrar na pasta

No git bash, certifique-se de estar na pasta que foi definida como seu repositório local. Caso não esteja, entre:

Clique no logo do Git Bash
Entre com o caminho da pasta onde irá trabalhar: cd C:/caminho/caminho/nomepasta/
Ou, você pode abrir o Git Bash direto na pasta:

Entre na pasta que irá trabalhar
Clique com o botão direito do mouse e selecione a opção git bash
==================

2. Puxar os dados do repositório

Para ter seu repositório local sempre sincronizado/atualizado com o repositório online, você precisará puxar as alterações:

Para isso, digite o comando: git pull origin master
O master significa que o projeto é master. Ele pode estar como Alpha ou outro nome. Caso não tenha certeza, é possível dar pull com apenas o comando git pull origin

==================

3. Enviar os arquivos ao repositório remotamente

git remote add origin git@github.com:username/projeto.git

git push -u origin master

==================

4. Ver status dos arquivos

Para saber o status dos arquivos, ver quais foram modificados, se já estão add pra commit e etc. use:

git status
Sempre que for modificado qualquer arquivo de dentro da pasta do projeto, ele aparecerá em vermelho. Permanecerão assim até serem add.

Em verde, aparecerão os que já estiverem prontos para serem commitados.

==================

4.1. Status com mais detalhes

Existe outro comando para ver mais detalhes sobre os arquivos modificados:

git diff
Apresentará os arquivos modificados com detalhes das linhas adicionadas e excluídas (assim como aparece no github após o push).

Adcionando a referência --staged e --cached.

git diff --staged é posssivel comparar o as alterações feitas com o último commit.

git diff --cached apresenta o que está sendo mudado até o momento.

Os dois, --cached e --staged são sinônimos.

=================

5. Adicionando a lista de mudanças

Para adicionar arquivos à lista para commit:

Para adicionar todos os arquivos que modificou, digite o código:
git add .
Para adicionar a lista de commit os arquivos que foram escluídos:
git add -u
Para adicionar algum arquivo específico:
git add nome-do-arquivo.xx
Caso já tenha adicionado um arquivo mas depois (antes de dar commit) tenha o modificado, o adicione novamente para que as mudanças sejam atualizadas.

É possível, também, desfazer a adição de algum arquivo, para isso, use o código:

git reset HEADnome-do-arquivo.xx
Também podemos adicionar e commitar ao mesmo tempo, basta adicionar a tag -a:

git commit-a-m "Mensagem do commit"
==================

6. Commitando as mudanças

É preciso commitar os arquivos adicionados antes de enviá-los. Isso serve para dar um nome ao envio, e seu envio automaticamente receberá uma numeração que o identificará:

git commit -m "Descrição da mudança feita"
faça uma descrição referente a mudança realizada.

Ao fazer o commit, é possível referenciar uma ensue criada no site de versionamento usando uma # + número da insue. Exemplo:

git commit -m "Descrição da mudança feita #20 "
É possível, também, adicionar e commitar ao mesmo tempo, basta adicionar a tag -a:

git commit-a-m "Mensagem do commit"
Uma insue é uma tarefa criada no site. Asim, a mudança ficará lincada à tarefa automaticamente

6.1. Voltando um commit

Caso tenha feito um commit e deseje desfaze-lo, digite:

git reset HEAD~1
Isso fará com que o commit último commit seja desfeito, caso deseje voltar mais commits basta mudar o número que vem depois do head~. O número corresponde ao número de commits que irá voltar.

Voltando dois: git reset HEAD~2
6.2. Ver histórico de commits

git log
Para que este seja mostradas as diferenças entre os commits adicione o -p

git log -p
Verificando os últimos 2 commits: git log -p -2
==================

7. Enviando os arquivos

Essa é a última parte da atualização, ele enviará para o repositório (gitlab, github..) as alterações feitas.

git push origin master
O master significa que o projeto é master. Ele pode estar como Alpha ou outro nome. Caso não tenha certeza, é possível dar pull com apenas o comando git pull origin



