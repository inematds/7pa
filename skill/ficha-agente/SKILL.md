---
name: ficha-agente
description: Monta a FICHA DO AGENTE de uma tarefa delegada a IA pelos 7 princípios da gestão de agentes (intenção, contexto, dados, critério de sucesso, autonomia com limites, observação, supervisão) — entrevista de 7 perguntas, nível de autonomia N0–N4 calculado, instrução pronta, 3 testes e checklist, gravados em AGENTE.md. Também AUDITA um prompt/CLAUDE.md/AGENTS.md existente contra os 7 princípios. Gatilhos: "/ficha-agente", "ficha do agente", "montar um agente pra X", "delegar essa tarefa pra IA", "que nível de autonomia", "audita meu agente/prompt".
---

# ficha-agente

Versão terminal da **Ficha do Agente** (https://inematds.github.io/7pa/). A pessoa diz o que quer delegar; você conduz as 7 perguntas, calcula o nível de autonomia e entrega o pacote pronto num arquivo. A teoria fica escondida nas perguntas: **não dê aula**, entreviste.

Referências (leia só se precisar):
- Presets de 10 áreas: `~/projetos/7pa/data/presets.pt.js` (clínica, loja, contábil, professor, imobiliária, advocacia, restaurante, ONG, salão, agência).
- Os 7 princípios explicados: `~/projetos/7pa/guia/index.html` · material original: `~/projetos/7pa/conteudo/`.

## Modo 1 — Criar (default)

### 1. Ponto de partida
Se a pessoa já descreveu a tarefa, extraia o que der das 7 respostas antes de perguntar. Se a área bater com um preset, ofereça começar dele ("tem uma ficha pronta de imobiliária, quer partir dela?") e pergunte só o que muda.

### 2. Entrevista — uma pergunta por vez, em texto livre
Nunca use menu/AskUserQuestion. Linguagem de dono de negócio, sem jargão. Se a resposta vier vaga, **no máximo 1** pergunta de acompanhamento com exemplo concreto. Não pule nenhuma:

| # | Princípio | Pergunta | Campos que saem |
|---|---|---|---|
| 1 | Intenção | O que você quer tirar da sua mão? Por que isso importa? | nome do agente, tarefa, porque |
| 2 | Contexto | Se contratasse alguém hoje pra isso, o que explicaria no 1º dia? | regras da casa, tom |
| 3 | Dados | De onde vem a informação certa? O que não vale? Se faltar, o que ele faz? | fonte, não vale, se faltar |
| 4 | Critério | Como é um dia em que isso ficou perfeito? Até quando? Que número mostra isso, e o que não pode piorar junto? Tem uns 20 casos reais com a resposta certa? | sucesso, prazo, métrica principal, 1–2 guardas, gabarito |
| 5 | Autonomia | Ele só pesquisa, prepara, executa ou toca um processo inteiro? Envolve dinheiro? Algo irreversível? Gente de fora? O que NUNCA faz sozinho? | ação, riscos, proibições |
| 6 | Observação | O que quer ver no relatório? Quando? De quanto em quanto tempo revisa os erros pra ajustar uma regra? | relatório, quando, cadência do loop |
| 7 | Supervisão | Quando ele para e te chama? Quando você revisa? | gatilhos, revisão |

### 3. Calcular o nível (regra fixa — não "ache", aplique)
```
ação: consulta → N0 · rascunho/prepara → N1 · executa → N3 · coordena processo → N4
se N ≥ 3 E (dinheiro OU irreversível OU gente de fora) → N2   (prepara, humano aprova)
se N > 1 E não há fonte oficial definida               → N1   (sem fonte, só sugere)
```
Explique o nível em 1 frase com o motivo real, e diga o que precisa acontecer pra subir (N1→N2: fonte definida + 2 semanas de rascunhos sem erro; N2→N3: 4 semanas aprovando sem corrigir, só na parte sem risco; N3→N4: 2 meses de relatórios limpos e alarmes funcionando). Na dúvida entre dois níveis, **o menor**.

### 4. Entregar — gravar `AGENTE.md`
Grave no diretório atual (ou `agentes/<slug>.md` se já existir um `AGENTE.md` de outro agente — **nunca sobrescreva sem perguntar**). Estrutura:

```markdown
# Ficha do Agente — <Nome>
> Nível <Nx> · <nome do nível> — <motivo em 1 frase>. Para subir: <condição>.

## 1. Missão (intenção) … ## 7. Supervisão
(os 7 blocos, curtos)

## Instrução pronta
(prompt em 2ª pessoa, pra colar: missão + por que importa; regras da casa e tom;
fonte oficial, o que não vale, "se faltar/conflitar: <regra>", "nunca invente dados";
definição de pronto; nível com o que pode e não pode — N2 = "nada sai sem meu OK explícito";
proibições + "se pedirem, diga que vai passar pra mim"; quando parar e me chamar;
formato e horário do relatório, incluindo erros; "antes de começar, confirme em 3 linhas".)

## 3 testes antes de confiar
1. Informação faltando/contraditória na fonte → esperado: <regra de "se faltar">.
2. Pedido proibido: "<1ª proibição>" → esperado: recusa e te chama.
3. Alarme: "<1º gatilho>" → esperado: para e te chama.

## Checklist de supervisão
Antes de ligar · Todo dia (2 min) · Toda semana (10 min, ajustar UMA regra) · Todo mês (o nível ainda é o certo?)

## Loop de melhoria
Métrica principal: <…> · Guardas: <…> · Gabarito: <arquivo, N casos, parte escondida> · Revisão: <cadência>
Cada ajuste é um ciclo: hipótese → mudança numa cópia → teste no gabarito → **você decide** se promove.

## Registro de falhas
| data | o que quebrou | menor correção | regra da ficha alterada | ciclo |
```

Se a pessoa não tiver métrica ou gabarito, marque `[DEFINIR]` e diga que sem isso o agente não aprende, só repete (o ajuste semanal vira palpite). Não invente números.

### 4b. Quando o agente estiver estável (N2 ou mais) — ligar o loop
A ficha é o ponto de partida; o que faz o agente melhorar com o uso é o **loop de melhoria** (executar → medir → criticar → propor → testar → validar → promover). Quando a pessoa quiser automatizar os ajustes com registro e botão de voltar, aponte o framework **LOOP-R** (https://inematds.github.io/loop-r/guia/, skill `/loop-r iniciar` no repo `inematds/loop-r`): as respostas 4, 5 e 6 da ficha já são métrica, limites e cadência que ele pede. Regra que não muda: o sistema **propõe**, o humano **promove** — nenhuma versão pior substitui a atual por decisão do agente.

Depois de gravar, mostre na conversa só: o nível + motivo, o caminho do arquivo e os 3 testes. Não despeje o arquivo inteiro.

### 5. Se o agente for um agente de CÓDIGO (Claude Code, Codex, etc.)
Traduza o nível para a configuração real e acrescente uma seção `## Configuração sugerida` no AGENTE.md:

| Nível | Claude Code | O que mais |
|---|---|---|
| N0 · N1 | modo plano (`plan`) — só lê e propõe | instrução no `CLAUDE.md`/`AGENTS.md` |
| N2 | modo padrão — pede aprovação a cada edição/comando | proibições como regras `deny` nas permissões |
| N3 | `acceptEdits` — edita sozinho, comandos continuam pedindo | testes/build como critério de pronto; `FALHAS.md`; ajustes pelo loop (`/loop-r`) com gabarito |
| N4 | só com hooks que bloqueiam o irreversível (push, deploy, delete) + ambiente isolado | nunca "bypass" em repo com produção |

Não altere `settings.json` sozinho: proponha o trecho e aplique só se a pessoa pedir.

## Modo 2 — Auditar
Quando a pessoa colar um prompt, um `CLAUDE.md`/`AGENTS.md` ou uma descrição de agente existente:
1. Dê nota **0 (ausente) · 1 (vago) · 2 (claro)** para cada um dos 7 princípios, com a evidência (trecho citado) ou "não encontrado".
2. Aplique a regra do nível ao que o texto permite e diga se a autonomia atual está **acima** do que a regra aceita — esse é o achado mais importante.
3. Liste no máximo 5 correções, da mais arriscada pra menos, cada uma com o texto pronto pra colar.
4. Ofereça gerar a ficha completa (Modo 1) a partir do que já existe, perguntando só o que falta.

## Regras
- Uma tarefa por ficha. Se a pessoa descrever três, sugira três fichas e comece pela de menor risco.
- Nunca suba o nível pra "ser útil". A regra só abaixa.
- Não invente regra da casa, fonte ou proibição: pergunte. O que a pessoa não disse fica marcado `[DEFINIR]`.
- Versão web pra quem não usa terminal: https://inematds.github.io/7pa/ · galeria: https://inematds.github.io/7pa/galeria/
