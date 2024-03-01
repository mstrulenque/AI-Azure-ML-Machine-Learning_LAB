# AI - Azure - ML Machine Learning

---

**LAB Utilizando**: Microsoft **Azure AI | Machine Learming Studio**

**Descrição do LAB**: 

Treinamento de Machine Learning, simulando um Use Case de "Aluguel de Bike", através da: 
 - Criação de um JOB (Automated ML),
 - Utilizando Modelo/Algoritmo de Regressão,
 - Uma fonte de dados na WEB, disponibilizado pela Microsoft, com dados históricos de aluguel de bike.
     
**Ações que serão realizadas**:

 - Azure:
   - Provisionar o Resource `Azure Machine Learning`
   - Criar um Resource Group
   - Criar um Workspace
 - Machine Learning Studio
   - Criar um `Automated ML`    (Job para Treinamento de Model)
   - Configurar um `Data Asset` (Dados históricos de Aluguel de bikes que será usado no Treinamento)
   - Associar o Data Asset a uma fonte de Dados na Web
   - Configurar o `Data Source`  (Fonte de Dados)
   - Configurar os parametros do Model/Algorithm - Regression
   - Configurar parametros de execução do JOB
   - Configurar o `Compute`       (Tipo Serverless, Virtual Machine e instancias que será usada para executar JOB)
   - Execução do JOB
   - Visualização dos Resultados do Treinamento
   - Deploy de um Web Service com o Model/Algorithm identificado como melhor no treinamento
   - Realizar Testes via Web Service verificando o Resultado.

---

# 👷 - Preparando Ambiente para realizar o LAB: 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (Criando Recurso Machine Learning, Resource Group, Storages e Workspace)


## 1 - Acesse: <a href="https://portal.azure.com"> <img width="99" alt="https://portal.azure.com" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/4665d721-98e7-4c24-bc97-f7540d64a917"></a>


## 2 - Faça o Login com a sua Conta 🔐
  
## 3 - Crie e Configure um Resource (Recurso)

3.1 - Na "Home", Clique em "Create Resource"
<br><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="62" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/b1b852ed-04a8-4eee-ba31-8f2845a546e7">

3.2 - No campo de busca digite ```machine learning``` e no resultado obtido, escolha "Azure Machine Learning" 
<br><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="275" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/c483358e-ec0c-45cf-a654-517850383b81">

3.3 - Clique no botão "Create" para criar o Recurso "Azure Machine Learning" 
<br><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="428" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/bb06f619-6589-4623-811a-4d70cc17236c">

3.4 - Criar seu workspace preenchendo  os campos: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.1 - "Subscription" - Já vem selecionado sua Subscription; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.2.1 - "Resource Group" - Clique no link "Create New" abaixo do campo; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.2.2 - "Resource Group" - Digite um nome para seu Resource Group; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.2.3 - "Resource Group" - Clique no botão "OK"; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.2.4 - "Resource Group" - o nome que você criou aparecerá selecionado no campo de escolha "Resource Group", <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
caso contrário escolha na lista; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="442" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/ad961abf-f4b3-4b79-8fcf-59b9a41a23ec">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.3 - "Name"   - dê um nome para seu workspace; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.4 - "Region" - escolha uma Region da Cloud para criação do workspace; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.5 - "Storage Account" - preenchido automaticamente com base no nome que você deu para seu workspace; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.6 - "Key vault" - preenchido automaticamente com base no nome que você deu para seu workspace; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.7 - "Application Insights" - preenchido automaticamente com base no nome que você deu para seu workspace; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.8 - Clique no botão "Review + Create"; <br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="442" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/83c19400-31f6-4999-ae50-554537c6ae93">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.9 - Revise os Dados e estando tudo correto, Clique no botão "Create"; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
**OBS**: Verificar se a validação que ocorre no inicio desta pagina aconteceu com sucesso, mensagem: "Validation passed". <br>
<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="442" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/e1d6b16d-60e0-4b82-85f6-da1a6a464acb">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.10 - Após a confirmação o Deploy iniciará, e ao final será apresentada uma pagina similar a pagina abaixo: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="561" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/dee7390a-0d0f-4489-a5ef-04adfcd61790">
<br>

---
# 🔬 Realizando o LAB - AI - Azure - Machine Learning: 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (Após Preparação do Ambiente ter sido Finalizado com Sucesso. Vamos inicia o LAB)

<br>

## 1 - Acessar o Azure - Machine Learning Studio

1.1 - Na "Home" do Azure, escolha o "Workspace" que você criou na etapa de "Preparação de Ambiente"
<br><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="549" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/43b68a4b-0d50-4df1-aeb8-27367c1d63b3">

1.2 - Na página do Workspace escolhido, clicar no botão ```Launch Studio``` 
<br><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="549" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/85553f83-b86e-4a03-8853-4989f93d388a">


## 2 - No "Machine Learning Studio" - Criar um "Automated ML" <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
(Job de Machine Learning, para processar Modelos com base em arquivo de Dados) 
<br>

### 2.1 - Acessar o menu "Automated ML"
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="549" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/25cd4363-5329-40e5-b9ad-c10352bf5fee">

### 2.2 - Clicar em "+ New Automated ML Job" 
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="354" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/03958a62-7cce-42eb-b0b0-7c37d3e96b41">

### 2.3 - Configurar o Automated ML Job <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.1 - "Basic Settings" - Preencher os campos: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.1.1 - "Job Name" - ``` job-bike-rental ``` (colocar um nome sugestivo relacionado a atividade que esta executando) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.1.2 - "New experiment name" - ``` mslearn-bike-rental ``` (colocar nome sugestivo relacionado a experimentação) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.1.3 - "Description" - (colocar a descrição da experimentação que esta executando) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.1.4 - Clicar no botão ```Next``` <br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="543" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/111837cf-1acf-411e-9277-3affa9dbd479">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2 - "Task type & Data" - Preencher os campos: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.1 - "Task type" - ``` Regression ``` (escolher esta opção.) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.2 - "Select Data" - Clicar no botão "Create" <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.3 - "Create data asset" - "Data Type" - campo: "Name" = ```bike-rentals``` (Nome da Base de Dados) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.4 - "Create data asset" - "Data Type" - campo: "Type" = ```Tabular``` (pois nossos dados sao CSV (tabulados)) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.5 - "Create data asset" - "Data Type" - Clicar no botão ```Next``` <br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="557" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/aec67fb5-c3a6-4630-a3df-fd885ea12265">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.6 - "Create data asset" - "Data Source" - Escolher: ```From Web Files``` (Os dados que utilizaremos está publicado na WEB) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.7 - "Create data asset" - "Data Source" - Clicar no botão ```Next``` <br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="553" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/4d393d0d-2077-4ddd-950f-1b0de484cf5f">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.8 - "Create data asset" - "Web URL" - Campo: "Web URL": ```https://aka.ms/bike-rentals``` (dados Microsoft) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.9 - "Create data asset" - "Web URL" - Opção: "Skip data validation": ```Desligado``` (para não pular a validação de dados) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.10 - "Create data asset" - "Web URL" - Clicar no botão ```Next``` <br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="553" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/2a505481-7de9-405b-9a93-e4fd9581cffb">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.11 - "Create data asset" - "Settings" - Campo: "File Format": ```Delimited``` (dados no formato CSV, delimitados por "," ) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.12 - "Create data asset" - "Settings" - Opção: "Delimiter": ```Comma``` (Delimitador é vírgula (comma)) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.13 - "Create data asset" - "Settings" - Opção: "Encoding": ```UTF-8```  <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.14 - "Create data asset" - "Settings" - Opção: "Column headers": ```Only First file has headers``` (cabeçalho na 1a linha) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.15 - "Create data asset" - "Settings" - Opção: "Skip rows": ```None``` (não pular linhas) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.16 - "Create data asset" - "Settings" - Opção: "Dataset contains multi-line data": ```desmarcado``` (dados não tem várias linhas) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.17 - "Create data asset" - "Settings" - Clicar no botão ```Next``` <br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="553" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/e833d58a-8cad-41a2-82d9-dd84ae402eb8">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.18 - "Create data asset" - "Schema" - Column Name: "Path": ```Desabilitar``` (Não será usado) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.19 - "Create data asset" - "Schema" - Column Name: "Todas as outras": ```Habilitadas``` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.20 - "Create data asset" - "Schema" - Clicar no botão ```Next``` <br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="553" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/1a7b05a1-1661-4b24-8b82-97855a8dbfa6">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.21 - "Create data asset" - "Review" - Revisar os dados preenchidos nas páginas anteriores <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.2.22 - "Create data asset" - "Review" - Clicar no botão ```Create``` <br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="553" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/c71674e2-9629-4557-b796-756e6da49951">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.3 - "Task type & Data" - Escolher o data que acabamos de criar: ```bike-rentals``` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.4 - "Task type & Data" - Clicar no botão ```Next``` <br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="557" alt="image" src="https://github.com/mstrulenque/AI-Azure-ML-Machine-Learning_LAB/assets/63933792/189ee58c-0961-4224-a3bb-f57f294d23bb">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.5 - "Task Settings" - Preencher os campos: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.5.1 - "Task Settings" - campo: "Target Column" - ```rentals (integer)``` (escolher esta opção.) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.5.2 - "Task Settings" - clicar no link: ```View Aditional configuration settings``` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.5.3 - "Task Settings" - "View Aditional configuration settings" - Preencher Conforme print abaixo <br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="557" alt="image" src="https://github.com/mstrulenque/AI-Azure-ML-Machine-Learning_LAB/assets/63933792/7a92f96d-2856-454e-8736-02f67bf472d0">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.5.4 - "Task Settings" - "Limits" - Preencher Conforme print abaixo <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.5.5 - "Task Settings" - "Limits" - Clicar no botão ```Next``` <br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="557" alt="image" src="https://github.com/mstrulenque/AI-Azure-ML-Machine-Learning_LAB/assets/63933792/73652151-96a0-4573-91ca-afe952b6c6b5">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.5.6 - "Task Settings" - "Validate Tests" - Preencher Conforme print abaixo <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.5.7 - "Task Settings" - "Validate Tests" - Clicar no botão ```Next``` <br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="557" alt="image" src="https://github.com/mstrulenque/AI-Azure-ML-Machine-Learning_LAB/assets/63933792/0fa03451-81f3-4add-99e4-69cb705cf01f">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.5.8 - "Task Settings" - "Compute" - Preencher Conforme print abaixo <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.5.9 - "Task Settings" - "Compute" - Clicar no botão ```Next``` <br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="557" alt="image" src="https://github.com/mstrulenque/AI-Azure-ML-Machine-Learning_LAB/assets/63933792/d8916513-b80a-4600-8975-0eddc6799eef">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.5.10 - "Task Settings" - "Review" - Revisar os dados digitados/escolhidos<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.3.5.11 - "Task Settings" - "Review" - Clicar no botão ```Submit Trainning Job``` <br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="557" alt="image" src="https://github.com/mstrulenque/AI-Azure-ML-Machine-Learning_LAB/assets/63933792/fe8687d2-a5ef-4b67-85d4-074bd4136ea6">

### 2.4 - Execução do Automated ML Job <br>

Com o click do botão ```Submit Trainning Job``` (passo anterior), o Job que criamos para o Treinamento dos Modelos escolhidos e dos Dados que configuramos começa a ser executado. Abaixo os prints dos momentos:
<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.4.1 - JOB - Em Execução <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="557" alt="image" src="https://github.com/mstrulenque/AI-Azure-ML-Machine-Learning_LAB/assets/63933792/28045cdc-7ded-426b-96a0-2e0cada83358">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.4.2 - JOB - Execução Finalizada<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="557" alt="image" src="https://github.com/mstrulenque/AI-Azure-ML-Machine-Learning_LAB/assets/63933792/a18a6d91-33a1-4fee-90f0-aa53651b1807">

### 2.5 - Resultados da Execução do Automated ML Job <br>

Ao finalizar com sucesso o processamento do JOB ele apresenta os Resultados do Treinamento indicando qual Modelo apresentou melhor resultado
<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.5.1 - No Resumo da Finalização de Execução do Job: Na Seção "Best Model Summary" - Clicar no link ```Algorithm Name```<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="557" alt="image" src="https://github.com/mstrulenque/AI-Azure-ML-Machine-Learning_LAB/assets/63933792/24a67fc7-3d03-4b72-bad1-0ef32125b072">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.5.2 - Na página do Algoritmo escolhido, Clicar na Guia ```Metrics``` para verificar os números e gráficos: `predict-true` e `residuals`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="557" alt="image" src="https://github.com/mstrulenque/AI-Azure-ML-Machine-Learning_LAB/assets/63933792/53419f50-b826-4453-95fb-bbd0cf380bd5">


### 2.6 - Deploy do MODEL <br>

Iremos gerar um Deploy do Modelo (Best Model / Algorithm), para que possamos passar os parametros via JSON e recebermos o Retorno do Model.
<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.6.1 - Na página do Algoritmo escolhido, Clicar na Guia ```Model```<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.6.2 - Escolher a Opção ```Deploy``` >  ```Web Service``` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="557" alt="image" src="https://github.com/mstrulenque/AI-Azure-ML-Machine-Learning_LAB/assets/63933792/f71a8b6c-e9c2-4bad-baf4-867f421203d3">


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.6.3 - Em "Deploy a model", Preencher os campos: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.6.3.1 - "Deploy a model" - campo: "Name" = ```predict-rentals``` (Nome do Web Service que vai expor o Model" <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.6.3.2 - "Deploy a model" - campo: "Compute Type": escolher ```Azure Container Instance``` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.6.3.3 - "Deploy a model" - Clicar no botão ```Deploy``` <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="557" alt="image" src="https://github.com/mstrulenque/AI-Azure-ML-Machine-Learning_LAB/assets/63933792/52318f9f-5ceb-43a6-ba5b-d32d33a9361b">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.6.4 - Deploy "Em Execução", print abaixo: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="505" alt="image" src="https://github.com/mstrulenque/AI-Azure-ML-Machine-Learning_LAB/assets/63933792/9424851b-b4e2-4727-b24c-23cd87a26e3a">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.6.5 - Deploy "Finalizado com Sucesso", print abaixo: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="477" alt="image" src="https://github.com/mstrulenque/AI-Azure-ML-Machine-Learning_LAB/assets/63933792/c5511f90-4455-477f-8c82-e6c04f4a2369">

### 2.7 - Testando o MODEL <br>

Iremos realizar testes no Model, através do **Web Service** que foi gerado com base no Model e Deployado.
<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.7.1 - Na Menu Lateral Esquerdo: Selecionar ```Endpoints``` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.7.1 - Na página "Endpoints": Selecionar o endpoint que criamos/deployamos ```predict-rentals``` <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="650" alt="image" src="https://github.com/mstrulenque/AI-Azure-ML-Machine-Learning_LAB/assets/63933792/473fb943-2f5d-44b8-9236-cee0c3d19750">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.7.2 - Na página do Endpoint "predict-rentals": clicar na guia ```Test``` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.7.3 - Colar o JSON abaixo em ```Input Data to test endpoint``` <br>

```
 {
   "Inputs": { 
     "data": [
       {
         "day": 1,
         "mnth": 1,   
         "year": 2022,
         "season": 2,
         "holiday": 0,
         "weekday": 1,
         "workingday": 1,
         "weathersit": 2, 
         "temp": 0.3, 
         "atemp": 0.3,
         "hum": 0.3,
         "windspeed": 0.3 
       }
     ]    
   },   
   "GlobalParameters": 1.0
 }

```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.7.4 - Clicar no botão ```Test``` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
2.7.5 - Visualizar o Resultado devolvido pelo endpoint/Model em ```Test Result``` <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="643" alt="image" src="https://github.com/mstrulenque/AI-Azure-ML-Machine-Learning_LAB/assets/63933792/7672a010-862d-4c1e-98f0-26812fec6475">









