# Desafio de Projeto: Processamento e Transformação de Dados com Power BI

## Descrição Geral do Desafio

### Objetivo
O desafio tem como objetivo integrar, transformar e analisar dados utilizando uma instância MySQL hospedada no Azure e o Power BI. Os dados fornecidos deverão ser processados para garantir a integridade, a consistência e a usabilidade para fins de relatório e análise.

### Etapas do Desafio

1. **Criação da Instância MySQL no Azure**
   - **Ação:** Criar uma instância de banco de dados MySQL no Azure.
   - **Referência:** Utilizar o repositório disponível no GitHub para obter o banco de dados necessário.

2. **Integração do Power BI com MySQL no Azure**
   - **Ação:** Conectar o Power BI ao banco de dados MySQL no Azure.
   - **Objetivo:** Facilitar a extração e o carregamento de dados para transformação e análise.

### Diretrizes para a Transformação dos Dados

1. **Verificação e Ajuste de Cabeçalhos e Tipos de Dados**
   - **Ação:** Examinar os cabeçalhos e os tipos de dados das tabelas importadas.
   - **Detalhe:** Modificar os valores monetários para o tipo `double` preciso, garantindo precisão em cálculos financeiros.

2. **Tratamento de Dados Nulos**
   - **Verificação de Nulos:** Identificar a presença de valores nulos nas tabelas.
     - **Ação:** Analisar a necessidade de remoção ou imputação desses valores.
   - **Gerenciamento de `Super_ssn` Nulos:** Verificar se funcionários com `Super_ssn` nulo são gerentes.
     - **Ação:** Garantir que todos os colaboradores tenham um gerente designado.
   - **Departamentos Sem Gerentes:** Identificar departamentos sem gerentes.
     - **Ação:** Assumir dados ausentes e preencher as lacunas conforme necessário.

3. **Verificação de Horas de Projetos**
   - **Ação:** Verificar e validar o número de horas alocadas para projetos.
   - **Objetivo:** Garantir que os dados refletem a realidade operacional.

4. **Manipulação de Colunas Complexas**
   - **Separação de Colunas:** Dividir colunas complexas em componentes mais simples quando necessário.
   - **Mesclagem de Consultas:**
     - **Ação:** Mesclar as tabelas `employee` e `department` para associar colaboradores aos seus respectivos departamentos.
     - **Detalhe:** A mescla deve ser baseada na tabela `employee` e deve eliminar colunas desnecessárias.
   - **Junção de Colaboradores e Gerentes:**
     - **Método:** Utilizar SQL ou a mescla de tabelas no Power BI.
     - **Ação:** Se usar SQL, documentar a query no README.
   - **Consolidação de Nomes:**
     - **Ação:** Mesclar as colunas de Nome e Sobrenome em uma única coluna representando o nome completo dos colaboradores.
   - **Unificação de Departamento e Localização:**
     - **Ação:** Mesclar nomes de departamentos e suas localizações para criar combinações únicas.
     - **Objetivo:** Facilitar a criação de um modelo estrela para análise futura.
     - **Justificativa:** A mesclagem (merge) garante a unicidade de combinações, enquanto a atribuição (assign) não.

5. **Agrupamento de Dados para Análise de Gerenciamento**
   - **Ação:** Agrupar dados para determinar o número de colaboradores por gerente.
   - **Objetivo:** Fornecer insights sobre a estrutura gerencial.
   - **Limpeza de Dados:** Eliminar colunas que não serão utilizadas no relatório final.

### Resultados Esperados

- **Base de Dados Transformada:** Uma base de dados limpa, integrada e pronta para análise no Power BI.
- **Relatórios e Insights:** Relatórios que forneçam insights acionáveis sobre a estrutura organizacional e a alocação de recursos.
