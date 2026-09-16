# FitTrack - Diário de Treinos Inteligente 🏋️‍♂️

Aplicativo web desenvolvido como avaliação (A1) da disciplina de **Desenvolvimento Híbrido** (Análise e Desenvolvimento de Sistemas). O sistema soluciona o problema de acompanhamento de progressão de carga na musculação, permitindo que usuários criem contas isoladas e gerenciem seus treinos diários em tempo real.

## 📋 Requisitos Atendidos (Escopo A1)
1. **Autenticação:** Sistema de login e cadastro seguro implementado (Firebase Auth via E-mail e Senha).
2. **Persistência de Dados:** Banco de dados na nuvem em tempo real (Firebase Firestore NoSQL).
3. **Privacidade e Isolamento:** Cada usuário possui acesso exclusivo aos próprios registros, garantido por consultas tipadas com o `uid` (User ID) exclusivo no Firestore.
4. **CRUD Completo:** O sistema suporta as 4 operações fundamentais (Create, Read, Update, Delete), superando o requisito mínimo da disciplina que exigia apenas duas operações.

---

## 🏗️ Decisões Arquiteturais e Ferramentas

Durante a concepção do projeto, as seguintes tecnologias e padrões foram escolhidos para compor a stack:

* **React JS + Vite:** Escolhido como biblioteca front-end pelo seu ecossistema maduro e renderização baseada em componentes. O Vite foi preferido por oferecer um carregamento de servidor local extremamente rápido (HMR) e um pacote final otimizado.
* **Firebase Authentication:** Utilizado para delegar a responsabilidade de segurança (hashing de senhas e controle de sessões). Isso elimina a necessidade de construir um servidor backend complexo do zero apenas para gerenciar credenciais.
* **Firebase Firestore (NoSQL):** Adotado devido à sua natureza reativa ("Realtime"). O uso do ouvinte `onSnapshot` permite que a tela de treinos atualize instantaneamente quando um dado é modificado, melhorando drasticamente a Experiência do Usuário (UX).
* **CSS Semântico e Clean Code:** Todo o design foi isolado em um único arquivo de estilos (`App.css`). Frameworks utilitários foram descartados para respeitar o princípio da **Separação de Preocupações (Separation of Concerns)**. Manter o CSS isolado com nomenclaturas de classes semânticas (ex: `.cartao-login`, `.btn-primario`) melhora a legibilidade do código JSX e facilita a manutenção estrutural do sistema.
* **Variáveis de Ambiente (`.env`):** Decisão fundamental de segurança cibernética. Arquivos `.env` protegidos via `.gitignore` garantem que as chaves da API do banco de dados nunca sejam expostas no código público hospedado no GitHub.
* **Metodologia GitHub Flow:** O desenvolvimento foi gerenciado por meio de **Issues** e **Pull Requests (PRs)** divididos em quatro etapas independentes, garantindo rastreabilidade e integridade na branch principal (`main`).

---

## 👥 Divisão de Tarefas da Equipe (Issues)

O projeto foi construído em grupo seguindo um fluxo corporativo de Engenharia de Software:
* **Issue #1 (Setup):** Inicialização do projeto base com React/Vite, configuração do ambiente e proteção de credenciais via `.env`.
* **Issue #2 (Auth):** Criação da interface de autenticação e integração com o Firebase Authentication.
* **Issue #3 (CRUD):** Implementação do painel de controle (Dashboard) e conexão com o Firestore (Create, Read, Update, Delete com isolamento por `userId`).
* **Issue #4 (Clean Code & UI):** Refatoração da arquitetura visual para o arquivo `App.css` com classes semânticas e padronização de nomenclatura.

---

## 🚀 Guia de Instalação Local (Passo a Passo)

Para executar esta aplicação em ambiente de desenvolvimento, certifique-se de ter o [Node.js](https://nodejs.org/) e o [Git](https://git-scm.com/) instalados na sua máquina.

### 1. Clonar o repositório
Abra o seu terminal e execute os comandos abaixo para baixar o código e entrar na pasta do projeto:
```bash
git clone [https://github.com/JM-762/FitTrack-app.git](https://github.com/JM-762/FitTrack-app.git)
cd FitTrack-app
