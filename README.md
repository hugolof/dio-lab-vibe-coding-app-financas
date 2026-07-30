# ChatFin - Assistente Financeiro Personalizado e Universal

Projeto desenvolvido como parte do desafio da DIO sobre Vibe Coding, focado no planejamento, especificação e prototipação de um aplicativo de organização de finanças pessoais utilizando Inteligência Artificial (Gemini e Lovable).

## Sobre o Projeto

O ChatFin é um conceito de aplicativo de controle financeiro pessoal que elimina a necessidade de planilhas complexas ou formulários manuais extenuantes. A proposta central é permitir que qualquer pessoa gerencie seu dinheiro conversando em linguagem natural, por texto ou por voz.

O projeto foi desenhado sob os princípios do Design Universal, garantindo acessibilidade e uma experiencia simples tanto para jovens nativos digitais quanto para idosos ou pessoas com necessidades especificas de acessibilidade.

## O que o App faz

- Registro por Conversa (Texto ou Voz): O usuário pode digitar ou falar "Gastei 15 reais no almoço" e o app processa a informação automaticamente.
- Categorização Automática: A IA identifica o valor, tipo (receita ou despesa) e a categoria adequada sem intervenção manual.
- Interface Universal e Acessível: Desenvolvida com alto contraste, alvos de toque grandes (mínimo 44x44px), fontes legíveis e suporte a leitores de tela (ARIA labels).
- Agente Financeiro Educativo: Respostas amigáveis com dicas proativas de economia e alertas de limites de gastos.
- Dashboard Simplificado: Visualização de saldos e gráficos com paleta de cores adaptada para daltônicos (colorblind-safe).

## PRD Final (Prompt Otimizado para o Lovable)

Abaixo está o PRD (Product Requirements Document) lapidado e formatado para servir de instrução (master prompt) para geradores de código baseados em IA, como o Lovable:

```markdown
# PRD Técnico e Otimizado para Lovable: ChatFin - O seu Assistente Financeiro Universal

## 1. Visão Geral do Produto
Objetivo: Criar um aplicativo web de finanças pessoais (Mobile-First) onde a principal interação ocorre via chat.
Diferencial (Design Universal): O aplicativo deve ser utilizável por qualquer pessoa, independentemente de idade, deficiência visual, motora ou familiaridade com tecnologia. A interface deve se adaptar as necessidades do usuário, exigindo o mínimo esforço cognitivo e físico.
Tom do App: Acolhedor, direto, sem jargões financeiros, com alto contraste e tipografia legível.

## 2. Stack Tecnológico Sugerido (Para o Lovable)
- Frontend: React (Vite) + TypeScript.
- Estilização e UI: Tailwind CSS, Shadcn UI / Radix UI (foco em suporte nativo a acessibilidade e navegação por teclado).
- Gráficos: Recharts (configurado com paletas de cores amigáveis para daltônicos - colorblind-safe).
- Acessibilidade: Integração com Web Speech API (para transformar voz em texto e vice-versa).
- Backend/IA: Supabase + OpenAI (processamento de linguagem natural).

## 3. Escopo do MVP focado em Design Universal

### Funcionalidades chave (Instruções para a IA)
1. Entrada Multimodal (Digitar ou Falar): O chat não depende apenas do teclado. Um botão de microfone bem visível permite registrar gastos falando: "Comprei remédios por 40 reais".
2. Feedback para Leitores de Tela: Respostas da IA claras e suporte a atributos ARIA.
3. Design a Prova de Erros: O usuário não precisa decorar formatos. A IA corrige erros de digitação e pede confirmação simples em caso de ambiguidade.
4. Dashboard de Alto Contraste: Gráficos que não dependem apenas de cor para diferenciar positivo/negativo (uso de ícones +/-, padrões visuais e textos claros).
5. Tipografia e Alvos de Toque: Textos responsivos e botões grandes (mínimo de 44x44px).

## 4. Mapa de Telas e Componentes (Instruções de UI)

### Tela 1: Onboarding e Autenticacao
- UI: Botões grandes, textos curtos e em linguagem simples.
- Acessibilidade: Formulários com labels explícitos (nunca usar apenas placeholders), contraste mínimo de 4.5:1 entre fundo e texto.

### Tela 2: Dashboard Principal (Home)
- Layout: Navegação simples em abas na parte inferior.
- Gráficos Universais: Ao invés de apenas um gráfico de pizza colorido, adicionar legendas em texto claro (Ex: "Transporte: 30%", "Alimentação: 50%").
- FAB (Botao Flutuante): Botam gigante no canto inferior direito, ícone de microfone e balão de chat, com a tag aria-label="Adicionar nova transação por chat".

### Tela 3: O Chat Financeiro (Core)
- UI: Foco total na area de conversa. Balões de texto com letras grandes.
- Input Area: Campo de digitação generoso. Ao lado, botam de microfone em destaque.
- Interação Universal:
  - User: "Gastei 15 na padaria." (digitado ou falado)
  - App: Exibe o texto em um balão.
  - App: Vibração suave e balão da IA: "Registrado: R$ 15,00 em Alimentação. Seu saldo agora e R$ 85,00."

## 5. Plano de Execucao no Lovable (Master Prompts)

Prompt 1 (Base e Layout Acessível):
"Crie um aplicativo web mobile-first chamado ChatFin usando React, Tailwind e Shadcn UI. A prioridade máxima e Acessibilidade (Design Universal). Crie a tela inicial com 3 cards (Saldo, Receitas, Despesas). Regras cruciais: 1. Use tags semânticas (main, nav, section). 2. Garanta contraste alto nas cores (text-gray-900 no fundo branco). 3. Todos os botões devem ter no mínimo 44x44px de área de clique. 4. Evite usar apenas verde/vermelho para status, use ícones da biblioteca Lucide React (seta pra cima/baixo) junto com os números."

Prompt 2 (O Chat Multimodal):
"Adicione a tela de Chat. A interface deve ter uma area de mensagens e um input embaixo. No input, além do botam de enviar (ícone de aviam de papel), coloque um botam de Microfone em destaque. Adicione aria-labels em todos os botões (ex: aria-label='Enviar mensagem'). Crie balões de chat com fontes grandes e legíveis (text-lg). Simule uma interação onde o usuário digita 'gastei 20 reais' e a IA responde confirmando."

Prompt 3 (Gráficos Colorblind-safe):
"Na tela inicial, adicione um gráfico usando Rechaçar para mostrar gastos por categoria. Configure as cores do gráfico para serem amigáveis para daltônicos (colorblind-safe palette, usando tons de azul, laranja, amarelo e roxo). Adicione legendas em texto claro ao lado ou abaixo do gráfico, para que a informação não dependa exclusivamente de quem enxerga a cor."

## 6. Esboço de Validação Inicial

1. Teste de Usabilidade Extremo: Testar o prototipo com um jovem nativo digital e com um adulto de 65+ anos com pouca familiaridade com apps. Sucesso = ambos conseguem registrar uma despesa sem ajuda.
2. Auditoria de Acessibilidade: Rodar ferramentas automáticas (Lighthouse/Axe) para garantir pontuação 90+ em Acessibilidade.
3. Métrica de Redução de Fricção: Acompanhar a porcentagem de uso do botam de voz vs teclado.
```
## Prototipação e Interações

Resultado final: https://always-listen-finance.lovable.app/auth

<img width="77.9" height="160.0" alt="Captura de tela 2026-07-30 173347" src="https://github.com/user-attachments/assets/b7d4b7be-f5cb-4472-a435-4e562afa367b" />
<img width="76.4" height="169.4" alt="Captura de tela 2026-07-30 173453" src="https://github.com/user-attachments/assets/11b8edb9-dd43-4503-8384-1eb0777c2a46" />
<img width="76.7" height="168.1" alt="Captura de tela 2026-07-30 173602" src="https://github.com/user-attachments/assets/54748638-3470-47e0-a8d9-004a180a07a9" />
<img width="77.0" height="168.7" alt="Captura de tela 2026-07-30 173540" src="https://github.com/user-attachments/assets/9e0c3655-1369-44d0-9f97-1f7632bc2e3f" />
<img width="75.5" height="168.2" alt="Captura de tela 2026-07-30 173550" src="https://github.com/user-attachments/assets/90f10100-b54c-4752-af60-bd1f9704fd7b" />

### Interações
```text
Por alguma razão as transações registradas pelo chat só registram até 999 reais;

Adicione a opção de inserção de metas;

Metas podem ser inseridas manualmente;

Ative IA real para entender;

Sugira modificações relevantes para o aplicativo;

Sugira ferramentas que possam ser útil;

O login deve ser feito por usuário, não email.
```

## Reflexao sobre o Processo (Vibe Coding)

### O que funcionou bem?

- Especificação Técnica Direta: Informar ao Lovable exatamente quais bibliotecas utilizar (Shadcn UI, Tailwind, Recharts) garantiu que o código gerado fosse limpo, moderno e modular desde a primeira iteração.
- Foco em Design Universal: Incluir regras claras de acessibilidade (como tamanho mínimo de botões e suporte a leitores de tela) evitou que a IA criasse layouts bonitos, porem inacessíveis.
- Construção Modular: Quebrar os prompts em etapas (Layout -> Chat -> Gráficos) ajudou a economizar os limites de uso da IA e manter o controle sobre o resultado.

### O que não funcionou como o esperado?

- Prompts muito abrangentes iniciais geravam interfaces genéricas. A IA precisava de limites bem definidos sobre o que não fazer (exemplo: não usar apenas cores verde/vermelha para representar dinheiro).
- A simulação da API de voz exigiu ajustes nos prompts para que a IA entendesse que a entrada de texto e voz deveriam compartilhar o mesmo estado da aplicação.

### O que aprendi sobre conversar com IAs?

Vibe Coding não é sobre fazer pedidos vagos, mas sobre atuar como um diretor de produto e arquiteto de software. Quanto mais clara e intencional for a definição do contexto, restrições e stack desejada, mais próximo do produto real será o resultado entregue pela IA. A chave está em saber lapidar a ideia inicial em instruções acionáveis.
