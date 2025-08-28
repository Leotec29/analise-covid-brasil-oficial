ANÁLISE DE DADOS COVID-19 POR CIDADE - BRASIL
📌 Descrição do Projeto
Este projeto tem como objetivo realizar uma análise detalhada dos dados de COVID-19 em cidades brasileiras. Utilizamos Python, Pandas, SQL, além de bibliotecas de visualização como Matplotlib e Seaborn.
O programa executa as seguintes etapas:
- Importação e tratamento do arquivo CSV `caso_full.csv.gz`.
- Inserção dos registros em uma tabela MySQL (`covid_city`), de forma otimizada em blocos.
- Produção de relatórios com:
  • Total de óbitos por cidade.
  • População estimada antes e após os casos.
  • Identificação da cidade com mais casos.
  • Identificação da cidade com menos casos.
- Criação de gráficos com:
  • Top 10 cidades em número de mortes.
  • Comparativo populacional antes e depois dos casos (Top 10).
  • Cidade com maior e menor quantidade de infecções registradas.
📂 Arquivos no Repositório
- `covid.py`: Código principal responsável por leitura, limpeza, carga no MySQL, relatórios e gráficos.
- `caso_full.csv.gz`: Base de dados compactada com informações de COVID-19 por município.
- `README.md`: Documento explicativo do projeto.
- `relatorio.pdf`: Relatório final contendo capturas de gráficos e tabelas.
⚙️ Pré-requisitos
Antes de executar o projeto, é necessário ter instalados:
- Python 3.13
- MySQL Server
- Bibliotecas Python:
    pip install pandas sqlalchemy mysql-connector-python matplotlib seaborn
▶️ Como Executar
1. Verifique se o MySQL está ativo.
2. Crie o banco de dados:
   CREATE DATABASE covid_db;

3. Crie a tabela:
   CREATE TABLE covid_city (
       city VARCHAR(255),
       city_ibge_code INT,
       date DATE,
       estimated_population_2019 INT,
       last_available_confirmed INT,
       last_available_deaths INT
   );

4. Configure as credenciais no script `covid.py`:
   usuario = 'root'
   senha = 'root'
   host = 'localhost'
   banco = 'covid_db'

5. Execute o programa:
   python covid.py
O sistema irá limpar a tabela existente, inserir os dados do CSV no banco e gerar automaticamente relatórios e gráficos.
📊 Resultados Esperados
- Gráfico com o Top 10 cidades em número de mortes.
- Gráfico comparativo de população antes e depois da pandemia (Top 10).
- Gráfico destacando a cidade com mais e menos casos.
- Relatórios exibidos no console.
📝 Observações
Para a produção do PDF final, recomenda-se salvar capturas das tabelas e gráficos gerados pelo programa.
