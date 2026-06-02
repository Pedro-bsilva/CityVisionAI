# CityVisionAI

# 🏙️ CityVision AI — Consultoria Inteligente de Planejamento Urbano Sustentável

A **CityVision AI** é um sistema inteligente baseado em sistemas multiagentes (MAS) focado em criar soluções autônomas e integradas para o desenvolvimento de cidades. A partir de uma única solicitação em linguagem natural, uma equipe de especialistas de inteligência artificial debate e valida planos de revitalização para áreas urbanas degradadas.

---

## 🎯 Objetivo do Projeto

* 
**Geral**: Elaborar, de forma autônoma e colaborativa, um plano urbano sustentável detalhado para revitalizar uma área degradada da cidade.


* 
**Equilíbrio Técnico**: Propor uma solução que harmonize o meio ambiente, a infraestrutura, a mobilidade, a habitação e a inclusão social.


* 
**Viabilidade**: Considerar restrições orçamentárias rígidas e critérios reais de viabilidade técnica e financeira.


---

## 🛠️ Tecnologias Utilizadas

Com base na implementação real demonstrada no ambiente do projeto, foram utilizadas as seguintes ferramentas:

* **Framework Multiagentes**: [AutoGen Studio / AutoGen Team UI](https://github.com/microsoft/autogen) (Interface interativa para orquestração de agentes locais).
* **Modelo de Linguagem (LLM)**: `nvidia/nemotron-3-nano-4b` (Modelo otimizado executado localmente).
* **Servidor Local de Inferência**: LM Studio / OpenAI-compatible API Server (rodando no endereço local `http://127.0.0.1:11234`).
* **Versionamento e Documentação**: GitHub.

---

## 🏗️ Arquitetura do Fluxo e Interação

O ecossistema funciona sob um modelo de **Group Chat** coordenado, onde o processo ocorre de maneira dinâmica através de reuniões simuladas:

```
[cite_start][ Input do Usuário (Briefing em Linguagem Natural) ] [cite: 9]
                       │
                       ▼
             ┌───────────────────┐
             [cite_start]│   Orquestrador    │ ◄─── (Coordena, valida e dita a próxima voz) [cite: 11]
             └─────────┬─────────┘
                       │
     ┌─────────────────┼─────────────────┐
     ▼                 ▼                 ▼
[cite_start][Urbanista] [cite: 12]  [Eng. [cite_start]Infra] [cite: 13]  [cite_start][Ambientalista][cite: 15]... (Demais Especialistas)
     │                 │                 │
     └─────────────────┼─────────────────┘
                       │
                       ▼
             ┌───────────────────┐
             [cite_start]│   Apresentador    │ ───► [ Proposta Final Consolidada ] [cite: 18, 22]
             └───────────────────┘

```

### Dinâmica das Interações:

1. 
**Entrada do Briefing**: O usuário envia um pedido descrevendo os problemas da região degradada.


2. 
**Mediação**: O **Orquestrador** assume o controle, define as prioridades iniciais da discussão e passa a palavra ao agente técnico adequado.


3. 
**Discussão Técnica**: Cada agente intervém trazendo sua própria personalidade, valores, nível de formalidade e "voz técnica".


4. 
**Resolução de Impasses**: Os agentes reagem às propostas uns dos outros (ex: o Economista avaliando os custos das ideias do Ambientalista).


5. 
**Consolidação**: Ao término do debate, o Apresentador de Projeto compila os pontos fortes de cada área e gera uma narrativa pública integrada.



---

## 👥 Estrutura de Agentes (8)

O ecossistema é composto por 8 agentes especializados:

| Agente | Papel e Responsabilidade Principal |
| --- | --- |
| 👑 **1. Orquestrador** | Coordena a discussão entre os demais agentes, define prioridades de fala e valida o progresso do plano de revitalização.

 |
| 📐 **2. Urbanista** | Define o conceito estético e funcional geral da requalificação urbana, além do zoneamento e uso do solo.

 |
| 🚰 **3. Engenheiro de Infraestrutura** | Avalia e garante as soluções técnicas para saneamento básico, energia, telecomunicações e a viabilidade estrutural do projeto.

 |
| 🚌 **4. Especialista em Mobilidade** | Desenha as malhas de transporte público, conexões de ciclovias, modais alternativos e foca em acessibilidade universal.

 |
| 🌿 **5. Ambientalista** | Defende a aplicação de soluções baseadas na natureza (SbN), preservação ambiental e mitigação de impactos ecológicos.

 |
| 🤝 **6. Sociólogo Urbano** | Avalia os impactos sociais da intervenção, garantindo habitação inclusiva, mitigação da gentrificação e bem-estar comunitário.

 |
| 📊 **7. Economista Urbano** | Responsável pelas projeções financeiras, planilhas de custos, análise de retorno sobre o investimento e controle orçamentário.

 |
| 📢 **8. Apresentador de Projeto** | Consolida as minutas e discussões técnicas em um resumo executivo narrativo, claro e cativante para o público geral.

 |

---

## 📂 Estrutura do Repositório (Entregáveis)

De acordo com os requisitos exigidos no projeto, este repositório está organizado da seguinte forma:

* 
`/agentes`: Documentação detalhada sobre a criação e a personalidade de cada agente.


* 
`/prompts`: Arquivos com as instruções de sistema (*system prompts*) configuradas no AutoGen para delimitar o comportamento dos especialistas.


* 
`/inputs`: Exemplos de briefings e pedidos iniciais em linguagem natural utilizados para testar a IA.


* 
`/roteiro-interacoes`: Log completo ou histórico textual de como o Orquestrador guiou as conversas.


* 
`/evidencias`: Prints, gravações ou logs que comprovam a execução real e autônoma do ecossistema de agentes.


* 
`/relatorio-perguntas`: Documento de texto respondendo às seguintes questões reflexivas da equipe:


1. 
*Influência do papel/personalidade nas decisões finais.* 


2. 
*Análise de conflitos entre agentes e soluções do Orquestrador.* 


3. 
*Riscos de má configuração de prompts (analisado por agente).* 


4. 
*Melhorias implementadas na coordenação multiagente.* 





---

### 🚀 Como Rodar o Projeto Localmente

1. Certifique-se de ter o **AutoGen Studio** instalado em seu ambiente Python.
2. Inicie o seu servidor local de LLM com o modelo `nvidia/nemotron-3-nano-4b` na porta `11234`.
3. Importe o arquivo de especificação do time (`test2`) disponível neste repositório dentro da aba **Team Builder** do AutoGen.
4. Abra uma nova **Session**, envie o briefing desejado e assista ao debate dos especialistas!
