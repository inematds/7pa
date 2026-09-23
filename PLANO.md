# 7PA — Os 7 Princípios na prática: plano de produto

Fonte: os 3 textos + infográfico "Gestão de Agentes de IA" (Intenção → Contexto → Dados → Critério de sucesso → Autonomia com limites → Observação → Supervisão/evolução).
Problema: a teoria é boa e abstrata. O leigo 40+ não vai "estudar gestão de agentes". Ele quer delegar uma tarefa pra IA e dormir tranquilo.

## 1. A ideia mágica em 1 frase

**"Ficha do Agente": a pessoa responde 7 perguntas em linguagem de dono de negócio (5 minutos) e sai com o agente pronto — instrução pra colar no ChatGPT/Claude, nível de autonomia recomendado, teste de aceitação e checklist de supervisão. Sem ler nenhum princípio.**

Por que essa forma e não outras:
- **Não é curso primeiro.** Curso ensina a teoria; a Ficha *aplica* a teoria escondida nas perguntas. O curso vira derivado (cada módulo = 1 pergunta).
- **Não é só prompt copiável.** Prompt solto depende de a pessoa saber conduzir a conversa. A Ficha tem formulário guiado, exemplos e presets clicáveis ("clínica", "loja", "escritório contábil", "professor") — o leigo preenche escolhendo, não redigindo.
- **A palavra "agente" fica no fundo.** Pra pessoa é "delegar uma tarefa pra IA". Funciona tanto pra quem vai criar automação quanto pra quem só vai usar o ChatGPT toda manhã — os 7 princípios valem igual.
- **O truque dos 7PA que ninguém faz:** o nível de autonomia (N0–N4) **é calculado**, não escolhido. Sai das respostas sobre risco e dados. É o momento "mágico": a pessoa descobre que o agente dela deve ser N2 e entende por quê.

## 2. Os 7 princípios em 7 perguntas de leigo

| # | Princípio | Pergunta (como aparece) | Exemplo no campo | O que o sistema gera |
|---|---|---|---|---|
| 1 | Intenção | **O que você quer tirar da sua mão? E por que isso importa?** | "Confirmar as consultas de amanhã pelo WhatsApp, porque 30% faltam sem avisar." | Missão do agente (1 frase) + "por que importa" (vira prioridade na instrução) |
| 2 | Contexto | **Se você contratasse alguém hoje pra isso, o que precisaria explicar no 1º dia?** | "Tratar por senhor/senhora, não mandar mensagem depois das 18h, sábado não tem atendimento." | Bloco "Regras da casa" + tom de voz. Só o mínimo (princípio: menor contexto que produz a melhor decisão) |
| 3 | Dados confiáveis | **De onde vem a informação certa? Quando duas fontes discordam, quem manda?** | "A agenda do sistema é a verdade. A planilha antiga não vale. Telefone errado → me avisa, não chuta." | "Fonte de verdade" + regra de conflito + regra "não inventa" |
| 4 | Critério de sucesso | **Como é um dia em que isso ficou perfeito? Como você saberia?** | "Todo paciente de amanhã recebeu mensagem até 17h; quem não respondeu está numa lista pra mim." | Definição de concluído + métrica simples + 3 testes de aceitação |
| 5 | Autonomia com limites | **O que ele NUNCA pode fazer sozinho? O que acontece de pior se errar?** (3 caixinhas: envolve dinheiro? é irreversível? mexe com pessoas de fora?) | "Nunca remarcar sem minha aprovação. Nunca falar de preço." | **Nível N0–N4 calculado** + lista de proibições + "o que precisa acontecer pra subir de nível" |
| 6 | Observação | **O que você quer ver no fim do dia ou da semana pra saber se está indo bem?** | "Quantos confirmaram, quantos não responderam, quais deram erro." | Relatório-padrão que o agente entrega + o que registrar (erros, custo, tempo) |
| 7 | Supervisão/evolução | **Quando ele deve te chamar? De quanto em quanto tempo você revisa?** | "Paciente reclamando → me chama na hora. Revisão toda sexta, 10 minutos." | Gatilhos de escalada + ritual de revisão (checklist semanal) + regra de evolução |

Regra do nível (no MVP, 4 linhas de lógica): dinheiro ou irreversível ou pessoa de fora → teto N2 (prepara, humano aprova). Só reversível e interno → N3. Só informação/rascunho → N1. Tem fonte de verdade definida (Q3 respondida) é pré-requisito pra passar de N1.

## 3. O pacote pronto (exemplo: Dra. Ana, dona de clínica)

**FICHA DO AGENTE — "Confirmador de Consultas"**
- **Missão:** confirmar por WhatsApp as consultas do dia seguinte, pra reduzir faltas.
- **Regras da casa:** tratar por senhor/senhora; mensagens só entre 9h e 17h; sem atendimento aos sábados.
- **Fonte de verdade:** agenda do sistema da clínica. Planilhas e anotações não valem. Dado faltando ou estranho → avisa a Ana, nunca chuta.
- **Sucesso:** até 17h, 100% dos pacientes de amanhã receberam mensagem; lista de "não respondeu" entregue à Ana.
- **Nível de autonomia: N2 — prepara, humano aprova.** Motivo: mexe com pessoa de fora (paciente) e remarcação é irreversível. Pra subir pra N3: 4 semanas sem erro na lista de envio.
- **Proibido:** remarcar, cancelar, falar de valores, responder reclamação.
- **Relatório diário (17h):** enviados / confirmados / não responderam / erros.
- **Me chama quando:** paciente reclama, pede remarcação, ou há 2 pacientes no mesmo horário.
- **Revisão:** sexta, 10 min — ler os erros da semana e ajustar 1 regra.

**+ Prompt do Agente** (colar no ChatGPT/Claude, ~20 linhas, gerado da ficha)
**+ 3 testes antes de ligar:** paciente sem telefone; dois no mesmo horário; paciente responde "quero remarcar".
**+ Checklist de supervisão** (imprimível: diário 2 min, semanal 10 min).

## 4. Formatos e canais

**Carro-chefe: UMA página web (GitHub Pages, `inematds/7pa`, dark âmbar INEMA).** 7 perguntas → ficha gerada na hora, no navegador, sem login, sem custo, sem IA obrigatória (template + presets). Botões: *Copiar Prompt do Agente*, *Copiar Ficha*, *Imprimir checklist*. Botão extra "Refinar com IA" copia um prompt-entrevistador pra quem prefere conversar com o ChatGPT.
Por quê: o público usa ChatGPT/Claude no navegador, não terminal; página funciona pra todo mundo, pra qualquer IA, é linkável do portal, vira card, é medível. Artifact claude.ai é ótimo pra protótipo mas o público é majoritariamente ChatGPT — não pode ser a porta.

Derivados (nesta ordem de valor):
1. **Prompt-entrevistador "7 Perguntas"** — texto único pra colar no ChatGPT/Claude/Custom GPT. Custa 1 hora, atinge quem só quer conversar.
2. **Reel 30s** (avatar HeyGen ou reel-edita-inema): "Você criou um agente. Quem manda nele? Responde 7 perguntas → link na bio."
3. **Vídeo explicativo 3–4 min** (video-explicativo) mostrando a Dra. Ana preenchendo.
4. **Curso v5 "Gestão de Agentes em 7 Perguntas"** (leigo 40+): 7 módulos = 7 perguntas, cada um termina preenchendo a página. Entra no portal e no catálogo PRO.
5. **Skill Claude Code `/ficha-agente`** — mesma lógica, pra quem já opera no terminal (INEMA.PRO, Nei, alunos avançados). Gera a ficha como `AGENTE.md` no projeto.
6. **Galeria de fichas prontas** (10 casos: clínica, loja, contabilidade, imobiliária, escola, advocacia, restaurante, igreja/ONG, consultório, marketing) — funciona como preset e como SEO/prova social.

## 5. Roadmap em 3 fases

**Fase 1 — MVP em 1 dia (hoje).** Repo `7pa` + `index.html` self-contained: 7 perguntas com exemplo em cada campo, 4 presets clicáveis, regra de nível N0–N4, geração da Ficha + Prompt + testes + checklist por template JS, botões copiar/imprimir, `prompts/entrevistador.md`. GitHub Pages ligado. Card no portal (atualiza-portal). Testar com 3 pessoas reais (Nei manda o link).

**Fase 2 — versão completa (1–2 semanas).** Galeria de 10 fichas prontas; "Refinar com IA" (prompt que pega a ficha crua e devolve melhorada); export PDF; reel + vídeo explicativo; curso v5 completo; skill `/ficha-agente`; versão EN/ES (usar relatórios do WiFi); guia `guia/index.html` (projetos-landing-guia).

**Fase 3 — escala/comunidade (1–2 meses).** "Auditoria do seu agente": a pessoa cola o prompt que já usa e recebe nota nos 7 princípios + o que falta (mesma página, modo reverso). Galeria comunitária (Artifact com db ou Supabase) onde alunos publicam fichas. Trilha PRO "Gestor de Agentes" com mentoria e certificado. Versão empresa: Ficha por setor + mapa de agentes (pessoas + processos + agentes).

## 6. Riscos e métrica

- **Pessoa não tem "agente" nenhum** → o produto tem que servir pra delegar ao ChatGPT comum. Linguagem: "delegar pra IA", não "gerenciar agentes". Já contemplado.
- **Ficha sai genérica** → presets e exemplos concretos em cada campo; teste com 3 pessoas antes de divulgar.
- **7 perguntas parecem muito** → uma por tela, barra de progresso, presets preenchem 70%. Meta: < 5 min.
- **Ninguém volta pra supervisionar** (o princípio 7 morre) → checklist imprimível + ritual de sexta explícito na ficha; na Fase 3, lembrete.
- **Prompt gerado não roda bem** → validar os 3 testes de aceitação em ChatGPT e Claude antes de publicar.

**Métrica de sucesso:** taxa de conclusão (chegou na Ficha ÷ abriu a página) ≥ 50%; clique em "Copiar Prompt" ≥ 30% dos que concluíram; 100 fichas geradas no 1º mês; 5 pessoas dizendo que a ficha está em uso real (o que importa de verdade).

## 7. Próximo passo imediato

Construir hoje o `index.html` da Ficha do Agente (Fase 1) com o preset "clínica" já preenchido como demonstração, publicar em `inematds/7pa` no GitHub Pages e mandar o link pra 3 pessoas. Antes: escrever `prompts/entrevistador.md` (1 hora) — serve de rascunho da lógica e já é um entregável.
