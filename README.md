# 🥗 ProdLab: Plataforma de Diagnóstico e Inteligência Operacional para Restaurantes

> **Plataforma de Diagnóstico de Maturidade Operacional e Benchmarking Setorial para o Setor de Alimentação Fora do Lar (AFL) no Distrito Federal.**  
> *Desenvolvido pelo Laboratório de Engenharia de Produção e Gestão da Qualidade (ProdLab) - Universidade de Brasília (UnB).*

---

## 📌 Sobre o Projeto

O **ProdLab Diag-Restaurantes** é uma solução que automatiza a avaliação de maturidade de estabelecimentos gastronômicos no DF, fundamentando-se no **Modelo de Referência IDEF0** (Macroatividades A1 a A8) e nas **10 Dimensões de Diagnóstico AS-IS**.

A plataforma opera sob um modelo de **Duplo Retorno**:
1. **Devolutiva B2B (Empresário):** Gera um diagnóstico individualizado com gráfico de radar de maturidade e um **Relatório Devolutivo TO-BE** com planos de ação sugeridos por Inteligência Artificial (RAG).
2. **Inteligência Setorial (ProdLab/GovTech):** Alimenta um banco de dados unificado e anonimizado para realização de **benchmarking setorial**, apoio a políticas públicas e pesquisas acadêmicas em Engenharia de Produção.

---

## 🤝 Metodologia Human-in-the-Loop

A Inteligência Artificial (Gemini via Google AI Studio) atua como um **copiloto de produtividade**, acelerando a geração da minuta inicial dos relatórios. Todos os relatórios passam por **curadoria, auditoria técnica e validação** efetuadas pelos pesquisadores e alunos do **ProdLab/UnB** antes de serem entregues ao restaurante.

---

## 🏗️ Arquitetura e Tecnologias

A aplicação adota uma arquitetura de microsserviços desacoplada e orientada à privacidade por padrão (*Privacy by Design*):

- **Front-end:** HTML5, Tailwind CSS, JavaScript Vanilla e [Chart.js](https://www.chartjs.org/) (Gráfico de Radar).
- **Motor de IA (RAG):** API do Gemini via Google AI Studio alimentada com o contexto do Modelo IDEF0.
- **Backend & Integrador:** Node.js (Serverless Function) para isolamento de credenciais e sanitização de dados.
- **Banco de Dados:** PostgreSQL (Supabase / Neon) com suporte a *Row Level Security* (RLS) e Views Anonimizadas.

---

## 📂 Estrutura do Repositório

```text
prodlab-diag-restaurantes/
├── docs/                       # Documentação técnica e científica do modelo IDEF0
├── src/
│   ├── assets/                 # Estilos, marcas e recursos visuais
│   ├── components/             # Componentes de interface (Formulário AS-IS, Radar Chart)
│   ├── config/                 # Parâmetros e variáveis globais
│   ├── services/               # Conexões com API do Gemini via Google AI Studio e Banco de Dados
│   └── mocks/                  # Dados fictícios para execução e desenvolvimento local
├── .env.example                # Modelo de variáveis de ambiente (sem segredos)
├── .gitignore                  # Arquivos e credenciais bloqueados no Git
├── README.md                   # Apresentação do projeto
└── package.json                # Dependências do projeto