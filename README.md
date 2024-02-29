# AI - Azure - Machine Learning (ML)

---

**LAB Utilizando**: Microsoft **Azure AI | Machine Learming Studio**

---

## 👷 Preparando Ambiente para realizar o LAB: 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (Criando Recurso Machine Learning, Resource Group, Storages e Workspace)


1 - Acesse: <a href="https://portal.azure.com"> <img width="99" alt="Clique Aqui" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/4665d721-98e7-4c24-bc97-f7540d64a917"></a>

2 - Faça o Login com a sua Conta 🔐

3 - Crie um Resource (Recurso)

3.1 - Clique em "Create Resource"
<br><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="62" alt="image" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/b1b852ed-04a8-4eee-ba31-8f2845a546e7">

3.2 - No campo de busca digite "machine learning" e no resultado obtido, escolha "Azure Machine Learning" 
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
