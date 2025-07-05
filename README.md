# Plataforma de Debate e Publicação de Artigos

Bem-vindo à Plataforma de Debate e Publicação! Este é um ambiente web interativo, criado em um único arquivo HTML, projetado para que estudantes possam aprimorar suas habilidades de escrita de artigos de opinião, participar de debates e compartilhar seus trabalhos em um mural colaborativo.

## 🚀 Visão Geral

A plataforma oferece três seções principais:
1.  **Painel Principal:** Uma visão geral com acesso rápido a todas as áreas.
2.  **Laboratório de Escrita:** Um guia com conceitos sobre a estrutura de um artigo de opinião (modelo ENEM), um link para uma ferramenta de escrita externa (`telegra.ph`) e um formulário para publicar o artigo finalizado.
3.  **Mural de Publicações:** Uma galeria onde todos os artigos publicados pela turma são exibidos em tempo real.

O projeto é totalmente responsivo, funcionando em desktops, tablets e celulares.

## ✨ Funcionalidades

- **Interface Intuitiva:** Navegação simples com um menu lateral (que se torna um menu "hamburger" em dispositivos móveis).
- **Conteúdo Educacional:** Seção dedicada a explicar a estrutura de um artigo de opinião.
- **Ferramenta de Escrita Externa:** Integração com o `telegra.ph` para uma experiência de escrita limpa e sem distrações.
- **Mural Colaborativo:** Os alunos podem publicar links para seus artigos, que aparecem instantaneamente para todos no mural.
- **Persistência de Dados:** As publicações são salvas de forma permanente usando o serviço gratuito [JSONBin.io](https://jsonbin.io/).
- **Design Responsivo:** A interface se adapta a qualquer tamanho de tela para uma experiência de uso consistente.
- **Zero Dependências (Backend):** O projeto é "serverless", funcionando inteiramente no navegador do cliente, sem necessidade de um servidor próprio.

## 🛠️ Tecnologias Utilizadas

- **HTML5:** Para a estrutura semântica do conteúdo.
- **Tailwind CSS:** Para a estilização rápida e responsiva, diretamente no HTML.
- **JavaScript (Vanilla):** Para toda a interatividade, manipulação do DOM, navegação entre páginas e comunicação com a API do JSONBin.io.

## 🗄️ Armazenamento de Dados com JSONBin.io

Para salvar e carregar os artigos publicados no mural, este projeto utiliza a API do [JSONBin.io](https://jsonbin.io/). Isso permite que os dados sejam persistentes sem a necessidade de um banco de dados complexo ou de um backend.

### Como funciona:
1.  Um "bin" privado é criado na sua conta do JSONBin.io para armazenar uma lista (array) de objetos JSON, onde cada objeto representa um artigo.
2.  Quando um aluno publica um novo artigo, o JavaScript:
    a.  Lê a lista atual de artigos do seu bin.
    b.  Adiciona o novo artigo à lista.
    c.  Envia a lista atualizada de volta para o bin, substituindo a versão antiga.
3.  Ao acessar o Mural, o JavaScript lê a lista do bin e a renderiza na tela.

## ⚙️ Como Configurar e Usar

Para rodar este projeto localmente ou em seu próprio serviço de hospedagem (como GitHub Pages), siga estes passos:

1.  **Clone ou baixe o arquivo `index.html`** deste repositório.

2.  **Crie uma conta no [JSONBin.io](https://jsonbin.io/)**. É gratuito.

3.  **Obtenha sua Chave de API (API Key):**
    - No painel do JSONBin, clique no seu avatar no canto superior direito e vá para a seção "API Keys".
    - Copie sua `X-Master-Key`.

4.  **Crie um "Bin" para armazenar os artigos:**
    - Volte ao painel principal e clique em "Create Bin".
    - **Importante:** Na caixa de texto, cole o seguinte conteúdo para inicializar o bin com um item de boas-vindas:
      ```json
      [
        {
          "title": "Bem-vindo ao Mural de Publicações!",
          "author": "Sistema",
          "url": "#",
          "createdAt": "2025-01-01T00:00:00.000Z"
        }
      ]
      ```
    - Marque a opção "Make Private".
    - Clique em "Create Bin".

5.  **Obtenha o ID do seu Bin:**
    - Após a criação, a URL no seu navegador será algo como `https://jsonbin.io/68699fe98a456b7966bbfe93`.
    - O ID do seu bin é essa sequência final de letras e números.

6.  **Atualize o código HTML:**
    - Abra o arquivo `index.html` em um editor de texto.
    - Vá até a seção `<script>` no final do arquivo.
    - Encontre e substitua os valores das constantes `JSONBIN_API_KEY` e `JSONBIN_BIN_ID` pelas suas credenciais que você acabou de obter:
      ```javascript
      // --- CONFIGURAÇÃO JSONBin ---
      const JSONBIN_API_KEY = 'SUA_X_MASTER_KEY_AQUI';
      const JSONBIN_BIN_ID = 'SEU_BIN_ID_AQUI';
      ```

7.  **Pronto!** Agora você pode abrir o arquivo `index.html` em qualquer navegador ou publicá-lo online.

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

  @media print {
    .ms-editor-squiggler {
        display:none !important;
    }
  }
  .ms-editor-squiggler {
    all: initial;
    display: block !important;
    height: 0px !important;
    width: 0px !important;
  }
