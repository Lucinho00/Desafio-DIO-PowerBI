# Desafio-DIO-PowerBI

Criação de um Dashboard Corporativo com Integração com MySQL e Azure
Abaixo está um guia passo a passo para criar um dashboard corporativo usando Power BI com integração ao MySQL no Azure. O processo envolve a configuração de uma instância MySQL no Azure, a criação do banco de dados, a integração do Power BI com o MySQL no Azure, e a transformação dos dados conforme as diretrizes fornecidas.

Passo 1: Criação de uma Instância MySQL no Azure
Acesse o Portal do Azure: Vá para portal.azure.com.
Criar um novo recurso:
Clique em "Create a resource".
Pesquise por "Azure Database for MySQL".
Selecione "Azure Database for MySQL" e clique em "Create".
Configuração da Instância:
Escolha a "Subscription" e o "Resource Group".
Insira um "Server name" (nome do servidor).
Escolha a "Data source" como "None".
Selecione a versão do MySQL desejada.
Configure "Location", "Compute + storage" e "Administrator account".
Clique em "Review + create" e depois em "Create".
Passo 2: Criar o Banco de Dados com Base Disponível no GitHub
Clone o Repositório do GitHub:
Clone o repositório que contém a base de dados usando git clone <URL-do-repositório>.
Conectar-se ao Servidor MySQL no Azure:
Use um cliente MySQL (como MySQL Workbench ou linha de comando) para conectar-se ao servidor MySQL no Azure.
Execute o comando: mysql -h <server-name>.mysql.database.azure.com -u <username>@<server-name> -p.
Criar o Banco de Dados:
No cliente MySQL, crie o banco de dados com o comando: CREATE DATABASE <nome-do-banco-de-dados>;.
Importar os Dados:
Importe os dados do repositório GitHub para o banco de dados: mysql -u <username>@<server-name> -p <nome-do-banco-de-dados> < caminho/para/o/arquivo.sql>.
Passo 3: Integração do Power BI com MySQL no Azure
Abrir o Power BI:
Abra o Power BI Desktop.
Conectar ao MySQL no Azure:
Clique em "Home" -> "Get Data" -> "More...".
Selecione "MySQL database" e clique em "Connect".
Insira o nome do servidor MySQL no Azure (<server-name>.mysql.database.azure.com), o nome do banco de dados e as credenciais.
Clique em "OK" e, depois, em "Connect".
Passo 4: Verificar Problemas na Base e Realizar a Transformação dos Dados
Verificação de Cabeçalhos e Tipos de Dados:

No Power BI, vá para a janela "Transform Data".
Verifique se os cabeçalhos das colunas e os tipos de dados estão corretos. Se necessário, ajuste os tipos de dados.
Modificação de Valores Monetários para Tipo Double:

Selecione as colunas monetárias e altere o tipo de dados para "Decimal Number".
Verificação de Nulos e Análise de Remoção:

Filtre as colunas para encontrar valores nulos.
Decida se é necessário remover os registros ou preencher os valores nulos.
Employees com Nulos em Super_ssn:

Filtre os registros com nulos em Super_ssn para identificar possíveis gerentes.
Verifique se há algum colaborador sem gerente e ajuste conforme necessário.
Verificação de Departamentos sem Gerente:

Analise a tabela de departamentos para garantir que todos tenham um gerente.
Se encontrar algum departamento sem gerente, preencha as lacunas com dados fictícios ou fornecidos.
Verificação do Número de Horas dos Projetos:

Analise a coluna de horas trabalhadas nos projetos para identificar e corrigir possíveis inconsistências.
Separação de Colunas Complexas:

Separe colunas que contenham dados compostos em colunas individuais.
Mesclar Consultas de Employee e Department:

Use a funcionalidade de mesclagem do Power BI para combinar as tabelas de employees e departments.
Escolha a junção apropriada (provavelmente uma junção interna) e elimine as colunas desnecessárias.
Junção de Colaboradores e Nomes dos Gerentes:

Utilize uma consulta SQL ou a funcionalidade de mesclagem do Power BI para unir colaboradores e seus respectivos gerentes.
Se usar SQL, documente a consulta utilizada no README.
Mesclar Colunas de Nome e Sobrenome:

Crie uma nova coluna combinando o nome e sobrenome dos colaboradores.
Mesclar Nomes de Departamentos e Localização:
Combine os nomes dos departamentos e suas localizações em uma única coluna.
Explicação sobre Mesclar e Não Atribuir:
O mesclar é utilizado aqui porque estamos criando combinações únicas que facilitam a análise e não estamos simplesmente reatribuindo valores existentes.
Agrupamento de Dados por Gerente:
Agrupe os dados para obter o número de colaboradores por gerente.
Eliminação de Colunas Desnecessárias:
Revise todas as tabelas e remova colunas que não serão usadas no relatório final.
Conclusão
Seguindo esses passos, você poderá criar um dashboard corporativo no Power BI com dados integrados do MySQL no Azure, transformando e limpando os dados conforme necessário para obter insights valiosos.
