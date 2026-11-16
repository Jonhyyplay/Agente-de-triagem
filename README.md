# Agente de Triagem Inteligente para Service Desk

> Um sistema agêntico autônomo para orquestração de suporte e triagem de políticas internas, powered by Google Gemini 2.5 Flash & LangGraph.

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![AI](https://img.shields.io/badge/AI-Gemini%20Flash-orange)
![Orchestration](https://img.shields.io/badge/Orchestration-LangGraph-red)

## 📋 Sobre o Projeto

Este projeto implementa um **Agente de IA de Nível 1** para Service Desk capaz de ler documentos corporativos (PDFs), interpretar intenções e tomar decisões autônomas. Diferente de chatbots tradicionais, ele utiliza um grafo de estados (State Machine) para decidir dinamicamente se deve responder uma dúvida com base na documentação ou escalar para um humano.

### 🧠 Arquitetura de Decisão

O sistema opera através de um fluxo orquestrado pelo **LangGraph**:

1.  **Triagem Inteligente:** Analisa a entrada e classifica em `AUTO_RESOLVER`, `PEDIR_INFO` ou `ABRIR_CHAMADO` usando saídas estruturadas (JSON/Pydantic).
2.  **RAG (Retrieval-Augmented Generation):** Se a decisão for resolver automaticamente, o agente vetoriza e consulta políticas internas (PDFs) usando **FAISS**.
3.  **Validação de Contexto:** Verifica se a informação recuperada é suficiente. Se o RAG falhar ou o usuário pedir exceção, o fluxo é redirecionado para abertura de chamado.

---

## 🛠️ Tech Stack

* **LLM:** Google Gemini 2.5 Flash (via `langchain-google-genai`)
* **Orquestração:** LangGraph (StateGraph)
* **Vector Store:** FAISS (Facebook AI Similarity Search)
* **Parsing de Documentos:** PyMuPDF & LangChain Text Splitters
* **Estruturação de Dados:** Pydantic
* **Framework:** LangChain

---
## 🛠️ Como Rodar o Projeto

Basta clonar o repositório para seu computador.

```bash
git clone [https://github.com/jonhyyplay/agente-de-triagem.git](https://github.com/jonhyyplay/agente-de-triagem.git)
cd agente-de-triagem
```
> ☝️ Você também pode utilizar o GitHub Desktop para clonar o repositório. Caso utilize o VS Code, poderá usar extensões que facilite esse processo. (Caso não conheça, é o "GitHub Repositories").
