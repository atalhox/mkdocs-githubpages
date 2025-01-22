# Vídeos

## 1. Introdução

Incorporar vídeos do YouTube em documentos markdown é uma maneira eficaz de enriquecer o conteúdo, tornando-o mais interativo e dinâmico. Este guia detalha como obter o código de incorporação de um vídeo do YouTube e como incluí-lo em um arquivo `.md`.

## 2. Objetivo

O objetivo deste documento é explicar o processo para incorporar um vídeo do YouTube em um arquivo de formato `.md`, utilizando o código de incorporação gerado pela plataforma. Além disso, serão fornecidas orientações sobre o uso correto do recurso em diferentes contextos.

## 3. Público-alvo

Este guia é destinado a:

- Desenvolvedores e criadores de conteúdo que utilizam arquivos markdown em seus projetos.
- Estudantes e profissionais que desejam enriquecer apresentações, documentações ou sites baseados em markdown.
- Qualquer pessoa interessada em aprender a usar vídeos do YouTube como recurso adicional.

## 4. Guia

### 4.1. Selecionar e Obter o Código de Incorporação do Vídeo

1. Acesse o vídeo desejado no YouTube.
2. Clique no botão Compartilhar localizado abaixo do vídeo.
3. No menu exibido, selecione a opção Incorporar.
4. Copie o código HTML apresentado.

Exemplo de código extraído de um vídeo do YouTube:

```html
<iframe width="560" height="315" src="https://www.youtube.com/embed/Q-YA_dA8C20?si=1NTMunOJQ7ZLWPXc"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

### 4.2. Adaptar o Código ao Formato Markdown

Como o markdown puro não suporta diretamente elementos HTML como`<iframe>`, será necessário garantir que o ambiente em que o markdown será renderizado permita HTML embutido.

Exemplo:

```html
<iframe width="560" height="315" src="https://www.youtube.com/embed/Q-YA_dA8C20?si=1NTMunOJQ7ZLWPXc"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

### Passo 3: Salvar o Arquivo

- Salve o arquivo com a extensão `.md` (ex.: video_tutorial.md).
- Certifique-se de testar a renderização em um visualizador de markdown que suporte HTML embutido.

## 5. Onde utilizar

### Ambientes Compatíveis

A renderização do código de incorporação depende do visualizador markdown. Plataformas como GitHub Pages, Jekyll e outros sistemas baseados em markdown frequentemente suportam HTML embutido.

### Boas Práticas

- Use vídeos relevantes para o contexto do documento.
- Sempre credite a fonte do vídeo.
- Evite incorporar vídeos de baixa qualidade ou conteúdo irrelevante.

### Validação

Antes de distribuir o documento, teste em diferentes dispositivos e navegadores para garantir a funcionalidade.

## 6. Resultado

<iframe width="560" height="315" src="https://www.youtube.com/embed/Q-YA_dA8C20?si=1NTMunOJQ7ZLWPXc"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## 7. Anexos

**TO-DO: adicionar capturas de tela do processo de extração e incorporação, bem como exemplos de diferentes implementações em markdown.**
