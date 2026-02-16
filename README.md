# Framework de Engenharia de Prompts para Pair Programming Assistido por IA

![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Prompt Engineering](https://img.shields.io/badge/Prompt_Engineering-8A2BE2?style=for-the-badge)

## 🎯 Objetivo do Projeto

Este repositório documenta uma arquitetura padronizada de **Engenharia de Prompts (Prompt Engineering)** desenvolvida para otimizar a interação com Modelos de Linguagem de Grande Escala (LLMs) no ciclo de desenvolvimento de software. 

O propósito deste framework é mitigar alucinações, evitar saídas de código genéricas e forçar a Inteligência Artificial a atuar dentro de diretrizes rígidas de engenharia, garantindo a aplicação de Clean Code, princípios SOLID e metodologias de teste estruturadas.

---

## ⚙️ Modos Operacionais (System Prompts)

A arquitetura divide a assistência técnica da IA em cinco estados mutuamente exclusivos. Essa separação garante que o escopo de atuação do modelo seja perfeitamente adequado à fase atual do desenvolvimento, evitando intervenções não solicitadas.

### 1. ❓ [Modo ASK: Diagnóstico Técnico](prompts/prompt-ask.md)
Focado na análise de causa raiz e depuração de código (Debugging). Neste modo, o modelo atua estritamente em **modo de leitura**, fornecendo hipóteses baseadas em fundamentos da linguagem (ex: Event Loop, Call Stack) sem modificar a base de código do usuário.

### 2. ✂️ [Modo EDIT: Refatoração Isolada](prompts/prompt-edit.md)
Projetado para mutações precisas em artefatos de código existentes. O modelo é restrito a aplicar atualizações (ex: otimização de performance, correções de sintaxe) preservando a arquitetura circundante e garantindo **zero side-effects**.

### 3. 🧭 [Modo PLAN: Arquitetura de Sistemas](prompts/prompt-plan.md)
Atua na fase de levantamento de requisitos e design de software. O output é limitado à geração de diagramas lógicos, contratos de API (Interfaces/DTOs) e mitigação de riscos, **bloqueando a geração prematura de código funcional**.

### 4. 🤖 [Modo AGENT: Implementação Autônoma](prompts/prompt-agent.md)
Destinado à geração de módulos completos e estruturação de novos projetos. O modelo gerencia dependências, propõe árvores de diretórios e constrói o fluxo completo da aplicação (Rotas, Controladores, Serviços) exigindo **código de grau de produção**.

### 5. 📚 [Modo STUDY: Instrução Técnica Avançada](prompts/prompt-study.md)
Orientado ao aprofundamento acadêmico e conceitual. Utiliza o **método socrático** para ensinar design patterns, complexidade algorítmica e arquitetura de software, focando na análise rigorosa de trade-offs em vez de entregar soluções prontas.

---

## 🚀 Metodologia de Implementação

Para estabelecer o contexto técnico adequado e acionar os bloqueios de comportamento da IA, siga este fluxo:

1. Identifique a necessidade atual do ciclo de desenvolvimento (Planejamento, Implementação, Depuração, etc.).
2. Acesse o diretório `/prompts` e abra o arquivo `.md` correspondente ao modo desejado.
3. Copie o conteúdo integral do arquivo.
4. Injete o texto como a instrução de sistema (System Prompt) primária ou como a **primeira mensagem** na sua sessão com o LLM (ChatGPT, Claude, Gemini, Copilot, etc.).

---

## 💻 Stack Tecnológica Base

Embora os princípios arquiteturais deste framework sejam agnósticos e aplicáveis a diversas linguagens, as diretrizes foram primariamente otimizadas para o ecossistema **JavaScript/TypeScript**, com forte ênfase no desenvolvimento de aplicações e APIs utilizando **Node.js**.
