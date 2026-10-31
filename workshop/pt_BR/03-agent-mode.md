<!-- l10n-sync: source-file="03-agent-mode.md" -->
# Parte 3: Agent Mode — Construa o Jogo

---

O Agent Mode permite que o Copilot planeje e implemente alterações de forma autônoma em múltiplos arquivos. Em vez de escrever código linha por linha, você descreve o que deseja e o Copilot descobre quais arquivos criar ou modificar, implementando tudo de ponta a ponta.

## Tarefa 1: Conecte a batalha

<!-- track:vscode:start -->
1. Mude para o modo **Agent** no Copilot Chat (selecione "Agent" no menu dropdown de modo).

2. Insira este prompt:
<!-- track:vscode:end -->

<!-- track:cli:start -->
1. Retorne o Copilot CLI ao fluxo normal de programação (ou continue no autopilot se quiser que ele prossiga até você interrompê-lo).
2. Se ajudar, mencione o arquivo da página para dar mais contexto: `@src/pages/index.astro`.
3. Insira este prompt:
<!-- track:cli:end -->

   > Add client-side JavaScript to the battle page that:
   > 1. When the Battle button is clicked, gets both usernames from the inputs
   > 2. Validates both are filled (show error if not)
   > 3. Fetches both users' contribution data in parallel from our API
   > 4. Renders contribution graphs as colored grids — each day is a colored square using GitHub's color palette
   > 5. Shows a VS badge between the two users
   > 6. Displays username, total contributions, and date range for each user
   > 7. Handles loading states and errors
   > 8. Also triggers on Enter key in input fields.
   > 9. Simple UI for now that is already scaffolded.
   >
   > Use TypeScript interfaces for the contribution data structure.

<!-- track:vscode:start -->
3. Deixe o Agent Mode trabalhar na implementação em `index.astro`. Observe enquanto ele planeja sua abordagem, identifica os arquivos que precisa modificar e escreve o código.

4. Revise as alterações propostas na visualização de diff antes de aceitá-las.
<!-- track:vscode:end -->

<!-- track:cli:start -->
4. Deixe o Copilot CLI implementar as alterações em `src/pages/index.astro`.
5. Inspecione as alterações geradas com `/diff` e aprove-as.
<!-- track:cli:end -->

## Tarefa 2: Teste a Batalha

1. Insira `octocat` e `torvalds` como os dois nomes de usuário e clique em **Battle**.
2. Você deve ver ambos os gráficos de contribuição renderizados lado a lado com grids coloridos.
3. Teste os casos de erro:
   - Deixe um ou ambos os campos vazios e clique em Battle — você deve ver um erro de validação.
   - Insira um nome de usuário inválido — o app deve exibir um erro da API.
4. Teste pressionando **Enter** em qualquer campo de entrada — deve disparar a batalha assim como clicar no botão.

## Tarefa 3: Itere com o Agent

Se algo não estiver totalmente correto, dê feedback ao Agent diretamente no chat. Por exemplo:

- *"The contribution squares are too large, make them 12x12px"*
- *"Add a hover tooltip showing the date and contribution count"*
- *"The loading state needs a pulse animation"*

<!-- track:vscode:start -->
O Agent Mode lida naturalmente com alterações em vários arquivos e iterações. Cada prompt de acompanhamento se baseia na conversa, permitindo refinar a implementação gradualmente sem começar do zero.
<!-- track:vscode:end -->

<!-- track:cli:start -->
As sessões do Copilot CLI mantêm o histórico, então cada prompt de acompanhamento aproveita o anterior. Use `/session` ou `/context` para inspecionar o contexto que o Copilot está mantendo e `/review` após uma iteração maior para procurar bugs ou melhorias.
<!-- track:cli:end -->

## Dicas para esta parte

- **Seja específico sobre o que você quer** — requisitos claros levam a resultados melhores.
- **Divida tarefas grandes em prompts menores** se o Copilot sair do rumo.
- **Revise as alterações antes de aceitar** — use a visualização de diff para entender o que foi modificado.
- **Teste o app após cada etapa de implementação** para manter os problemas localizados.

## ✅ Parte 3 Concluída

Você aprendeu a:

- Usar o **Agent Mode** para implementações complexas em múltiplos arquivos
- **Iterar nos resultados** com feedback direcionado
- Lidar com o **ciclo de vida completo de uma funcionalidade** — da implementação ao teste e refinamento — em uma única conversa
