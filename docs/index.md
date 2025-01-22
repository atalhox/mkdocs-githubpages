# Home

## 1. Introdução

MkDocs é uma ferramenta poderosa para geração de sites estáticos de documentação. Usando arquivos em Markdown, ela permite criar documentações organizadas, atrativas e de fácil navegação. Este documento fornece uma introdução aos conceitos fundamentais do MkDocs, desde a configuração inicial até a publicação.

[Começar Rápido](github-pages.md){: .md-button .md-button--primary }
[Ver no GitHub](https://github.com/atalhox/mkdocs-githubpages){: .md-button .md-button--secondary }

## 2. Objetivo

Este guia tem como finalidade capacitar o leitor a:

- Compreender os conceitos básicos do MkDocs.
- Criar e organizar um projeto de documentação.
- Configurar temas e personalizações.
- Publicar a documentação gerada.

## 3. Público-alvo

O material é voltado para:

- Desenvolvedores que precisam documentar seus projetos.
- Estudantes interessados em organização de materiais didáticos.
- Empresas que desejam criar manuais de processos internos.

## 4. O que é o MkDocs?

MkDocs é um gerador de sites estáticos para documentação, baseado em arquivos Markdown e configurado por um arquivo YAML simples (`mkdocs.yml`). Algumas de suas principais características incluem:

- **Simplicidade**: Configuração e utilização fáceis.
- **Flexibilidade**: Suporte a temas e plugins.
- **Publicação Rápida**: Deploy integrado para GitHub Pages e outros servidores.

## 5. Funcionalidades Principais

- Geração de sites responsivos.
- Navegação hierárquica com busca integrada.
- Extensa biblioteca de temas e plugins.
- Visualização ao vivo durante o desenvolvimento.

## 6. Fluxo de Trabalho Básico

1. **Instalação do MkDocs**:

   ```bash
   pip install mkdocs
   ```

2. **Criação de um Novo Projeto**:

   ```bash
   mkdocs new meu-projeto
   cd meu-projeto
   ```

3. **Execução do Servidor Local**:

   ```bash
   mkdocs serve
   ```

4. **Build do Site Estático**:

   ```bash
   mkdocs build
   ```

5. **Publicação no GitHub Pages**:

   ```bash
   mkdocs gh-deploy
   ```

## 7. Configuração Básica

A configuração do MkDocs é feita por meio do arquivo `mkdocs.yml`. Aqui está um exemplo simples:

```yaml
site_name: "Meu Projeto"
theme:
  name: mkdocs
nav:
  - Início: index.md
  - Sobre: sobre.md
```

Adicione seus arquivos Markdown no diretório `docs/` para criar o conteúdo do site.

## 8. Personalização

- **Temas**: Utilize temas como o "Material for MkDocs" para designs modernos.

  ```bash
  pip install mkdocs-material
  ```

  Atualize o arquivo `mkdocs.yml`:

  ```yaml
  theme:
    name: material
  ```

- **Plugins**: Adicione funcionalidades extras como tabelas ou busca aprimorada.

  ```yaml
  plugins:
    - search
    - table-reader
  ```

## 9. Referências

- [Site Oficial do MkDocs](https://www.mkdocs.org/)
- [Temas no MkDocs](https://www.mkdocs.org/user-guide/styling-your-docs/)
- [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)

## 10. Comandos Resumidos

- `mkdocs serve`: Executa um servidor local.
- `mkdocs build`: Gera os arquivos estáticos.
- `mkdocs gh-deploy`: Publica no GitHub Pages.

## 11. Estrutura do Projeto

Ao criar um projeto, a estrutura inicial é:

```bash
meu-projeto/
├── docs/
│   └── index.md
├── mkdocs.yml
```
