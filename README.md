# DataBot-19: Automação de Extração de Dados COVID-19 e Criação de Gráfico

## Descrição

Este bot automatiza a extração de dados sobre COVID-19 usando a API da **OWID Catalog** e não de um CSV. Ele obtém dados atualizados, filtra-os para o Brasil, armazena as informações no Google Sheets e gera gráficos da evolução diária de casos e mortes. 

## Funcionalidades

1. **Automatização de Download e Processamento dos Dados**  
   - Conecta-se à API OWID para obter dados sobre COVID-19.
   - Filtra dados específicos para o Brasil, selecionando as colunas necessárias.
   - Usa os últimos 7 dias de dados para criar uma visualização focada.

2. **Armazenamento no Google Sheets**  
   - Envia os dados filtrados para uma planilha Google Sheets, simplificando o acesso e compartilhamento.
   - Usa a API do Google Sheets para organizar e salvar as informações em uma tabela.

3. **Criação de Gráficos com Matplotlib**  
   - Gera um gráfico com os dados coletados, visualizando a evolução diária de casos e mortes.
   - Salva o gráfico localmente em formato PNG.

## Pré-requisitos

1. **Python 3.10**  
   - Use o Conda para configurar um ambiente virtual com Python 3.10.

   ```bash
   conda create --name nome_projeto_robo python=3.10
   ```

2. **Instalação das Dependências**  
   - Instale as bibliotecas necessárias a partir do arquivo `requirements.txt`:

   ```bash
   pip install -r requirements.txt
   ```

3. **Configuração do Google Sheets**  
   - Configure as credenciais do Google Sheets seguindo as instruções no [guia oficial de configuração](https://developers.google.com/sheets/api/quickstart/python).
   - Atualize o código para incluir o **ID correto da sua planilha** no Google Sheets.

## Como Executar

1. Clone o repositório e entre na pasta do projeto.
2. Ative o ambiente virtual configurado com Conda.
3. Insira o arquivo de credenciais JSON para o Google Sheets.
4. Execute o bot:

   ```bash
   python databot19.py
   ```

## Estrutura do Código

- **Método `action`**: Controla o fluxo de execução e o tratamento de exceções.
- **Método `load_data`**: Carrega e filtra os dados da API da OWID para o Brasil.
- **Método `add_to_google_sheets`**: Envia os dados filtrados para o Google Sheets.
- **Método `generate_plot`**: Cria e salva o gráfico da evolução diária de casos e mortes no Brasil.

## Exemplos de Uso

- **Configurações Regionais**: Filtre por país para comparar o impacto da COVID-19 em diferentes regiões.
- **Análise de Período Específico**: Adapte o script para analisar períodos maiores ou menores, como o ano completo ou somente um mês específico.

## Observações

- Os dados são extraídos da **API da OWID**.
- O relatório final é salvo no **Google Sheets**.
