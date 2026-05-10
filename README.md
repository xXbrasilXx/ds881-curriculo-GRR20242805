# Projeto Individual: Currículo Online DS881 - GRR20242805

Este repositório contém a atividade prática da disciplina DS881, focada em conteinerização, automação de pipeline CI/CD e governança de código. O projeto consiste em um currículo profissional estático hospedado no GitHub Pages.

**[Acesse o Currículo em Produção](https://xXbrasilXx.github.io/ds881-curriculo-GRR20242805/)**

---

## Tecnologias Utilizadas

- **Ambiente:** Docker & Docker Compose
- **Gerenciador de Build/Server:** Vite
- **Linter/Análise Estática:** Prettier
- **Pipeline CI/CD:** GitHub Actions
- **Hospedagem:** GitHub Pages

---

## Execução do Ambiente Local (Docker)

Para garantir que o projeto rode sem a necessidade de instalar dependências locais (Node.js/Vite), utilize a infraestrutura Docker configurada.

1.  Certifique-se de ter o **Docker** e o **Docker Compose** instalados.
2.  Clone este repositório.
3.  Na raiz do projeto, execute o comando:
    ```bash
    docker-compose up --build
    ```
4.  Acesse o servidor de desenvolvimento em: `http://localhost:8080`.
    - _Nota: O mapeamento de volumes (Bind Mounts) está configurado para garantir o **Hot Reload** automático no navegador ao salvar alterações nos arquivos._

---

## Governança de Código e Git Flow

Seguindo as boas práticas de desenvolvimento:

- **Branch Protection:** A branch `main` está protegida contra pushes diretos.
- **Pull Requests:** Toda alteração é integrada via PR, exigindo que o pipeline de CI esteja com status "verde".
- **Conventional Commits:** O histórico de commits segue o padrão (ex: `feat:`, `fix:`, `ci:`, `style:`).

### Configuração de Branch Protection

Conforme exigido, a regra de proteção aplicada impede merges sem o sucesso dos status checks (Lint e Build).

![](<img/Captura de tela 2026-05-10 182308.png>)
![](<img/Captura de tela 2026-05-10 182340.png>)
![](<img/Captura de tela 2026-05-10 182154.png>)
![](<img/Captura de tela 2026-05-10 182221.png>)

---

## Pipeline CI/CD

O workflow automatizado em `.github/workflows/main.yml` executa as seguintes etapas em cada Pull Request e após o Merge na `main`:

1.  **Linter/Static Analysis:** Validação de padrões de código via Prettier.
2.  **Build:** Compilação e minificação dos ativos estáticos via Vite.
3.  **Deploy:** Publicação automática no GitHub Pages (disparada apenas após o merge na branch `main`).

---

## Autor

- **Nome:** Gabriel de Paula Brasil
- **GRR:** 20242805
- **Curso:** Tecnologia em Análise e Desenvolvimento de Sistemas (TADS) - UFPR
