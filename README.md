# Currículo Online – DS881

Este repositório contém meu currículo profissional online, desenvolvido para a disciplina DS881 da UFPR.

🔗 **Site no ar:** ``

---

## Sobre o projeto

O site foi feito com HTML e CSS puro e está hospedado no GitHub Pages. Para garantir um ambiente de desenvolvimento consistente, usei Docker — assim qualquer pessoa consegue rodar o projeto localmente sem precisar instalar nada além do Docker.

---

## Como rodar localmente

Você vai precisar ter o [Docker](https://docs.docker.com/get-docker/) e o [Docker Compose](https://docs.docker.com/compose/install/) instalados.

Com isso, basta rodar na raiz do projeto:

```bash
docker compose up --build
```

O site vai estar disponível em `http://localhost:8080`.

O diretório local está mapeado para dentro do container, então qualquer alteração nos arquivos aparece na hora — só recarregar o navegador.

Para parar:

```bash
docker compose down
```

---

## Proteção da branch main

A branch `main` está protegida: não é possível fazer push direto nela. Toda alteração precisa passar por um Pull Request, e o merge só é liberado depois que o pipeline de CI roda com sucesso (lint + build).


---

## Pipeline de CI/CD

A cada Pull Request ou push na `main`, o GitHub Actions executa automaticamente:

1. **Lint** – verifica a sintaxe do HTML
2. **Build** – valida o Dockerfile e empacota os arquivos
3. **Deploy** – publica no GitHub Pages (só quando o merge acontece na `main`)
