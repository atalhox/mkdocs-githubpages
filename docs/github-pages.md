# Como automatizar o Github pages como Mkdocs

## 1. Introdução

O GitHub Pages é uma ferramenta poderosa que permite a publicação de páginas web diretamente de repositórios GitHub. Ao combinar o GitHub Pages com o MkDocs, é possível criar documentações elegantes e organizadas de forma simples. Este guia detalha como configurar e automatizar o deploy de um site utilizando estas ferramentas.

## 2. Objetivo

Fornecer um passo a passo claro e estruturado para:

- Criar um repositório no GitHub.
- Configurar e personalizar o MkDocs.
- Automatizar o deploy utilizando GitHub Actions.
- Configurar o GitHub Pages para publicação do site.

## 3. Público-alvo

Este documento é voltado para desenvolvedores, documentaristas e profissionais de tecnologia interessados em criar documentações técnicas ou sites informativos de maneira automatizada, utilizando ferramentas modernas.

## 4. Guia de uso

### 4.1. Criar o Repositório no GitHub

1. Acesse sua conta no GitHub.
2. Clique em “New Repository”.
3. Preencha os detalhes do repositório:
   - Nome: `my-project` (ou outro de sua escolha).
   - Privacidade: Configure como privado.
4. Clique em “Create Repository”.

### 4.2. Configurar MkDocs

#### Instalar o MkDocs

Se ainda não o tiver instalado, execute:

```bash
pip install mkdocs
```

#### Criar a Estrutura Inicial do MkDocs

No diretório desejado, crie a estrutura básica:

```bash
mkdocs new my-project
cd my-project
```

### 4.3. Modificar a Configuração do MkDocs

Edite o arquivo `mkdocs.yml` para personalizar o projeto. Exemplo de configuração:

```yaml
site_name: MKDocs

plugins:
  - mermaid2
  - search

theme:
  name: material
```

### 4.4. Configurar o Deploy com GitHub Actions

Crie o arquivo `.github/workflows/ci.yml` no repositório para automatizar o deploy:

```yaml
name: mkdocs

on:
  push:
    branches:
      - main

permissions:
  contents: write

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Configure Git Credentials
        run: |
          git config user.name github-actions[bot]
          git config user.email 41898282+github-actions[bot]@users.noreply.github.com
      - uses: actions/setup-python@v5
        with:
          python-version: 3.12.6
      - run: echo "cache_id=$(date --utc '+%V')" >> $GITHUB_ENV
      - uses: actions/cache@v4
        with:
          key: mkdocs-material-${{ env.cache_id }}
          path: .cache
          restore-keys: |
            mkdocs-material-
      - run: pip install mkdocs-material
      - run: pip install mkdocs-mermaid2-plugin
      - run: mkdocs gh-deploy --force
```

### 4.5. Configurar o GitHub Pages

1. Acesse o repositório no GitHub.
2. Navegue para a aba “Settings” > “Pages”.
3. Em “Build and Deployment”, selecione “Deploy from a branch”.
4. Escolha a branch `gh-pages` e o diretório `/`.
5. Clique em “Save”.
6. Agora, o site estará disponível para acesso público.

### 4.6. Exemplos de Recursos Adicionais

#### Mermaid

Renderize gráficos em Markdown utilizando o Mermaid. Exemplo:

```mermaid
graph TD;
    A[Start] --> B{Decision};
    B -- Yes --> C[Result 1];
    B -- No --> D[Result 2];
```

#### Emojis

Utilize emojis para enriquecer sua documentação.

Exemplo: `:smile:`= :smile:

## 5. Dicas

1. Siga as etapas descritas para configurar seu repositório e site.
2. Personalize o arquivo `mkdocs.yml` para atender às necessidades do seu projeto.
3. Realize commits e pushes para atualizar automaticamente o site via GitHub Actions.
4. Acesse seu site pelo link gerado no GitHub Pages.

## 6. Referências

- [Documentação do MkDocs](https://www.mkdocs.org/)
- [GitHub Actions](https://docs.github.com/en/actions)
- [GitHub Pages](https://pages.github.com/)
- [Mermaid.js](https://mermaid-js.github.io/)
