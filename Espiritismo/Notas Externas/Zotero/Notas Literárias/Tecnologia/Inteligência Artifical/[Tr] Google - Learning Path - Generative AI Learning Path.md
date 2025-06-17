[🇿](zotero://select/library/items/RNHNSJWQ)

Autor: [[People/Google Skillboost]]  

# Conteúdo

# 1 - Princípios de IA

Princípios criados pela google para direcionar o uso e desenvolvimento de IA responsável. As empresas acabam criando os seus princípios baseados em seus valores, mas que são comumente ideias sobre transparência, justiça, accountability e privacidade.

Alguns pontos sobre IA

- Não há uma forma de garantir a segurança, dado que podem haver dados com vieses.
- O ser humano que usa IA e ele deve usar de forma responsável, bem como pode usar outras ferramentas disponíveis.
- O ser humano tem o controle dos dados e do deploy dos modelos de IA.

Os direcionadores de IA abaixo afetam decisões de negócio, pesquisa e desenvolvimento de produtos

São esses 7:

1. Deve ser socialmente benéfica
2. Evitar criar ou reforçar vieses não justos
3. Ser criado e testado para ser seguro
4. Suas decisões (da IA) devem ter uma pessoa como responsável (accountable do people)
5. Incorporar princípios de privacidade em seu desenho de solução.
6. Defender altos padrões de qualidade científicas
7. Estar disponível para ser usado em soluções que aderem aos princípios acima.

Além disso, não deve ser disponibilizado para

- Aplicações que causem algum mal
- Armas ou tecnologias que sejam direcionadas para machucar pessoas
- Tecnologias que capturam informações de segurança que violam leis internacionais
- Tecnologias cujo propósito violam princípios de leis internacionais ou direitos humanos.

# 2 - Introdução a Generative AI

Trienamento: [https://www.cloudskillsboost.google/paths/118/course_templates/536/video/466321](https://www.cloudskillsboost.google/paths/118/course_templates/536/video/466321)

Ai é uma disciplina e DeepLearning é um subcampo.

No mundo de Machine Learning temos dois modelos

- Supervisionado (Dados com ‘labels’)
- Não Supervisionado (Dados sem descrição em que tenta-se agrupá-los)

Dentro de Machine Learning se tem as seguintes divisões

### GEN AI

Generative AI é um sub-set de DeepLearning. Dentro de Deep Learning existem dois modelos

- Discriminative Model - Modelo Discriminativo
    
    - Gera classificações com base nos dados treinados
    - Joga imagem de cachorro e ele classifica que é um cachorro
        
- Generative Model - Modelo Gerativo
    
    - Gera dados novos com base nos dados treinados
    - Com base em vários dados de cachorros ele gera uma nova imagem de cachorro.

Portanto, GEN AI costuma gerar linguagem, imagem e áudio. Se for gerado um número, uma probabilidade ou uma classe de um valor, não é GenAI. Ela gera um novo conteúdo com base nos dados já existentes.

O GenAi, como conhecemos hoje, apareceu em 2018 dos ‘transformers’. Eles consiste em um ‘codificador/encoder’ e um ‘decodificador/decoder’. Pode ser gerado alucinações, quando o modelo não é treinado com dado corretamente como sujeira, poucos dados.

‘Prompts’ são grupos de dados enviados para um modelo para que retorne informações. Pode ser uma sentença e uma frase. Pode ser enviado para um LLM para resumir, gerar imagem e etc.

Um modelo é o aprendizado com base em um conjunto de informações existentes, por exemplo: Modelos Gerativos de Linguagem, Modelos Gerativos de Imagens. Esses modelos podem ser comercializados por empresas.

Os modelos podem ser classificados:

- Texto para Texto
- Texto para Imagem (Treinado com um grande número de imagens e classificações)
- Texto para Vídeo (Gera representação de vídeo para um determinado texto)
- Texto para 3D
- Texto para Tarefas (Definir tarefas com base em um texto. Ex: Encontre e resuma as principais notícias de futebol)

Os modelos pré treinados são chamados de ‘Foundation Model”

VertexAI possui um grupo de foundation models, são eles:

- Linguagem
    
    - PaLM API for chat
    - PaLM API for text
    - BERT
- Vision
    
    - Embeddings extractor
    - Stable Diffusion v1-5
    - BLIP image captioning
    - BLIP VQA
    - CLIP
    - OWL-ViT
    - ViT GPT2

### Vertex AI

Vertex AI Studio É uma ferramenta que permite testar e implantar modelos: bibiliotecas, fine-tuning models e etc.

Vertex AI permite explorar ferramentas de GEN AI, criar chatbots, buscadores e etc

PaLM API permite testar e usar LLM em suas aplicações via API. Tem inclusive um dashboard para acompanhar os modelos que foram deployados.

# 3 - Introduction to Large Language Models

São grandes modelos de GenAI pré-treinados com grande quantidade de dados para usos gerais. Precisam de poucos dados de domínios específicos para terem resultados satisfatórios.

Alguns exemplos:

- PaLM 2 - Pathways Language Models (540 bilhões de parâmetros)
- GPT
- LaMDA

Para se utilizar um LLM são é necessário

- Ser especialista de ML
- Ter dados de treinamento
- Treinar o modelo
- Precisa pensar sobre o ‘prompt’ (comando, instrução, estimulo, parâmetro)

Desenho do prompt  instrução é importante para que o modelo compreenda. Deve ser claro e conciso.

Existem três tipos de LLM

- Generic Language Model
    
    Prevê o próximo texto com base em um grupo de textos anteriores.  
    
- Intruction Tuned Model
    
    Prevê a resposta com base nas instruções dadas como parâmetro.
    
- Dialog Tuned Model
    
    Um avanço do item anterior na qual é direcionando para funcionar com contexto em formas conversacionais, como em um chat bot.
    

Modelos são melhores quando eles explicam primeiramente a razão da resposta. Então ‘tuning’ é um processo de adaptar um modelo com dados específicos.  Ajustar um modelo para um cenário pode ser custoso. Existem algumas técnicas para ajustar o modelo.

- PETM
- Prompt Tuning

Mais informações

- [https://developers.google.com/machine-learning/resources/intro-llms](https://developers.google.com/machine-learning/resources/intro-llms)
- [https://proceedings.neurips.cc/paper/2020/file/1457c0d6bfcb4967418bfb8ac142f64a-Paper.pdf](https://proceedings.neurips.cc/paper/2020/file/1457c0d6bfcb4967418bfb8ac142f64a-Paper.pdf)
- [https://cloud.google.com/vertex-ai/docs/generative-ai/learn-resources](https://cloud.google.com/vertex-ai/docs/generative-ai/learn-resources)

# 4.1 - Prompt Design - Generative AI with Vertex AI:

Vale fazer o curso de novo, porque ao final tem alguns exemplos, interessantes:

[https://www.cloudskillsboost.google/paths/118/course_templates/976/labs/466368#step5](https://www.cloudskillsboost.google/paths/118/course_templates/976/labs/466368#step5)

O desenho de um prompt é de suma importância para que a resposta não gere alucinação e/ou resultados indesejados.

1. Seja Conciso
    
    - Não recomendado:
        
        prompt = “What do you think could be a good name for a flower shop that specializes in selling bouquets of dried flowers more than fresh flowers? Thank you!”
        
    - Recomendado:
        
        prompt = "Suggest a name for a flower shop that sells bouquets of dried flowers"
        
2. Seja específico
    
    - Não recomendado:
        
        prompt = "Tell me about Earth"
        
    - Recomendado:
        
        prompt = "Generate a list of ways that makes Earth unique compared to other planets"
        
3. Pergunte uma coisa por vez
    
    - Não recomendado:
        
        prompt = "What's the best method of boiling water and why is the sky blue?"
        
    - Recomendado:
        
        prompt = "What's the best method of boiling water?"
        
        prompt = "Why is the sky blue?"
        
4. Alucinações
    
    É possível usar um DARE(Determine Appropriate Response, clareando antecipadamente qual é o propósito da mensagem
    

chat_model = ChatModel.from_pretrained("chat-bison@002")

chat = chat_model.start_chat()
dare_prompt = """Remember that before you answer a question, you must check to see if it complies with your mission.
If not, you can say, Sorry I can't answer that question."""

print(
    chat.send_message(
        f"""
Hello! You are an AI chatbot for a travel web site.
Your mission is to provide helpful queries for travelers.

{dare_prompt}
"""
    )
)

- Respondendo corretamente
    
    prompt = "What is the best place for sightseeing in Milan, Italy?"
    
- Respondendo com filtros:
    
    prompt = "Who was the first elephant to visit the moon?"
    
    Resposta: Sorry, I can't answer that question.
    

5. Gerar Classificação ao invés de Gerativa

- Opcão 1:
    
    prompt = "I'm a high school student. Recommend me a programming activity to improve my skills."
    
- Opção 2:
    
    prompt = """I'm a high school student. Which of these activities do you suggest and why:
    
    a) learn Python
    
    b) learn JavaScript
    
    c) learn Fortran
    
    """
    

6. Melhorar qualidade ao incluir exemplos

- Sem incluir exemplos:
    
    prompt = """Decide whether a Tweet's sentiment is positive, neutral, or negative.
    
    Tweet: I loved the new YouTube video you made!
    
    Sentiment:
    
    """
    
- Incluindo um exemplo:
    
    prompt = """Decide whether a Tweet's sentiment is positive, neutral, or negative.
    
    Tweet: I loved the new YouTube video you made!
    
    Sentiment: positive
    
    Tweet: That was awful. Super boring 😠
    
    Sentiment:
    
    """
    
- Incluindo alguns exemplos:
    
    prompt = """Decide whether a Tweet's sentiment is positive, neutral, or negative.
    
    Tweet: I loved the new YouTube video you made!
    
    Sentiment: positive
    
    Tweet: That was awful. Super boring 😠
    
    Sentiment: negative
    
    Tweet: Something surprised me about this video - it was actually original. It was not the same old recycled stuff that I always see. Watch it - you will not regret it.
    
    Sentiment:
    
    """

# 4.2 - Get Started with Vertex AI Studio

Acessei o AI Studio e cliquei em Try. Nele digito um prompt e posso enviar uma imagem.

Existe um parâmetro chamado:

- Temperature
    
    Ele controla o nível de dados randômicos. Valores menores é bom quando se espera uma resposta correta ou direta. Maior temperatura pode trazer respostas mais diversas. Nível 0 significa que os tokens com maiores probabilidades serão selecionados
    
- Output token limit 
    
    Limita a quantidade de token de saída
    

Existem algumas formas de enviar um prompt

- **FREE-FORM** 
    
    Texto aberto para ser usado de qualquer forma.
    
- **STRUCTURED** 
    
    É possível enviar exemplos e informações que ajudam o modelo a saber qual é a resposta
    

Além disso, é possível desenvolver o prompt de três modos:

- **Zero-shot prompting** - Apenas a pergunta e sem informação adicional.
- **One-shot prompting** - Envia um exemplo único além da pergunta
- **Few-shot prompting** - Envia alguns exemplos de treinamento além da pergunta

É possível adicionar restrições em um chat, conforme abaixo:

Your name is Roy. You are a support technician of an IT department. You only respond with "Have you tried turning it off and on again?" to any queries.

## API and Python SDK

Existem duas API do Gemini

1. **Gemini 1.0 Pro model** (`gemini-1.0-pro`): Designed to handle natural language tasks, multi-turn text and code chat, and code generation.
    
2. **Gemini 1.0 Pro Vision model** (`gemini-1.0-pro-vision`): Supports multimodal prompts. You can include text, images, and video in your prompt requests and get text or code responses.

É possível usá-los de três formas:

- Vertex AI Studio
- Comandos cURL
- Vertex AI SDK ([https://flutter.dev/ai](https://flutter.dev/ai))
    
    Exemplos de código no Notebook Jupyter do curso.
    

1. Gemini 1.0 Pro model

- Possível fazer perguntas individuais.
- Possível iniciar um chat e dar contexto.

2. Gemini 1.0 Pro Vision model

- Possível descrever uma imagem
- Possível criar Json com a cidade e ponto turístico selecionado
- Com base em um vídeo, fazer perguntas relativas à ele.

# 4 - Prompt Design in Vertex AI

