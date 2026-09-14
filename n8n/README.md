# Portfólio de Análise de Dados e Automação

Este repositório apresenta projetos práticos desenvolvidos com foco em análise de dados, automação de processos e aplicação de Inteligência Artificial.

---

# 🚀 Projeto 1 — Automação de Triagem de Currículos

Automação desenvolvida com **n8n** para receber currículos por e-mail, processar os arquivos, extrair informações utilizando Inteligência Artificial e registrar os resultados em uma planilha.

## 🎯 Objetivo

Automatizar etapas iniciais do processo de recrutamento e seleção, reduzindo atividades manuais relacionadas ao recebimento, organização e análise inicial de currículos.

---

## 🔄 Funcionamento

O fluxo realiza as seguintes etapas:

1. Monitoramento de uma conta Gmail.
2. Identificação de e-mails não lidos contendo anexos.
3. Resposta automática ao candidato.
4. Marcação do e-mail como lido.
5. Download do currículo recebido.
6. Armazenamento do arquivo no Google Drive.
7. Leitura do currículo utilizando Google Gemini.
8. Extração estruturada das informações.
9. Análise do currículo utilizando critérios definidos para a vaga.
10. Classificação do candidato.
11. Registro dos resultados no Google Sheets.

---

## 🧩 Tecnologias utilizadas

- n8n
- Gmail API
- Google Drive
- Google Gemini
- Google Sheets
- Git
- GitHub
- JavaScript / Expressões n8n

---

## 📊 Dados extraídos

A automação estrutura informações como:

- Nome
- Profissão
- Resumo profissional
- Experiência
- Competências
- E-mail
- Avaliação do candidato

---

## 🤖 Classificação

O processo utiliza três classificações:

### ✅ Apto

Candidato apresenta aderência aos requisitos da vaga.

### ❌ Não Apto

Candidato não apresenta aderência suficiente aos requisitos definidos.

### ⚠️ Pendente de Avaliação Humana

O currículo necessita de análise complementar antes de uma decisão.

---

# 🏗️ Arquitetura do fluxo

```text
                  ┌──────────────────────┐
                  │      Gmail Trigger   │
                  └──────────┬───────────┘
                             │
                             ▼
                  ┌──────────────────────┐
                  │ Resposta automática  │
                  └──────────┬───────────┘
                             │
                             ▼
                  ┌──────────────────────┐
                  │ Marcar como lido     │
                  └──────────┬───────────┘
                             │
                             ▼
                  ┌──────────────────────┐
                  │ Baixar currículo     │
                  └──────────┬───────────┘
                             │
                   ┌─────────┴─────────┐
                   ▼                   ▼
          ┌────────────────┐   ┌────────────────┐
          │ Google Drive   │   │ Google Gemini  │
          └────────────────┘   └───────┬────────┘
                                       │
                                       ▼
                             ┌──────────────────┐
                             │ Information      │
                             │ Extractor        │
                             └────────┬─────────┘
                                      │
                                      ▼
                             ┌──────────────────┐
                             │ AI Agent         │
                             └────────┬─────────┘
                                      │
                                      ▼
                             ┌──────────────────┐
                             │ Google Sheets    │
                             └──────────────────┘