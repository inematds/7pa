# 🧭 7PA — Os 7 Princípios da Gestão de Agentes de IA

[![Ficha do Agente — 7 perguntas, seu agente de IA pronto e bem gerido](guia/assets/banner.jpg)](https://inematds.github.io/7pa/guia/)

> **Não basta criar agentes. É preciso gerenciá-los.**
> Responda 7 perguntas e seu agente de IA sai pronto: instrução, nível de autonomia calculado, testes e checklist de supervisão.

| | Português | English | Español |
|---|---|---|---|
| 🧭 **Ficha do Agente** (a ferramenta) | [abrir](https://inematds.github.io/7pa/) | [open](https://inematds.github.io/7pa/en/) | [abrir](https://inematds.github.io/7pa/es/) |
| 📖 **Guia** (o conteúdo explicado) | [ler](https://inematds.github.io/7pa/guia/) | [read](https://inematds.github.io/7pa/guia/en/) | [leer](https://inematds.github.io/7pa/guia/es/) |
| 🔓 **O segredo revelado** | [revelar](https://inematds.github.io/7pa-segredo/) | [reveal](https://inematds.github.io/7pa-segredo/en/) | [revelar](https://inematds.github.io/7pa-segredo/es/) |

## 📖 Guia de uso

Guia completo (landing + passo a passo): **https://inematds.github.io/7pa/guia/**

---

## O conteúdo, direto ao ponto

### 1. A virada

A IA deixou de ser só ferramenta de perguntas e respostas. Agora ela interpreta o que você quer, busca informação, executa tarefas e entrega resultado, com mais ou menos liberdade. Isso muda o seu papel:

- **Antes:** Você → executa o processo → resultado
- **Agora:** Você → define a intenção → organiza o contexto → delega → supervisiona → avalia

Você sai de "fazer a tarefa" e passa a **gerenciar o sistema que faz a tarefa**.

### 2. Os 7 princípios (e a pergunta que cada um responde)

| # | Princípio | A pergunta de todo dia | Em uma frase |
|---|---|---|---|
| 1 | **Intenção** | O que você quer tirar da sua mão, e por quê? | Antes de delegar, defina o propósito. |
| 2 | **Contexto** | O que você explicaria no 1º dia a um recém-contratado? | O menor contexto capaz da melhor decisão. |
| 3 | **Dados confiáveis** | De onde vem a informação certa? Quem manda quando duas fontes discordam? | Nenhum agente é melhor que seus dados. |
| 4 | **Critério de sucesso** | Como é um dia em que isso ficou perfeito? | Toda delegação precisa de sucesso definido. |
| 5 | **Autonomia com limites** | O que ele nunca pode fazer sozinho? | Autonomia cresce com evidência e controle. |
| 6 | **Observação e avaliação** | O que você quer ver pra saber se está indo bem? | O que não é observado não melhora. |
| 7 | **Supervisão humana** | Quando ele te chama? Quando você revisa? | Agentes ampliam; não eliminam o julgamento. |

É um **ciclo**: o que você aprende na supervisão (7) volta a ajustar a intenção (1). A soma é **Pessoas + Processos + Agentes**.

### 3. A escada da autonomia

| Nível | Nome | O que ele pode |
|---|---|---|
| N0 | Consulta | Responde e pesquisa. Não age. |
| N1 | Recomenda | Prepara rascunhos e sugestões. Você decide. |
| N2 | Prepara, você aprova | Deixa pronto; nada sai sem seu OK. |
| N3 | Executa | Faz sozinho, dentro das regras, e presta contas. |
| N4 | Gerencia processos | Toca um processo inteiro, com relatórios e alarmes. |

**A regra que a Ficha usa:** dinheiro, ação irreversível ou gente de fora → no máximo **N2**. Interno e reversível → pode chegar a **N3/N4**. Sem fonte oficial definida → fica em **N1**.

### 4. O que realmente importa (tirando o marketing)

Relatórios sobre "a nova era dos agentes" têm muita camada promocional. Depois do filtro, sobra:

1. **Dados confiáveis:** a organização decide qual informação tem autoridade.
2. **Automação por intenção:** você diz objetivo, contexto, restrições e critérios; o sistema escolhe parte do caminho.
3. **Sucesso explícito:** o que é bom, como medir, quando está pronto.
4. **Limites:** permissões, níveis, revisão humana, monitoramento.
5. **O gargalo mudou:** o difícil agora é definir intenção, criar contexto, organizar dados e avaliar.
6. **Demo não é produção:** o que importa é estabilidade, repetição, segurança e reação ao inesperado.

A nova disciplina não é "usar IA". É **Gestão de Agentes de IA**.

### 5. Como aplicar em 5 minutos

1. Abra a **[Ficha do Agente](https://inematds.github.io/7pa/)** e escolha um exemplo (clínica, loja, escritório contábil, professor) ou comece em branco.
2. Responda as 7 perguntas, uma por tela.
3. Receba o pacote: **Ficha**, **Instrução pronta** (pra colar no ChatGPT/Claude/Gemini), **3 testes** e **Checklist** de supervisão, com o nível de autonomia calculado.
4. Rode os 3 testes antes de confiar. Use **✨ Refinar com IA** pra lapidar.
5. Supervisione: 2 min por dia, 10 min por semana.

Prefere conversar? Use o **[prompt entrevistador](prompts/entrevistador.md)**: cole no ChatGPT/Claude e ele faz as 7 perguntas pra você.

### 🔓 O segredo

Afinal, o que são esses textos? Tem uma leitura por trás do relatório, da análise e do infográfico, e ela muda tudo. → **[inematds.github.io/7pa-segredo](https://inematds.github.io/7pa-segredo/)**

---

## Estrutura do repositório

```text
index.html              # Ficha do Agente (PT) — roda 100% no navegador, sem login
en/ · es/               # Ficha do Agente em inglês e espanhol
guia/index.html         # o conteúdo explicado (PT) + guia/en/ + guia/es/
guia/assets/            # banner e imagens
prompts/entrevistador.md# versão "conversa" pra colar no ChatGPT/Claude
conteudo/               # material original: relatório, análise, 7 princípios
capa/capa.png           # capa do catálogo INEMA
PLANO.md                # plano de produto
```

Nada é enviado a servidor: as respostas ficam só no navegador de quem usa.

---

[INEMA.CLUB](https://inema.club) · [INEMA.PRO](https://inema.pro)
