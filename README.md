# Trabalhando com Machine Learning na Prática no Azure ML
## Links Importantes
- [Explore Automated Machine Learning in Azure Machine Learning (Lá você encontra o passo a passo com mais detalhes)](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html)
- [Explore Azure AI Services](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/02-content-safety.html)
## Passo a passo
### 1. Criar workspace
1. Entre no portal do Azure https://portal.azure.com usando suas credenciais da Microsoft.

2. Selecione + Criar um recurso , pesquise Machine Learning e crie um novo recurso do Azure Machine Learning.

3. Selecione Revisar + criar e selecione Criar . Aguarde a criação do seu espaço de trabalho (pode demorar alguns minutos) e, em seguida, vá para o recurso implantado.

4. Selecione Launch Studio (ou abra uma nova guia do navegador e navegue até https://ml.azure.com e entre no Azure Machine Learning Studio usando sua conta da Microsoft). Feche todas as mensagens exibidas.

5. No estúdio Azure Machine Learning, você deverá ver seu espaço de trabalho recém-criado. Caso contrário, selecione Todos os espaços de trabalho no menu à esquerda e selecione o espaço de trabalho que você acabou de criar.

### 2. Use aprendizado de máquina automatizado para treinar um modelo

1. No Azure Machine Learning Studio , veja a página Automated ML (em Authoring ).

2. Crie um novo trabalho de ML automatizado com as configurações orientadas no site do primeiro link neste README.

3. Envie o trabalho de treinamento. Ele inicia automaticamente.

4. Espere o trabalho terminar. Pode demorar um pouco.

### 3. Avalie o melhor modelo

1. Na guia Visão geral do trabalho automatizado de aprendizado de máquina, observe o melhor resumo do modelo.

2. Selecione o texto em Nome do algoritmo do melhor modelo para visualizar seus detalhes.

3. Selecione a guia Métricas e selecione os gráficos residuais e predito_true se eles ainda não estiverem selecionados.

### 4. Implantar e testar o modelo

1. Na guia Modelo do melhor modelo treinado pelo seu trabalho automatizado de machine learning, selecione Implantar e use a opção de serviço Web para implantar o modelo com as seguintes configurações:

- Nome : prever-aluguéis
- Descrição : Prever aluguel de bicicletas
- Tipo de computação : Instância de Contêiner do Azure
- Habilitar autenticação : selecionado

2. Aguarde o início da implantação – isso pode levar alguns segundos. O status de implantação do endpoint de previsão de aluguel será indicado na parte principal da página como Running .

3. Aguarde até que o status da implantação mude para Succeeded . Isso pode levar de 5 a 10 minutos.

### 5. Testar o serviço implantado

1. No estúdio Azure Machine Learning, no menu esquerdo, selecione Endpoints e abra o ponto final em tempo real de previsão de alugueis.

2. Na página do endpoint em tempo real de previsão de aluguel, visualize a guia Teste.

3. No painel Dados de entrada para testar o endpoint, substitua o modelo JSON pelo código do arquivo input.json, disponível nesse repositório.

4. Clique no botão Testar .

5. Revise os resultados do teste, que incluem um número previsto de aluguéis com base nos recursos de entrada. O resultado deve ser igual ao código do arquivo output.json, disponível nesse repositório.