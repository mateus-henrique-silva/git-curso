# Guia Básico de Configuração do GitHub

Este guia vai te ensinar os passos iniciais para configurar o GitHub após criar sua conta no site. Vamos configurar seu Git, criar um repositório, conectar seu projeto local ao GitHub e enviar seu código para a plataforma.

## Sumário

1. [Instalar o Git](#instalar-o-git)
2. [Configurar o Git](#configurar-o-git)
3. [Criar um Repositório no GitHub](#criar-um-repositorio-no-github)
4. [Clonar o Repositório no Seu Computador](#clonar-o-repositorio-no-seu-computador)
5. [Adicionar Arquivos ao Repositório](#adicionar-arquivos-ao-repositorio)
6. [Fazer Commits e Enviar para o GitHub](#fazer-commits-e-enviar-para-o-github)
7. [Configurar Chave SSH (Opcional)](#configurar-chave-ssh-opcional)

---

## 1. Instalar o Git <a name="instalar-o-git"></a>

Se você ainda não instalou o Git, é necessário instalá-lo no seu sistema.

### Instalação no Windows:

1. Acesse [o site oficial do Git](https://git-scm.com/).
2. Baixe e execute o instalador para Windows.
3. Durante a instalação, aceite as configurações padrão e conclua.

### Instalação no Linux (Debian/Ubuntu):

```bash
sudo apt update
sudo apt install git
```

### Instalação no MacOS:

```bash
brew install git
```

Após a instalação, verifique se o Git foi instalado corretamente:

```bash
git --version
```

---

## 2. Configurar o Git <a name="configurar-o-git"></a>

Depois de instalar o Git, você precisa configurá-lo com suas credenciais de usuário. Essas informações serão usadas para associar suas alterações (commits) ao seu nome e email.

1. Configure seu nome:

   ```bash
   git config --global user.name "Seu Nome"
   ```

2. Configure seu email (use o email associado à sua conta GitHub):

   ```bash
   git config --global user.email "seuemail@exemplo.com"
   ```

3. Verifique suas configurações:

   ```bash
   git config --list
   ```

---

## 3. Criar um Repositório no GitHub <a name="criar-um-repositorio-no-github"></a>

Agora que você já configurou o Git no seu sistema, vamos criar um repositório no GitHub.

1. Acesse o [site do GitHub](https://github.com/) e faça login com sua conta.
2. Clique no botão **New** no topo da página ou no menu **+** e selecione **New Repository**.
3. Preencha as seguintes informações:
   - **Repository name**: Dê um nome ao seu repositório (por exemplo, "meu-primeiro-repo").
   - **Description**: Descrição do repositório (opcional).
   - Escolha entre **Public** (público) ou **Private** (privado).
   - Marque a opção **Initialize this repository with a README** para criar um arquivo README automaticamente.
4. Clique em **Create repository**.

---

## 4. Clonar o Repositório no Seu Computador <a name="clonar-o-repositorio-no-seu-computador"></a>

Agora que o repositório foi criado, vamos cloná-lo no seu computador para começar a trabalhar localmente.

1. No seu repositório GitHub, clique no botão **Code** e copie o link HTTPS (ou SSH, se configurado).
2. No terminal, navegue até a pasta onde você deseja clonar o repositório e execute o seguinte comando:

   ```bash
   git clone https://github.com/usuario/meu-primeiro-repo.git
   ```

Substitua o link pelo URL do seu repositório.

---

## 5. Adicionar Arquivos ao Repositório <a name="adicionar-arquivos-ao-repositorio"></a>

Com o repositório clonado no seu computador, agora você pode adicionar arquivos.

1. Navegue até o diretório do repositório:

   ```bash
   cd meu-primeiro-repo
   ```

2. Crie ou adicione arquivos ao diretório, por exemplo:

   ```bash
   echo "print('Olá, mundo!')" > hello.py
   ```

3. Adicione os arquivos ao controle de versão com o comando:

   ```bash
   git add .
   ```

O comando `git add .` adiciona todos os arquivos novos ou modificados.

---

## 6. Fazer Commits e Enviar para o GitHub <a name="fazer-commits-e-enviar-para-o-github"></a>

Agora que você adicionou seus arquivos, é hora de fazer o commit e enviá-los para o GitHub.

1. Faça o commit das suas alterações com uma mensagem descritiva:

   ```bash
   git commit -m "Adiciona script hello.py"
   ```

2. Envie as alterações para o GitHub:

   ```bash
   git push origin main
   ```

Se estiver usando outra branch, como `master`, substitua `main` por `master` ou o nome da branch correta.

---

## 7. Configurar Chave SSH (Opcional) <a name="configurar-chave-ssh-opcional"></a>

Para evitar digitar suas credenciais sempre que fizer push ou pull, você pode configurar uma chave SSH.

1. Gere uma chave SSH no seu computador:

   ```bash
   ssh-keygen -t rsa -b 4096 -C "seuemail@exemplo.com"
   ```

2. Quando solicitado, pressione `Enter` para aceitar o local padrão para salvar a chave.

3. Adicione sua chave SSH ao ssh-agent:

   ```bash
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_rsa
   ```

4. Copie a chave SSH para o clipboard:

   ```bash
   cat ~/.ssh/id_rsa.pub
   ```

5. Vá até o GitHub, clique na sua foto de perfil no canto superior direito, depois em **Settings** > **SSH and GPG keys** > **New SSH Key**. Cole a chave que você copiou.

6. Agora, você pode clonar repositórios via SSH ou fazer push/pull sem precisar digitar a senha.

---

## Conclusão

Com essas etapas, você configurou o Git no seu computador, criou um repositório no GitHub, clonou-o e enviou suas alterações. Agora, você está pronto para colaborar em projetos e manter seu código versionado na nuvem.
