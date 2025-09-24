# 🚀 Landing Page com CI/CD usando GitHub Actions + Vercel

Este projeto é uma **landing page simples** construída com **HTML + TailwindCSS**, configurada com **CI/CD (Continuous Integration / Continuous Deployment)** utilizando o **GitHub Actions** para automação e a **Vercel** para deploy.

---

## 📌 Objetivo

O propósito deste repositório é demonstrar como aplicar boas práticas de **CI/CD** em projetos simples:

* **CI (Integração Contínua):** garante que o código siga padrões e seja formatado automaticamente com **Prettier**.
* **CD (Entrega Contínua):** realiza o **deploy automático** na Vercel sempre que houver alterações no repositório ou no horário agendado (02:00 AM UTC).

---

## ⚙️ Como funciona o Workflow

1. **Prettier Auto Format**

   * A cada `push` ou `pull request` na branch `main`, o GitHub Actions roda o Prettier e formata o código.
   * Caso haja mudanças, o bot do GitHub (`github-actions[bot]`) commita automaticamente as correções.

2. **Deploy Automático**

   * Após o Prettier, o workflow dispara o deploy para a **Vercel**.
   * O deploy também é agendado para rodar **todos os dias às 02:00 da manhã (UTC)** automaticamente.

---

## 🛠️ Como reproduzir

### 1. Clonar o repositório

```bash
git clone https://github.com/seu-usuario/nome-do-repo.git
cd nome-do-repo
```

### 2. Instalar dependências (opcional, se for usar Prettier localmente)

```bash
npm install
```

### 3. Configurar a Vercel

* Crie um projeto na [Vercel](https://vercel.com/).
* Pegue os seguintes dados:

  * `VERCEL_TOKEN`
  * `VERCEL_ORG_ID`
  * `VERCEL_PROJECT_ID`
* No GitHub, vá em **Settings > Secrets and variables > Actions** e adicione cada um como **secret**.

### 4. Estrutura do Workflow

O workflow fica em:

```
.github/workflows/ci.yml
```

Ele contém dois jobs:

* `format` → roda Prettier e commita mudanças.
* `deploy` → dispara o deploy na Vercel.

### 5. Rodando localmente (opcional)

Você pode rodar o Prettier localmente antes de commitar:

```bash
npx prettier --write .
```

---

## 📖 Benefícios do CI/CD

✅ Padronização automática do código com Prettier.
✅ Deploy contínuo sem esforço manual.
✅ Agendamento garante que o site seja atualizado diariamente.
✅ Histórico limpo com commits automáticos do GitHub Actions.

---

## 🚀 Deploy

O deploy é feito automaticamente na Vercel. Após configurar os secrets, basta commitar na branch `main` e aguardar a execução do GitHub Actions.

---

## 📜 Licença

Este projeto é apenas para fins de estudo/demonstração. Pode ser utilizado e modificado livremente.
