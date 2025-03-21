# Azure-AI-Search
Este readme descreve o passo a passo para configurar uma pesquisa, assim como seus insights, possibilidades de ferramentas que se beneficiam com esse tipo de ferramenta e aprendizados adquiridos durante o processo.

# 1. Pré-requisitos
Antes de iniciar, certifique-se de ter:

- Uma conta no Azure Portal (portal.azure.com)
- Um Azure Cognitive Search Service configurado
- Um Azure Storage Account para armazenar os dados
- O Azure SDK instalado localmente ou acesso à API REST do Azure
- Dados estruturados para indexação (JSON, CSV, etc.)

# 2. Passo a Passo da Configuração

 Criando o Azure AI Search Service
 
1️⃣ No Azure Portal, vá até Criar um recurso.
Pesquise por Azure Cognitive Search e clique em Criar.
Escolha um nome, plano de serviço e região adequada.
Após a criação, acesse o recurso e copie a Chave de Administração e a URL do Serviço.

2️⃣ Configurando o Azure Storage
No Azure Portal, vá até Armazenamento > Criar Conta de Armazenamento.
Escolha um nome e uma região.
No recurso criado, vá até Containers e crie um container para armazenar seus documentos.
Faça o upload dos arquivos que deseja indexar no Azure Search.

3️⃣ Criando um Índice no Azure AI Search
No Azure Search, vá até Índices > Novo Índice.
Defina os campos necessários (exemplo: id, nome, descrição, sentimento, categoria).
Configure os Campos Pesquisáveis e Filtros conforme necessário.
Salve e publique o índice.

4️⃣ Criando um Indexador para o Azure Storage
No Azure Search, vá até Indexadores e clique em Novo Indexador.
Escolha Azure Blob Storage como origem de dados.
Selecione o container do Azure Storage onde seus arquivos estão.
Associe o indexador ao índice criado anteriormente.
Configure o agendamento de indexação (exemplo: a cada 24 horas).
Execute o indexador e verifique os logs para confirmar a indexação.

# Insights e Possibilidades
 
Filtragem Inteligente: Com campos como categoria e sentimento, é possível refinar pesquisas por relevância.
Integração com Chatbots: Chatbots podem consumir o Azure AI Search para responder perguntas baseadas em documentos indexados.
Análises Avançadas: Combinando o Azure AI Search com Azure AI Text Analytics, é possível extrair insights como análise de sentimentos.
Automação com Azure Functions: Agende reindexações automáticas ao detectar novos documentos no Storage.

# Aprendizados Adquiridos

Otimizar a Estrutura do Índice melhora a performance da pesquisa.
Monitoramento do Indexador é essencial para garantir que os dados estejam sempre atualizados.
Uso de Analisadores (como standard-lucene) pode aprimorar a precisão da busca.
Limitações de Plano: Algumas funcionalidades avançadas podem exigir um plano Standard ou Premium do Azure AI Search.

# Exemplos de Utilização
