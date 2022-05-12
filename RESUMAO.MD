                                                   RASCUNHO DO GIT
                                              comandos do GIT - windows

-cd  / = sai de todas as pastas
-cd .. = sai de uma pasta
-cd  = entra na pasta
-dir ou ls  = lista os arquivos e pastas
-mkdir  cria pastas
- del = exclui pastas/arquivos
rmdir nome da pasta /s /q = exclui a pasta com tudo que tem dentro.
mv= move um arquivo ou pasta
clear  (CTRL + L)= limpa a tela
echo > nome.txt = cria arquivo
ls -a = lista os arquivos ocultos
git init = cria repositório, ou seja inicia o GIT
git add = inicia o versionamento do arquivo
git remote -v = visualiza o que está no repositório remoto
git push origin master = É usado para fazer upload de conteúdo em repositórios remotos para isso, o git pede a confirmação das credenciais do GITHUB.
git pull origin master = É um dos muitos comandos que têm a responsabilidade de "sincronizar" conteúdo remoto.
git status = mostra o status do repositório, em que modo se encontra o arquivo. comando muito importante, sempre é usado porque ele informa como está o ciclo de vida do arquivo, ou seja em qual fase ele se encontra.
git restore -staged <nomedoarquivo> = move o arquivo  que está na fase “stage” para UNTRACKED
git config --list = exibe toda lista que está no GIT

Para o primeiro acesso no GIT é necessário criar uma conta:
git config –global user.email “cleuzabcosta@gmail.com”
git config  --global user.name cleuzabcosta
caso você tenha a conta, porém quer mudar será preciso remover o atual para depois criar seguir os passos acima .
git config –global –unset user.email
git config –global -unset user.name

a)	git init = inicia o git, ou seja cria um repositório

OBS: Pode usar o HTML ou Markdown (md). Aqui usaremos o mais comum (md)

echo  “cleuza.md” = arquivo criado

OBS: No Windows/gerenciador de arquivos,  abre o arquivo escolha aplicativo txt: bloco de notas, wordpad,, Eu instalei o atom do GITHUB. Escreva algo no arquivo uma receita , artigo, etc.. salva.

b)	git add *  enter = inicia versionamento de todos os arquivos que estiver na pasta,

git add nome do arquivo = inicia versionamento de apenas desse arquivo indicado

c)	git commit -m “commit inicial”
Para indexar um arquivo
echo “readme.txt” =  cria-se o arquivo
git add * enter
git commit -m “adiciona index”
Enviando um arquivo para repositório remoto (GITHUB)
Acessar o GITHUB, entrar com suas credenciais.
Clicar no perfil/Seus repositórios, dá o caminho onde está o seu arquivo, depois informa o nome que você quer dar ao repositório. Seleciona a opção de um caminho que te dará e leva para o git:

git remote add origin https://github.com/cleuzabcosta/livro-receitas.git ENTER

FUNCIONAMENTO DO GIT – DEBAIXO DOS PANOS

1 – Sha1 = encripta  o arquivo ou seja, cria código com 40 dígitos. Identifica um arquivo de forma segura, inteligente e rápida

openss1 sha1 readme.txt = está encriptado.

2 – Objetos fundamentais: São três elementos responsável pelo versionamento do código
a)	 Blob = Contém metadados (\0),guarda o sha ( tamanho, tipo, conteúdo) do arquivo, mas não o arquivo em si.
b)	 Tree = Contém metadados (\0) guarda o nome do arquivo, aponta para vários blob diferentes.
c)	 Comit = Possui sha1 (encriptação) aponta para um TREE que sua vez pode aponta para vários tree, aponta também para PARENTE e AUTOR. Monta uma linha do tempo. Quando muda o arquivo muda toda a sua estrutura
OBS: Por isso o GIT é um sistema distribuído e seguro.

CICLO DE VIDA DOS ARQUIVOS NO GIT
O rastreio do GIT se dividem em três estágios onde os arquivos transitam:

TRACKED: São arquivos que o GIT tem ciência deles.
1 -  Unmodified = arquivo que ainda não foi modificado
2 – Working Directory (Modified) = arquivo que foi modificado, porque compara o sha1 dos arquivos
3 – Staging Área (Staged) = arquivo que está se preparando para fazer parte do COMMIT (repositório local). e o COMMIT retorna o arquivo para MODIFIED  para começar o ciclo de novo


UNTRACKED: São arquivos que o GIT ainda não tem ciência deles, ou seja não chegou até ele.

RESOLVENDO CONFLITOS
Quando o código está no repositório remoto e você escolhe a opção pública, outras pessoas podem acessar, corrigir ou fazer alteração e com isso entra em conflito com o código que está na sua máquina com o que está no remoto.


Para resolver isso segue procedimentos:
Terá que ser feito manualmente, abrir o arquivo que foi modificado, e analisar o que quer fazer se exclui, altera, permanece o mesmo, depois salva o arquivo. E volte no GIT e segue todo o procedimento para retorná-lo  no GITHUB.
São os seguintes passos:
git add *
git commit -m “resolve conflitos”
Usa os comandos:
push e pull
Copiando código de outra pessoa no GITHUB

NO GIT digita o seguinte comando que está no GITUHUB copia/cola
git clone
