# Tratamento de SLA de Inbound com Pandas

Este projeto tem como objetivo realizar o tratamento de dados de SLA (Service Level Agreement) de inbound, combinando três bases de dados distintas e realizando transformações e cálculos importantes para análise de desempenho.

## Descrição

O código realiza o seguinte fluxo de trabalho:

1. **Leitura de Dados**: Três bases de dados são lidas diretamente de planilhas do Google Sheets.
2. **Tratamento de Dados**:
   - **Concatenação de Colunas de Data e Hora**: As colunas de data e hora são combinadas em uma única coluna para facilitar o manuseio.
   - **Conversão para Datetime**: As colunas de data e hora são convertidas para o formato `datetime` do Pandas para facilitar cálculos e manipulações.
   - **Preenchimento de Valores Faltantes**: Algumas colunas com valores ausentes (NaN) são preenchidas com valores padrão, como uma string vazia.
   - **Cálculo de Tempo de Fila**: O tempo de fila é calculado com base na diferença entre o início e o fim das operações.
   - **Cálculo de SLA**: A partir do cálculo de tempo de operação, o SLA é verificado, considerando regras específicas para diferentes dias e horários.
3. **Merge de Bases**: As três bases de dados são unificadas, com as informações combinadas em um único DataFrame.
4. **Ajustes Finais**:
   - Renomeação de colunas para padronização.
   - Cálculo de diferenças de tempo entre o início e o fim de processos.
   - Cálculo de tempo total em minutos e classificação de cada operação com base no SLA (dentro ou fora do SLA).
5. **Exportação dos Resultados**: O DataFrame final, com todas as informações tratadas, é exportado para uma nova planilha no Google Sheets, pronto para ser analisado ou utilizado para relatórios.

## Funcionalidade

Este código é útil para empresas que precisam controlar e analisar o tempo de atendimento de seus processos de inbound, verificando se estão dentro dos SLAs estabelecidos. Ele permite a integração de dados de diferentes fontes, tratando inconsistências e realizando os cálculos necessários para análise.

## Como Usar

1. Importe as bibliotecas necessárias.
2. Substitua os IDs das planilhas no código pelas suas planilhas de dados.
3. Execute o código para realizar o tratamento de dados e exportação para uma nova planilha.

## Dependências

- `pandas`
- `numpy`
- `gspread`
- `gspread-dataframe`
- `google-auth`

## Como Instalar

Se você estiver usando o Google Colab, as bibliotecas podem ser instaladas diretamente com o seguinte comando:

```bash
!pip install gspread gspread-dataframe google-auth
