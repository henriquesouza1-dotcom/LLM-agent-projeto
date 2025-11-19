🤖 LLM Agent com HuggingFace – Projeto Acadêmico

Este repositório apresenta a implementação de um LLM Agent simples, utilizando a biblioteca HuggingFace Transformers em Python.

O agente é capaz de interpretar um comando e escolher automaticamente a melhor ação entre:

🧮 Realizar cálculos matemáticos

🔎 Buscar informações em um arquivo (baseLLM.txt)

💬 Responder perguntas utilizando um modelo de linguagem (FLAN-T5)

Este trabalho atende aos requisitos da atividade prática sobre LLM Agents, demonstrando a arquitetura básica de um agente inteligente.

👥 Integrantes do Grupo

- Bruno Dias
- Caio Limonge
- Enzo Gonzalez
- Éder Junior
- Henrique De Oliveira
- Gustavo Mori


🎯 Objetivo do Projeto

Criar um agente inteligente capaz de:

Interpretar comandos em linguagem natural.

Identificar automaticamente qual operação executar.

Usar ferramentas diferentes (tools) para cada tipo de tarefa.

Utilizar um modelo da HuggingFace (FLAN-T5) para respostas complexas.

Esse comportamento representa o funcionamento básico de um LLM Agent real, que combina um modelo de linguagem (LLM) com ferramentas externas.

🧠 Como o Agente Funciona

A lógica principal reside na função agente(prompt), que atua como o "cérebro" do agente, responsável por analisar o texto de entrada do usuário e decidir qual ação realizar (a.k.a. Tool Selection).

✔ 1. Pedidos de cálculo

Quando o usuário insere uma expressão matemática:

"Calcule 25 * 4"

O agente identifica um cálculo matemático e utiliza a ferramenta_calculo(expr).
Essa ferramenta executa diretamente operações usando a função eval() do Python.

✔ 2. Pedidos de busca em arquivo

Quando o usuário solicita uma pesquisa dentro da base de conhecimento local:

"Procure por inteligência artificial"

O agente utiliza:

ferramenta_busca(termo)


Essa função abre o arquivo base.txt, procura o termo solicitado e retorna um trecho relevante do texto como resposta.

✔ 3. Perguntas gerais (respostas naturais com LLM)

Se o comando não for identificado como cálculo nem busca, o agente assume que é uma pergunta geral e usa o LLM:

Modelo Utilizado: google/flan-t5-base

llm(prompt)


O modelo gera uma resposta natural, explicando ou descrevendo o tema solicitado.

🛠 Tecnologias Utilizadas

Python 3

Google Colab (Ambiente de Execução)

HuggingFace Transformers (Para o modelo LLM e a pipeline)

SentencePiece (Dependência do FLAN-T5)

Accelerate (Dependência da HuggingFace)

📦 Instalação das Dependências

Para rodar o projeto no Google Colab, execute o seguinte comando:

!pip install transformers sentencepiece accelerate


📜 Código Completo do Agente

O código-fonte principal está organizado no notebook Jupyter:

**agente_llm.ipynb**

Este arquivo inclui:

Definição das ferramenta_calculo e ferramenta_busca.

Carregamento e inicialização do modelo FLAN-T5.

A função principal do agente com a lógica de decisão (tool selection).

Testes automatizados para validação do agente.

▶️ Exemplos de Teste

Para testar o agente após a execução do Projeto_LLM_Agente.ipynb , utilize os seguintes comandos:

# Teste de Cálculo
agente("Calcule 25 * 4")

# Teste de Busca em Arquivo
agente("Procure por inteligência artificial")

# Teste de Resposta com LLM
agente("Explique o que é um LLM Agent")


📂 Estrutura do Repositório

/
├── 📄 README.md
├── 📄 baseLLM.txt               # Arquivo de texto usado como base de conhecimento
├── 📄 Projeto LLM.pptx          # Apresentação do projeto
└── 📄 Projeto_LLM_Agente.ipynb  # Código-fonte principal do LLM Agent


🖥️ Slides do Projeto

O arquivo de apresentação detalhada do projeto está incluído para referência:

Projeto LLM.pptx 

📑 Conclusão

O projeto demonstra o funcionamento básico de um LLM Agent, combinando um modelo da HuggingFace com ferramentas (tools) externas. Mesmo sendo uma implementação simples, o agente cumpre as etapas essenciais do ciclo de vida de um agente:

- Entende o comando.
- Seleciona a ferramenta adequada.
- Executa a ação correta.
- Retorna a resposta automaticamente.
- O trabalho está completo, organizado e funcional para fins acadêmicos.
