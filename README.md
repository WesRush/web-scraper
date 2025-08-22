# Web Scraper de Contatos para Projeto Acadêmico

Este repositório contém um script de Web Scraping desenvolvido em Python, projetado para rodar no ambiente do Google Colab.

## 🎯 Objetivo do Projeto

O script foi concebido com o objetivo principal de agilizar a busca e a coleta de contatos de casas de repouso na Região Metropolitana de Recife. Estes dados servem como base para a concepção de um projeto da disciplina de **Atividades Práticas Interdisciplinares de Extensão I**, do curso de Análise e Desenvolvimento de Sistemas (ADS) da UNINASSAU - Recife.

## 🤖 Contexto de Desenvolvimento

Este script foi inteiramente modelado com o auxílio da IA **Gemini**, da Google. A escolha pelo ambiente **Google Colab** foi estratégica, visando eliminar a necessidade de configuração de qualquer IDE (Ambiente de Desenvolvimento Integrado) local, permitindo que o projeto seja executado em qualquer máquina com acesso à internet e a um navegador, de forma simples e direta.

## ✨ Funcionalidades

* **Busca Automatizada:** Realiza buscas no Google por estabelecimentos locais com base em um termo de pesquisa e localização.
* **Paginação:** Navega automaticamente por até 10 páginas de resultados para coletar um volume maior de dados.
* **Filtragem Inteligente:** Processa os resultados e salva apenas os estabelecimentos que possuem informações de contato e endereço.
* **Exportação em CSV:** Salva todos os dados coletados em um arquivo de planilha (`.csv`), pronto para ser utilizado em outros softwares como Excel ou Google Sheets.

## 🚀 Como Usar

Para executar este scraper, siga os passos abaixo. Não é necessário instalar Python ou qualquer programa em seu computador.

### Passo 1: Criar sua Chave de API no SerpApi

O script utiliza o serviço do SerpApi para realizar as buscas no Google de forma segura e eficiente.

1.  Acesse o site **[SerpApi](https://serpapi.com/users/sign_up)**.
2.  Crie uma conta gratuita. O plano gratuito oferece um número generoso de buscas por mês, mais do que suficiente para este projeto.
3.  Após criar a conta, você será redirecionado para o seu *Dashboard*. Lá, você encontrará sua chave de API pessoal (sua **API Key**). Copie esta chave, pois você precisará dela no próximo passo.

### Passo 2: Configurar o Google Colab e os "Secrets"

1.  Acesse o **[Google Colab](https://colab.research.google.com/)**.
2.  Crie um `Novo notebook`.
3.  No menu à esquerda, clique no ícone de **chave (🔑)** para abrir o painel de "Secrets".
4.  Clique em `+ ADICIONAR NOVO SECRET`.
5.  Preencha os campos da seguinte forma:
    * **`name`**: `SERPAPI_KEY` (é muito importante que seja exatamente este nome).
    * **`value`**: Cole a sua chave de API que você copiou do site SerpApi.
6.  Ative a opção "Acesso do notebook" para que seu código possa ler o secret.

### Passo 3: Executar o Script

1.  Copie o código completo do script Python fornecido.
2.  Cole o código em uma célula no seu notebook do Google Colab.
3.  Execute a célula clicando no botão de "Play" (▶️) ou pressionando `Shift + Enter`.
4.  Aguarde o script finalizar. Ele irá imprimir o progresso da busca página por página.

### Passo 4: Baixar os Resultados

1.  Após a execução, um novo arquivo `.csv` aparecerá no painel de arquivos.
2.  Clique no ícone de **pasta (📁)** no menu à esquerda para abrir o painel.
3.  Localize o arquivo (`casas_de_repouso_simplificado.csv`).
4.  Clique nos três pontos (⋮) ao lado do nome do arquivo e selecione **Fazer o download**.

## 🔧 Generalização e Customização

Este scraper foi construído para buscar casas de repouso em Recife, mas sua verdadeira força está na sua flexibilidade. **Ele pode ser usado para buscar e guardar informações sobre qualquer coisa!**

Para adaptá-lo para outra finalidade, basta modificar duas linhas no dicionário `params` dentro do código:

```python
params = {
    # Mude aqui para o que você quer pesquisar (ex: "restaurantes veganos")
    "q": "casa de repouso",

    # Mude aqui para a cidade ou região da sua busca (ex: "São Paulo, Brazil")
    "location": "Recife, Pernambuco, Brazil",

    # ... outros parâmetros
}
