
# Descrição do desafio módulo 3 – Processamento de Dados Simplificado com Power BI

Abaixo, os arquivos gerados nos processos de coleta, transformação e apresentação da base de dados ‘azure_company’, disponíveis nesse mesmo repositório:
- *MySQL: ‘script_testes com azure_company.sql’ (utilizado Workbench 8.0 conectado à base de dados na instância MySQL – Azure);
- **Power Query: ‘desafio_azure_company.pbix’.

## ROTEIRO:

    1. Criação de uma instância na Azure para MySQL: OK
    2. Criar o Banco de dados com base disponível no github: Ok
    3. Integração do Power BI com MySQL no Azure: Ok
    4. Verificar problemas na base a fim de realizar a transformação dos dados: *MySQL

### Diretrizes para transformação dos dados
    1. Verifique os cabeçalhos e tipos de dados: **Power Query
    2. Modifique os valores monetários para o tipo double preciso: **Power Query
    3. Verifique a existência dos nulos e analise a remoção: *MySQL
    4. Os employees com nulos em Super_ssn podem ser os gerentes. Verifique se há algum colaborador sem gerente: *MySQL
    5. Verifique se há algum departamento sem gerente: *MySQL
    6. Se houver departamento sem gerente, suponha que você possui os dados e preencha as lacunas
    7. Verifique o número de horas dos projetos: *MySQL
    8. Separar colunas complexas (employee > Address): **Power Query
    9. Mesclar consultas employee e departament para criar uma tabela employee com o nome dos departamentos associados aos colaboradores. A mescla terá como base a tabela employee. Fique atento, essa informação influencia no tipo de junção: **Power Query – Mesclar1
    10. Neste processo elimine as colunas desnecessárias: **Power Query – Mesclar1
    11. Realize a junção dos colaboradores e respectivos nomes dos gerentes. Isso pode ser feito com consulta SQL ou pela mescla de tabelas com Power BI. Caso utilize SQL, especifique no README a query utilizada no processo: **Power Query – Mesclar2
    12. Mescle as colunas de Nome e Sobrenome para ter apenas uma coluna definindo os nomes dos colaboradores: **Power Query – Mesclar2
    13. Mescle os nomes de departamentos e localização. Isso fará que cada combinação departamento-local seja único. Isso irá auxiliar na criação do modelo estrela em um módulo futuro: **Power Query – Mesclar3
    14. Explique por que, neste caso supracitado, podemos apenas utilizar o mesclar e não o atribuir: Para unir as colunas ‘Dlocation’ e ‘Dname’ das tabelas ‘dept-locations’ e ‘departament’ respectivamente, e gerar uma coluna com a união das duas colunas originais, o ideal é utilizar a função Combinar – Mesclar consultas do Power Query (como na consulta Mesclar3), pois a função Combinar – Acrescentar consultas reuniria todos os registros das duas tabelas como resultado, evidenciado na consulta Acescentar1.
    15. Agrupe os dados a fim de saber quantos colaboradores existem por gerente: *MySQL
    16. Elimine as colunas desnecessárias, que não serão usadas no relatório, de cada tabela: **Power Query
    17. Relatório PBI: ‘desafio_azure_company.pbix’