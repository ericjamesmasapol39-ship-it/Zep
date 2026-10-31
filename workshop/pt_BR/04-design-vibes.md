<!-- l10n-sync: source-file="04-design-vibes.md" -->
# Parte 4: Tema Orientado a Design

---

Nesta parte, você vai usar o **Plan Mode** para projetar uma transformação visual completa e o **Agent Mode** para implementá-la. Isso é desenvolvimento orientado a design — comece com a visão, itere nos visuais e deixe o Copilot cuidar do trabalho pesado de CSS.

## Tarefa 1: Planeje o tema retrô

<!-- track:vscode:start -->
Mude para o modo **Plan** no GitHub Copilot.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Use `/plan` no GitHub Copilot CLI ou pressione **Shift+Tab** até ativar o plan mode.
<!-- track:cli:end -->

Insira este prompt:

> I want to transform this page into a full retro arcade experience. Plan a comprehensive visual overhaul that includes: CRT scanline effects on the background, neon glow on the title that pulses like a neon sign, animated VS badge with gradient color shifts, shine/shimmer overlay on the user result cards, float-in animations for input fields, color-shifting loading text between green and purple, and hover glow effects on contribution squares. Keep the dark background (#0a0a1a) with green (#5fed83) and purple (#8a2be2) accent colors. Use a dark theme with the Press Start 2P retro gaming font from Google Fonts.

O Copilot vai gerar um plano de implementação detalhado cobrindo todos os efeitos visuais. **Não aceite imediatamente** — revise o plano e itere:

- Sugira ajustes no timing das animações (ex.: "Make the neon pulse slower, around 3 seconds")
- Pergunte sobre efeitos específicos (ex.: "How will the shimmer overlay work on the cards?")
- Solicite mudanças na abordagem se algo não parecer correto

Quando estiver satisfeito com o plano, deixe o Copilot prosseguir com a implementação.

## Tarefa 2: Implemente o Tema

Peça ao Copilot para implementar o plano:

> Implement the retro arcade theme plan we just designed.

O Copilot vai adicionar múltiplas animações CSS, pseudo-elementos e transições na sua folha de estilos. Isso pode incluir:

- `@keyframes` para scanlines, pulso neon, shimmer e efeitos de float-in
- Pseudo-elementos (`::before`, `::after`) para efeitos de sobreposição
- CSS custom properties para as cores do tema
- Estados de transição e hover para elementos interativos

Depois que as alterações forem aplicadas, **verifique a pré-visualização no seu navegador** para ver a transformação completa do tema retrô arcade.

<!-- track:cli:start -->
Depois que as alterações forem aplicadas, use `/diff` para revisar as mudanças de estilo antes de aprová-las.
<!-- track:cli:end -->

## Tarefa 3: Ajuste Fino das Vibes

> **⚠️ Não está vendo as alterações?** Se o novo tema ou as animações não aparecerem, pare o servidor de desenvolvimento (`Ctrl+C`), reinicie com `npm run dev` e atualize o navegador completamente (`Ctrl+Shift+R`).

Mantenha a pré-visualização do navegador aberta e itere no design. Tente prompts como:

> The scanline effect is too strong, reduce opacity to 0.03

> Add a subtle electrical flicker to the title text

> The VS badge should pulse more dramatically

Isso é **desenvolvimento orientado a design** — você está iterando na saída visual em tempo real. Cada prompt refina a experiência até que fique perfeita. Não se contente com "bom o suficiente" — aperfeiçoe as vibes até que a página pareça pertencer a um gabinete de arcade.

## Tarefa 4: Atualize as instruções

Suas instruções de workspace devem refletir decisões importantes de design. Peça ao Copilot:

<!-- track:vscode:start -->
> Add a design guide section to copilot-instructions.md describing our retro arcade theme: colors, fonts, animation style
<!-- track:vscode:end -->

<!-- track:cli:start -->
> Update our repository instructions with a short design guide for the retro arcade theme: colors, fonts, animation style, and the rule that new UI should keep the neon aesthetic.
<!-- track:cli:end -->

Isso mantém futuras interações com o Copilot alinhadas à identidade visual definida. Novos recursos e componentes seguirão a estética retrô arcade.

Faça commit das instruções atualizadas e das alterações de design quando a página estiver como você quer.

## ✅ Parte 4 Concluída

**O que você aprendeu:**

- Usar fluxos de planejamento para definir um **sistema de design antes da implementação**
- **Iterar na saída visual** — use prompts rápidos de acompanhamento para ajustar animações, cores e efeitos
- **Manter as instruções atualizadas com decisões de design** — documente seu tema para que o Copilot mantenha a consistência
- **Fluxo de desenvolvimento orientado a design** — comece com a visão, implemente com IA, refine até ficar perfeito
