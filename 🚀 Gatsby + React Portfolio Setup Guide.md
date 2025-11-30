🚀 Gatsby + React Portfolio Setup Guide
PART 1: Local Terminal Setup (Run These First)
You must run these commands in your local terminal to prepare your project environment.

1. Install Prerequisites
Make sure you have Node.js (which includes npm) and Git installed.
Just run the installer file.

2. Install Gatsby CLI and Create Project
This command installs the Gatsby command-line tool and then creates a new folder (my-react-portfolio) with all the necessary boilerplate files.
# Install Gatsby CLI globally
npm install -g gatsby-cli

# Create a new project using the default starter template
gatsby new my-react-portfolio

# Navigate into your new project directory
cd my-react-portfolio
That's a very common situation! Since you're on Windows and don't have npm installed, the initial steps for setting up the environment change slightly. We need to get Node.js (which includes npm) installed first, and then we can proceed with the React/Gatsby setup.

Here is the updated step-by-step guide focusing on the necessary installations for a Windows environment.

🛠️ Updated Setup Guide for Windows
PART 1: Installing Node.js (and npm)
You can use the official Node.js installer, which is the easiest way to get both Node and the Node Package Manager (npm) working on Windows.

1. Download the Installer
Go to the official Node.js website:


Shutterstock
Explorar
Download the LTS (Long-Term Support) version. This is the most stable version and is recommended for most users.

2. Run the Installer
Run the downloaded .msi file.

Follow the prompts. Accept the default settings, especially the one that says, "Add to PATH." This is crucial for running npm commands from any directory in your Command Prompt or PowerShell.

3. Verify the Installation
Open a new Command Prompt (or PowerShell) window.

Check the versions of Node and npm:

Bash

node -v
npm -v
You should see version numbers displayed for both, confirming a successful installation.

PART 2: Project Setup and Dependencies
Now that you have npm, you can proceed with the React/Gatsby setup as planned.

1. Install Gatsby CLI and Create Project
Navigate to the directory where you want your portfolio code to live (e.g., your Desktop or a Projects folder) and run:

Bash

# Install Gatsby CLI globally
npm install -g gatsby-cli

# Create a new project using the default starter template or choose a template
gatsby new my-react-portfolio
Or use this to use the template: https://github.com/LekoArts/gatsby-starter-portfolio-cara?tab=readme-ov-file
# Navigate into your new project directory
cd my-react-portfolio

2. Install Remaining Dependencies
Now we install the necessary packages for deployment and styling:

Bash

# Install gh-pages (for GitHub deployment) and Tailwind CSS tools
npm install gh-pages tailwindcss postcss autoprefixer gatsby-plugin-postcss

FASE 1: Configuração do Git e do Repositório
1. Criar Repositório no GitHub
AÇÃO: No seu navegador, vá ao GitHub e crie um novo repositório público.

Nome do Repositório (Exemplo): my-react-portfolio

IMPORTANTE: Não adicione README, licença ou .gitignore (o Gatsby já criou o seu próprio).

2. Inicializar o Git Localmente
Volte ao terminal (dentro da pasta my-react-portfolio) e siga os passos padrão para conectar o seu código ao repositório remoto.

Bash

# Inicializa o Git no seu projeto
git init

# Adiciona todos os ficheiros do projeto (código React, configuração, etc.)
git add .

# Faz o primeiro commit
git commit -m "feat: Initial React and Gatsby portfolio setup"

# Substitua 'YOUR-USERNAME' e 'my-react-portfolio' pelos seus dados
# Conecta o repositório local ao seu repositório GitHub
git remote add origin https://github.com/YOUR-USERNAME/my-react-portfolio.git

# Envia o código fonte (React) para a branch principal (main)
git push -u origin main
FASE 2: Atualização do pathPrefix
Quando hospeda um site em username.github.io/REPOSITORIO-AQUI/, o Gatsby precisa saber o nome do repositório para garantir que todos os links e assets (CSS, JS) sejam carregados corretamente.

AÇÃO: Abra o ficheiro gatsby-config.js na raiz do seu projeto e substitua o placeholder pelo nome exato do seu repositório que acabou de criar no GitHub.

AÇÃO: Depois de editar o gatsby-config.js, salve o ficheiro e faça um commit da alteração:

Bash

git add gatsby-config.js
git commit -m "fix: set path prefix for github pages deployment"
git push

---

## FASE 3: O Comando de Deployment Mágico

O seu ficheiro `package.json` já contém o script `deploy`. Este script executa as duas ações necessárias para o GitHub Pages:

1.  `gatsby build --prefix-paths`: Constrói o site em HTML estático e aplica o `pathPrefix`.
2.  `gh-pages -d public`: Pega nos ficheiros estáticos da pasta `public/` e envia-os para uma nova branch no GitHub chamada **`gh-pages`**.



**AÇÃO:** Execute o comando final no seu terminal:

```bash
npm run deploy
```
Isto irá demorar alguns minutos. Quando terminar, verá mensagens de sucesso sobre o *build* e o *push* para a branch `gh-pages`.


## FASE 4: Ativar o GitHub Pages (Passo Final no Navegador)

O código estático está no GitHub, mas ainda precisa de dizer ao GitHub para servir o site a partir dessa branch.

1.  Vá ao seu repositório no GitHub (`https://github.com/YOUR-USERNAME/my-react-portfolio`).
2.  Clique no separador **`Settings`** (Definições).
3.  No menu lateral, clique em **`Pages`**.
4.  Em "Build and deployment" > "Source":
    * Selecione **`Deploy from a branch`**.
    * Selecione a **Branch** como **`gh-pages`** e a pasta como **`/ (root)`**.
    * Clique em **Save**.

Após alguns instantes (pode demorar até 10 minutos), o seu portfólio React estará **AO VIVO** em:

`https://YOUR-USERNAME.github.io/my-react-portfolio/`


# Para editar o site:

Abre o terminal na pasta do projeto.
Corre ```npm run develop```
Abre http://localhost:8000 no browser.
Faz as alterações no código (o site atualiza-se sozinho enquanto editas).

# Para publicar as alterações:

Quando estiveres satisfeito com o que vês no localhost:
Para o servidor (Ctrl + C).
Corre ```npm run deploy```
Espera uns minutos e vê o resultado no teu link do GitHub.