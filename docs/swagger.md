# Como incorporar um swagger

## 1. Introdução

A integração do Swagger com o MkDocs permite a visualização e a documentação interativa de APIs diretamente no site gerado. Isso é especialmente útil para desenvolvedores que desejam fornecer uma referência visual e funcional de suas APIs RESTful, combinando a simplicidade do MkDocs com as capacidades interativas do Swagger UI.

## 2. Objetivo

O objetivo desta documentação é detalhar o processo de incorporação de uma interface Swagger (Swagger UI) em um site MkDocs, possibilitando a exibição de especificações OpenAPI de maneira interativa e fácil de acessar.

## 3. Público-alvo

Este documento é destinado a:

- Desenvolvedores que utilizam MkDocs para criar documentações técnicas.
- Equipes que desejam disponibilizar especificações de API interativas junto à documentação textual.
- Usuários com conhecimento básico de OpenAPI, YAML/JSON e estrutura de diretórios em projetos MkDocs.

## 4. Conteúdo Principal

### 4.1. Requisitos

- Python 3.6 ou superior.
- MkDocs instalado em sua máquina.
- Conhecimento básico sobre OpenAPI (especificações YAML ou JSON).
- Arquivo de especificação OpenAPI previamente criado (ex.: swagger.yaml).

### 4.2. Passo a Passo para Integração

#### Passo 1: Configuração do Ambiente

Certifique-se de que o MkDocs está instalado e configurado:

```bash
pip install mkdocs
```

#### Passo 2: Estrutura de Diretórios do MkDocs

A estrutura típica do MkDocs deve conter:

```vash
project/
├── docs/
│   ├── index.md
│   ├── api/
│   │   ├── swagger.yaml
├── mkdocs.yml
```

#### Passo 3: Adicionando o Swagger UI

Baixe os arquivos necessários do Swagger UI:

- Acesse o repositório oficial no GitHub: Swagger UI GitHub.
- Baixe e copie os arquivos da pasta dist para um diretório dentro do seu projeto, por exemplo, docs/swagger-ui.

Estrutura sugerida para integração:

```bash
project/
├── docs/
│   ├── index.md
│   ├── swagger-ui/
│   │   ├── swagger-initializer.js
│   │   ├── swagger-ui.css
│   │   ├── swagger-ui-bundle.js
│   │   └── swagger.yaml
```

#### Passo 4: Configurando o Swagger UI

Crie o arquivo swagger-initializer.js com o seguinte conteúdo:

```javascript
window.onload = function() {
  const ui = SwaggerUIBundle({
    url: './swagger.yaml',
    dom_id: '#swagger-ui',
    presets: [
      SwaggerUIBundle.presets.apis,
      SwaggerUIStandalonePreset
    ],
    layout: "BaseLayout"
  });
  window.ui = ui;
};
```

### Passo 5: Criando a Página de API no MkDocs

Edite o arquivo mkdocs.yml para incluir o Swagger:

```yaml
site_name: Meu Projeto com API
nav:

- Home: index.md
- API:
  - Documentação: api/index.md
```

Crie o arquivo docs/api/index.md com o conteúdo:

```html
# API Interativa

<div id="swagger-ui"></div>
<link rel="stylesheet" type="text/css" href="../swagger-ui/swagger-ui.css">
<script src="../swagger-ui/swagger-ui-bundle.js"></script>
<script src="../swagger-ui/swagger-initializer.js"></script>
```

### Passo 6: Testando o Projeto

Inicie o servidor do MkDocs:

```bash
mkdocs serve
```

Acesse a documentação no navegador em <http://127.0.0.1:8000/api/>.

## 5. Guia de Uso

- Adicionar ou Atualizar Especificações: Substitua o conteúdo do arquivo swagger.yaml para atualizar as especificações da API.
- Personalização: Modifique o layout ou o estilo do Swagger alterando os arquivos CSS ou a configuração no swagger-initializer.js.

### Publicação

Gere os arquivos estáticos do MkDocs:

```bash
mkdocs build
```

Publique os arquivos em qualquer servidor de hospedagem, como GitHub Pages ou Netlify.

## 6. Anexos

### 6.1 Swagger remoto

Adicione uma linha como a abaixo em um arquivo `.md` e veja a mágica acontecer:

```html
<swagger-ui src="https://petstore.swagger.io/v2/swagger.json"/>
```

### 6.2 Exemplo anterior aplicado

<swagger-ui src="https://petstore.swagger.io/v2/swagger.json"/>
