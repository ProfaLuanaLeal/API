# API - Back end Profa Luana Leal
Para o seu **README.md** no GitHub, é importante usar uma linguagem que conecte a teoria da aula (Arquitetura e Microsserviços) com a prática que eles acabaram de ver no Codespaces. 

Aqui está um modelo estruturado e "escaneável" para você copiar e colar:

---

# 📚 Guia de Conceitos: API & Node.js

Este repositório serve como laboratório prático para entender como a Web moderna funciona por debaixo do capô. Abaixo, explicamos os dois pilares deste projeto:

---

## 🔌 O que é uma API? (Application Programming Interface)

Imagine que uma API é um **garçom** em um restaurante:
1. Você (o **Cliente/Front-end**) olha o cardápio e faz um pedido.
2. O garçom (a **API**) leva seu pedido até a cozinha.
3. A cozinha (o **Servidor/Back-end**) prepara a comida.
4. O garçom traz a comida (os **Dados**) de volta para você.

No nosso projeto, a **Open Library API** é a "cozinha" que tem milhões de livros. Nossa aplicação Node.js é o "garçom" que vai lá buscar apenas o que o usuário digitou.

### Por que usamos APIs?
* **Interconectividade:** Permite que sistemas diferentes (como o nosso e o da Open Library) conversem.
* **Segurança:** O cliente não acessa o banco de dados diretamente, apenas o que a API permite.
* **Padronização:** Os dados trafegam no formato **JSON**, que é leve e fácil de ler.



---

## 🟢 O que é o Node.js?

O **Node.js** não é uma linguagem de programação, mas sim um **ambiente de execução** (runtime) que permite usar JavaScript fora do navegador (no servidor).

### Características que você verá neste código:
* **Event-Driven:** O Node consegue lidar com várias requisições ao mesmo tempo sem travar.
* **npm (Node Package Manager):** Usamos para instalar o **Express**, o framework que gerencia nossas rotas.
* **Performance:** Ideal para construir Microsserviços rápidos e escaláveis.



---

## 🏗️ A Arquitetura deste Projeto

Neste laboratório, seguimos uma estrutura de **Responsabilidade Única**:

1.  **Front-end (`index.html` e `style.css`)**: A interface visual que o usuário interage.
2.  **Back-end (`server.js`)**: Onde a mágica acontece. Ele recebe a rota, faz a requisição "Back-to-Back" para a Open Library e devolve o resultado limpo para o usuário.

> **Dica para o Aluno:** Observe como o arquivo `server.js` usa o `fetch` para consumir uma API externa. Essa é a base para criar integrações com meios de pagamento, mapas ou serviços de inteligência artificial.

---

### ✅ Como este projeto foi construído:
* **Gerenciador de Pacotes:** npm / pnpm.
* **Framework Web:** Express.js.
* **Consumo de Dados:** Fetch API (nativo do Node 18+).
* **Ambiente:** GitHub Codespaces.

---
Aqui está um **Guia de Instalação e Execução** detalhado para você copiar e colar no final do seu `README.md`. Ele foi pensado para que qualquer aluno, mesmo iniciante, consiga rodar o projeto no **GitHub Codespaces** sem erros.

---

## 🚀 Como Rodar o Projeto (Passo a Passo)

Siga estas etapas para colocar a API de busca de livros para funcionar no seu ambiente:

### 1. Preparação do Ambiente
Se você estiver no **GitHub Codespaces**, o Node.js já está instalado. Caso contrário, certifique-se de ter o Node.js (versão 18 ou superior) na sua máquina.

### 2. Instalação de Dependências
No terminal, na raiz do projeto, digite o comando abaixo para instalar o framework **Express**:
```bash
npm install
```
*Isso lerá o arquivo `package.json` e baixará tudo o que é necessário para a pasta `node_modules`.*

### 3. Executando o Servidor
Para iniciar a API, utilize o comando:
```bash
node server.js
```
Você verá a mensagem: `🚀 Servidor rodando em http://localhost:3000`.



### 4. Visualizando a Interface
1. O Codespaces exibirá um pop-up no canto inferior direito informando que uma porta foi aberta. Clique em **"Open in Browser"** (Abrir no Navegador).
2. Se o pop-up não aparecer, vá na aba **Ports** (ao lado do Terminal) e clique no ícone do globo 🌐 na linha da porta **3000**.

### 5. Testando a Busca
Na página que abrir:
1. Digite o nome de um livro ou autor no campo de busca (ex: *Dom Casmurro* ou *JavaScript*).
2. Clique no botão **Buscar**.
3. Os resultados aparecerão logo abaixo, vindos diretamente da **Open Library API**.

---

## 🛠️ Solução de Problemas (FAQ)

* **Erro: "app is not defined"**
    * *Causa:* Você tentou usar o `app` antes de criá-lo no código.
    * *Solução:* Certifique-se de que a linha `const app = express();` venha antes de qualquer `app.use` ou `app.get`.
* **Erro: "Cannot find module 'express'"**
    * *Causa:* O Express não foi instalado.
    * *Solução:* Rode `npm install express` no terminal.
* **A busca não retorna nada:**
    * *Causa:* Pode ser um erro de digitação na URL da API ou problema na sua conexão de internet.
    * *Solução:* Verifique o console do navegador (F12) para ver se há erros de rede.

---

### 📝 Desafio para o Aluno
Tente modificar o arquivo `style.css` para mudar a cor dos cartões de livros ou o arquivo `index.html` para exibir também o número de páginas (procure por `number_of_pages_median` no JSON da Open Library).

---
