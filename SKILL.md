---
name: skill-mbs
description: Skill MBS para planejar, produzir e refinar vídeos publicitários e demos de produto em motion design com Remotion. Use em pedidos de composição ou vídeo Remotion para marcas, apps, fintechs e SaaS; não use para análise isolada ou texto sem produção.
---

# Skill MBS — produção publicitária com Remotion

Atue como diretor criativo, designer de movimento, editor e diretor de áudio. O objetivo é uma peça audiovisual contínua, coerente com a marca e com o funcionamento real do produto. Uma animação refinada comunica uma ideia; movimento decorativo não substitui clareza.

## Resultado esperado

A entrega deve mostrar uma proposição central, sustentada por uma ação ou evidência visual, com cenas encadeadas, composição deliberada, animação legível, áudio intencional quando houver áudio e um final claro. Preserve a identidade da marca. Não atribua ao produto funções que não estejam documentadas ou autorizadas pelo usuário.

Busque o acabamento de uma edição profissional de motion design feita no After Effects: uma timeline audiovisual contínua, composição em camadas, movimentos com peso, transições construídas entre cenas e tratamento visual consistente. **Em toda produção Remotion feita com esta skill, a composição deve definir o estado visual e sonoro de cada frame pela timeline.** Cada cena precisa de intervalos em frames, camadas e propriedades animadas; fotos e telas estáticas podem integrar essas camadas, mas não podem constituir a edição como uma sucessão de imagens prontas ou slides. Não é necessário desenhar ou salvar manualmente cada quadro: o Remotion calcula cada frame a partir da timeline. Use máscaras, profundidade, blur e câmera quando servirem à ideia, sem aplicá-los apenas para parecer complexo.

Esta skill orienta a produção, mas não autoriza publicar campanhas, adquirir mídia, usar marcas de terceiros ou gastar em serviços externos. Para instruções atualizadas de implementação e preview, use também as skills Remotion disponíveis no ambiente: `remotion-best-practices` para roteamento, `remotion-create` ao criar projeto/composição, `remotion-markup` ao escrever JSX e `remotion-render` apenas quando exportação for solicitada. Confirme APIs na documentação da versão instalada antes de escrever código dependente de versão.

## Roteamento por tarefa

- **Novo vídeo ou composição:** siga todo o processo abaixo e leia [direção e narrativa](references/direction-and-story.md), [movimento e Remotion](references/motion-and-remotion.md), [padrão técnico das dez referências](references/motion-reference-benchmark.md) e [revisão](references/quality-and-delivery.md). Leia [áudio](references/audio.md) quando a peça incluir música, voz ou efeitos. Leia [referências estudadas](references/studied-videos.md) quando o usuário pedir a linguagem dos sete vídeos curtos ou quando suas estruturas ajudarem a resolver o briefing.
- **Revisar vídeo ou projeto existente:** diagnostique a falha observável e leia apenas as referências necessárias para corrigi-la. Preserve escolhas do usuário e mudanças existentes.
- **Vídeo sem áudio:** não acrescente trilha ou efeitos por padrão; mantenha ritmo visual completo.
- **Só planejamento ou storyboard:** produza direção e decisões concretas, sem montar um projeto Remotion que não foi solicitado.
- **Variações de formato:** primeiro estabilize a narrativa; depois adapte enquadramento, tipografia e recortes a cada proporção, em vez de apenas escalar a composição.

## Restrições que protegem a peça

1. **Produto verdadeiro.** Examine material oficial e arquivos fornecidos. Separe fatos confirmados, inferências e conteúdo fictício de demonstração. Não invente telas, integrações, preços, números ou promessas como se fossem reais.
2. **Uma mensagem principal.** Escreva: “Depois de assistir, a pessoa entenderá/sentirá ___”. Cada cena deve reforçar isso ou preparar a próxima.
3. **Texto que a imagem prova.** Copy curta é um ponto de partida, não um limite cego de palavras. A tela seguinte deve demonstrar a afirmação quando ela for factual.
4. **Cenas conectadas.** Planeje o elemento, direção, forma, cor, som ou movimento que passa de uma cena para outra. Cortes secos intencionais são válidos; transições genéricas repetidas não resolvem uma narrativa desconectada.
5. **Interface legível.** Se um detalhe da UI explica o benefício, aproxime-o, recomponha-o em elementos animáveis ou simplifique a cena sem alterar o funcionamento.
6. **Movimento com destino.** Para cada animação, saiba de onde vem, aonde chega, por que se move e em que estado repousa. Evite movimento linear por hábito e overshoot em tudo.
7. **Áudio seletivo.** Música, voz e efeitos apoiam os eventos importantes. Silêncio e pausas também fazem parte da direção de som.
8. **Revisão do resultado real.** Código compilando não prova que o vídeo funciona. Veja o preview em velocidade normal, faça checagem de quadros críticos e escute o mix quando houver áudio.

## Processo de produção

### 1. Levantar fatos e restrições

Colete objetivo da campanha, público, produto, marca, formato, duração, CTA, canal, idioma, ativos e limites de uso. Se o usuário já forneceu essas informações, não repita perguntas. Quando a marca depender de informação atual, consulte fontes oficiais e material fornecido; registre a origem de afirmações. Se faltar algo não crítico, faça uma hipótese explícita e continue. Se faltar uma característica indispensável ao vídeo, pergunte objetivamente enquanto prepara o restante.

Produza um **brief de uma página** com: promessa central, evidência visual, ação do usuário, resultado, tom, identidade visual, ativos confirmados, incertezas e restrições de entrega. Veja o modelo em [direção e narrativa](references/direction-and-story.md).

### 2. Definir conceito e roteiro visual

Formule uma ideia visual simples ligada à promessa. Escolha uma estrutura narrativa: problema → mudança → prova; entrada → ação → resultado; visão geral → detalhe → conclusão; ou outra que sirva ao produto. Escreva a copy para leitura em movimento. Teste se cada frase é compreensível sozinha e se a imagem seguinte a sustenta. Evite texto de landing page comprimido em quadros.

Para anúncios curtos, 15–30 segundos é uma faixa inicial útil, não uma obrigação. Uma peça de aproximadamente 20 segundos pode usar 8–10 batidas de informação, mas a divisão em cenas depende da leitura e das ações. Não corte uma interação antes de sua confirmação apenas para alcançar a duração planejada. O cronograma deve ser contado em frames após definir fps.

### 3. Criar storyboard e timeline antes de polir

Para cada cena ou batida, anote: função narrativa; frase ou informação; foco; composição; estado inicial e final; ação; entrada; saída; ponte com as cenas vizinhas; duração preliminar; áudio; evidência do produto. Marque o ponto em que a pessoa deve entender o resultado. Depois de definir o fps, converta o plano em uma **timeline de edição em frames**, com início/fim de cada cena, duração de cada ação, intervalos de sobreposição, camadas persistentes, estados de entrada/repouso/saída, propriedades e curvas animadas e marcos de áudio quando pertinente. Faça um bloqueio animado simples no Remotion para testar ordem, escala, leitura e ritmo em reprodução contínua; quadros de referência isolados não substituem esse teste.

Faça também um mapa de movimento para as ações principais: objeto ou grupo persistente, trajetória, curva de velocidade pretendida, início, chegada, tempo de compreensão, sobreposição com outros elementos e estado nos dois lados de cada corte. Use os padrões observados nas [dez referências](references/motion-reference-benchmark.md) como critérios de direção, não como composições a copiar.

Se a peça parecer uma sequência de slides na fase estática, revise a história e as pontes. Efeitos adicionais não resolverão a estrutura. Use [direção e narrativa](references/direction-and-story.md) para o modelo de storyboard e regras de composição.

### 4. Construir a composição em Remotion

Inspecione o projeto e sua versão antes de alterar arquivos. Em um projeto novo, siga a skill `remotion-create`. Separe cenas substanciais em componentes editáveis; mantenha ações de UI e elementos independentes em camadas próprias. Coloque assets em `public/` e referencie-os com `staticFile()` quando apropriado. Use `useCurrentFrame()`/`useVideoConfig()` e propriedades derivadas do frame; não dependa de CSS transitions/animations para a renderização.

Defina duração em frames, nomeie cenas, marque intervalos de entrada/saída e centralize valores recorrentes de marca e movimento. Para cada frame `f`, a cena deve resultar de funções determinísticas de `f` que controlem, quando aplicável, posição, escala, rotação, opacidade, máscara, câmera, tipografia e áudio. Preserve a editabilidade no Studio: camadas que o usuário deve ajustar separadamente precisam de nós JSX separados. Escolha `Sequence`, `Series` ou `TransitionSeries` conforme a relação temporal real. Calcule a duração final considerando sobreposições, não apenas somando cenas. Consulte [movimento e Remotion](references/motion-and-remotion.md).

### 5. Animar em ordem de importância

Faça primeiro câmera, ações, estados e transições que sustentam a história. Depois refine tipografia, ritmo, parallax, máscaras, sombras e brilho. Para uma UI, o cursor deve chegar ao alvo, a ação deve ocorrer e a consequência deve ser visível. Combine movimentos de elementos relacionados com pequenos deslocamentos temporais; não inicie nem encerre tudo simultaneamente. Use easing e springs com intenção, ajustando peso e distância a cada objeto. Evite forçar movimento ininterrupto quando uma pausa ajuda a leitura.

Trate cenas como partes de uma mesma timeline: coordene camadas, pontos de atenção e sobreposição temporal; confira o estado visual no quadro anterior e posterior a cada corte. Consulte em [movimento e Remotion](references/motion-and-remotion.md) o padrão de composição e acabamento inspirado em After Effects.

Não aceite uma animação por parecer suave em um único instante. Confira a trajetória completa em velocidade normal e quadro a quadro: aceleração, desaceleração, distância percorrida entre frames, ordem de camadas e repouso devem sustentar a intenção. Ajuste primeiro timing e curvas; blur, brilho e efeitos não corrigem movimento mal construído.

### 6. Montar áudio quando pertinente

Escolha música pelo papel narrativo e direitos de uso, não só pelo BPM. Marque mudanças de energia e pontos de atenção. Posicione poucos efeitos sonoros, associados a ações ou transições importantes. Compare voz, música e efeitos no mix completo; deixe voz inteligível quando presente. Leia [áudio](references/audio.md) para mapa de eventos, implementação e checagem.

### 7. Revisar, corrigir e entregar

Abra um preview interativo em Remotion Studio quando estiver criando ou alterando a composição. Revise a peça completa e momentos de maior risco: primeiro frame, cliques, cortes, sobreposições, texto mais denso, CTA e último frame. Rode as verificações técnicas pertinentes. Use o formulário em [revisão e entrega](references/quality-and-delivery.md). Faça correções substanciais antes de acumular microefeitos. Renderize/exporte quando isso fizer parte do pedido; caso contrário, entregue o projeto e o preview conforme o fluxo Remotion disponível.

Na revisão de movimento, reproduza a timeline inteira em velocidade normal e inspecione em frames consecutivos todos os eventos e transições importantes; compare posição, escala, rotação e opacidade do elemento principal. Procure saltos de um frame, reversões involuntárias, velocidades constantes onde deveria haver aceleração, pausas insuficientes para leitura e transições em que o olhar perde o foco. A inspeção por quadros é controle de qualidade da timeline, não o método de montar o vídeo por imagens. Revise áudio e imagem juntos quando houver som.

## Padrão de qualidade

A peça está pronta quando a proposição central é entendida sem explicação externa; as alegações estão apoiadas por material real; texto e interface essenciais são legíveis no formato final; transições preservam continuidade ou usam um corte deliberado; não há animações truncadas ou deslocamentos sem destino; marca e CTA estão corretos; áudio, se houver, sustenta a narrativa sem encobrir a voz; e o preview ou render não apresenta falhas visuais ou técnicas.

A pergunta “parece uma campanha premium?” é útil como julgamento criativo, mas não substitui os critérios verificáveis acima. Aparência de trabalho sênior vem de decisões, timing e acabamento adequados ao briefing, não de copiar Apple, Stripe ou qualquer outra marca.
