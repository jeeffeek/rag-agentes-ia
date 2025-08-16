# 🚀 Projeto RAG + Agentes de IA

Este projeto utiliza **Retrieval-Augmented Generation (RAG)** e **Agentes de Inteligência Artificial** para criar aplicações que buscam, processam e respondem com base em dados externos (como PDFs, bancos vetoriais e APIs).  

Abaixo estão as bibliotecas e frameworks utilizados, com explicações sobre seu papel no projeto.

---

## 📦 Bibliotecas Instaladas

### 1. `pypdf`
- **O que é:** Biblioteca Python para leitura, manipulação e extração de texto de arquivos PDF.
- **Uso no projeto:** Carregar e processar documentos PDF para alimentar a base de conhecimento.
- **Exemplo:** Extrair conteúdo de artigos ou manuais para indexação no mecanismo de busca do RAG.

---

### 2. `langchain`
- **O que é:** Framework que simplifica a criação de aplicações baseadas em LLMs (*Large Language Models*).
- **Uso no projeto:**
  - Criar *chains* (fluxos de execução)
  - Orquestrar *agents* (agentes autônomos)
  - Integrar LLMs com fontes de dados externas e bancos vetoriais.
- **Função:** É a espinha dorsal da aplicação, conectando modelo, dados e lógica.

---

### 3. `langchain-community`
- **O que é:** Coleção de integrações e conectores criados pela comunidade LangChain.
- **Uso no projeto:** Adicionar suporte a mais fontes de dados, bancos vetoriais e APIs.
- **Exemplo:** Conexão com Pinecone, Chroma, Weaviate, Google Drive, entre outros.

---

### 4. `langchain-groq`
- **O que é:** Integração entre LangChain e a plataforma **Groq**, especializada em LLMs de alta performance.
- **Uso no projeto:** Utilizar modelos hospedados na Groq para respostas rápidas e econômicas.
- **Vantagem:** Maior velocidade de inferência e menor custo em alguns cenários.

---

### 5. `langchain-huggingface`
- **O que é:** Integração oficial entre LangChain e o **HuggingFace Hub**.
- **Uso no projeto:**
  - Carregar modelos *open source* de LLMs e embeddings do HuggingFace.
  - Realizar inferência local ou via API.
- **Exemplo:** Usar um modelo de embeddings para indexar e buscar informações nos documentos do RAG.

---

### 6. `langgraph`
- **O que é:** Extensão para o LangChain que permite criar **fluxos de agentes e RAG como grafos** (*state machines*).
- **Uso no projeto:** Estruturar pipelines complexos de IA, onde cada nó representa uma ação, consulta ou decisão.
- **Benefício:** Facilita a visualização e depuração do fluxo.

---

## 🔄 Visão Geral do Fluxo

```mermaid
flowchart TD
    A[PDFs e Dados Externos] -->|Extração de texto| B[pypdf]
    B -->|Indexação| C[Embeddings - HuggingFace]
    C --> D[Banco Vetorial]
    D -->|Busca de contexto| E[LangChain]
    E -->|Raciocínio e Decisão| F[Agente LangGraph]
    F -->|Resposta Final| G[Usuário]
