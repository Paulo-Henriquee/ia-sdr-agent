# 🧠 Agente SDR com IA + WhatsApp

Este projeto implementa um **Agente de SDR Inteligente** usando **LLMs, RAG e integração com WhatsApp**, com suporte a mensagens de texto, áudio, imagem e PDF.

🔧 Desenvolvido com foco em **pré-venda automatizada, qualificação de leads e geração de valor consultivo**, o agente interage com o cliente, entende suas dores e apresenta a melhor solução, encaminhando os interessados para um especialista humano.

---

## 🎯 Funcionalidades Principais

✅ Interação por WhatsApp (texto, áudio, imagem, PDF)  
✅ Transcrição automática de áudios com **Whisper/OpenAI**  
✅ Uso de **RAG + banco vetorial** para respostas personalizadas  
✅ Prompt dinâmico com estilo consultivo (estrutura de vendas real)  
✅ Memória via Redis para contexto de sessão  
✅ Resposta por texto e áudio (via ElevenLabs TTS)

---

## 🧩 Arquitetura Tecnológica

| Componente | Descrição |
|-----------|-----------|
| **n8n** | Orquestrador de todo o fluxo |
| **OpenAI GPT-4.1** | IA generativa para respostas |
| **Whisper** | Transcrição de áudios |
| **Redis** | Memória de sessão por usuário |
| **Postgres PGVector** | Banco vetorial para base de conhecimento (RAG) |
| **LangChain** | Wrapper para chamadas vetoriais e LLM |
| **ElevenLabs** | Geração de voz natural para envio de áudio |
| **WhatsApp Cloud API + EvolutionAPI** | Envio e recebimento de mensagens |

---

## 🧠 Fluxo de Execução

1. 📥 **Recebe mensagem (texto, áudio, imagem ou PDF)**
2. 🧹 Transforma áudio ou imagem em texto
3. 🧠 Gera resposta com IA + memória via RAG
4. 📤 Divide resposta longa e envia por texto ou áudio

---

## 📁 Estrutura do Projeto

```
📦 ia-sdr-agent
├── workflow.json             # Arquivo do fluxo no n8n
├── imagens/                  # Prints do fluxo e exemplos
├── README.md                 # Este arquivo
```

---

## 🚀 Como Usar

1. Importe o arquivo `workflow.json` no seu ambiente n8n
2. Configure as credenciais para:
   - OpenAI
   - Redis
   - EvolutionAPI (WhatsApp)
   - Postgres (PGVector)
   - ElevenLabs (opcional)
3. Configure seu webhook em `/sofia`
4. Teste o agente enviando mensagens por WhatsApp

---

## 📌 Requisitos

- n8n >= 1.8
- Conta OpenAI (GPT-4.1 + Whisper)
- Banco Redis ativo
- Postgres com extensão PGVector
- Conta na ElevenLabs (opcional)
- API Evolution ativada com envio de mídia

---

## 🧑‍💻 Autor

**Paulo Henrique Amaral**  
[LinkedIn](https://www.linkedin.com/in/paulo-amaral-5679a2253/) | [GitHub](https://github.com/Paulo-Henriquee)

---

## 🧠 Próximos Passos

- 🔄 Adicionar suporte para histórico de conversas persistente
- 📊 Integração com dashboards para métrica de desempenho
- 🌐 Multi-idioma
