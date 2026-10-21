# Movimento e implementação em Remotion

Leia ao escrever a composição, animar UI, criar transições ou corrigir movimentos mecânicos. Verifique APIs na documentação da versão instalada e use as skills Remotion do ambiente para instruções atuais de projeto, markup, áudio, preview e render.

## Contrato da timeline por frame

Ao produzir com esta skill, entregue uma composição Remotion que calcula cada frame da peça por uma timeline explícita. A timeline deve identificar fps e duração total, intervalos de cenas e sobreposições, trilhas de camadas, ações, estados de repouso, parâmetros de movimento e pontos de áudio quando houver som. Use intervalos `[início, fim)`: o frame inicial participa e o frame final já pertence ao próximo intervalo. Calcule a duração total a partir do maior fim das trilhas, considerando as sobreposições.

Para cada evento animado, registre **camada/objeto, frame inicial, frame de chegada, frame final, estado inicial e final, propriedades que mudam, curva ou spring, relação com outras camadas e resultado perceptível**. A lista de eventos é um mapa editável, não uma pilha de imagens. Em cada frame, derive o estado das camadas do tempo da composição ou do tempo local de sua sequência. Um estado pode permanecer estável por vários frames quando a leitura exigir repouso; isso continua sendo parte da timeline.

Exemplo de mapa a 30 fps para uma transição: cartão A se desloca e amplia nos frames `84–102`; câmera acompanha nos `88–110`; o conteúdo do cartão se transforma em tela B nos `96–114`; título B é revelado nos `108–122`; todos chegam a um estado legível até o frame `138`. Os números ilustram a coordenação temporal e devem ser ajustados ao briefing. O objeto compartilhado atravessa a passagem; nenhum quadro completo da cena A ou B é usado como slide para simular a transição.

Imagens, fotografias e capturas de interface podem ser assets dentro de camadas. Se um elemento precisa mover, reagir, revelar conteúdo ou permanecer identificável durante uma transição, mantenha-o animável como camada ou componente próprio. Não gere a peça concatenando imagens prontas, trocando telas estáticas a cada batida ou usando apenas pan/zoom genérico sobre capturas. Extração de frames das referências serve à análise; não é método de produção da composição nova.

## Composição e acabamento de motion profissional

Pense na peça como uma timeline contínua de camadas, não como uma coleção de telas independentes. Planeje o que permanece, entra, sai ou se transforma durante cada passagem de cena. Quando um elemento conduz a atenção ao próximo plano, alinhe posição, direção, escala, cor e velocidade nos dois lados da transição. Um corte seco pode ser a melhor escolha se preservar a intenção.

Organize títulos, UI, personagens, fundos, sombras, brilhos e câmera em camadas controláveis. Elementos ligados fisicamente devem compartilhar o movimento base; detalhes secundários podem ter atraso e deslocamento próprios. Use máscaras, recortes, perspectiva, parallax, desfoque e motion blur somente onde acrescentarem foco, profundidade ou sensação de velocidade. Faça o tratamento de cor, contraste, textura e tipografia parecer parte da mesma peça, inclusive quando combinar assets de origens diferentes.

Antes de polir, teste o fluxo em velocidade normal: o olhar deve seguir a ação sem precisar reiniciar a leitura a cada cena. No acabamento, inspecione também os frames das transições para detectar saltos, bordas expostas, camadas fora de ordem, blur excessivo e texto que perde nitidez. Priorize ritmo, hierarquia e continuidade perceptiva sobre a quantidade de efeitos.

## Desenhe o movimento em estados

Para cada elemento importante, registre quatro estados: **origem → aproximação → repouso → saída/transformação**. Nem toda animação precisa de todos os estados, mas todo movimento precisa de motivo e destino. O repouso é parte do design: sem ele, a ação pode ocorrer sem ser percebida.

Observe três tempos separados:

1. **Início:** o momento em que o primeiro sinal de mudança aparece.
2. **Chegada:** o momento em que o objeto alcança o destino.
3. **Compreensão:** o tempo adicional necessário para ler ou reconhecer o novo estado.

Uma animação pode terminar antes que a informação seja compreendida. Ajuste a duração pela leitura em velocidade normal, não apenas por uma tabela de frames.

Para ações principais, desenhe também a curva de deslocamento ou acompanhe posição/escala em frames consecutivos. Verifique a distância percorrida a cada frame: ela deve crescer e diminuir conforme o peso desejado, sem saltos isolados ou reversão acidental. Em trajetórias com vários trechos, iguale direção e velocidade no encontro entre trechos, exceto quando houver impacto ou parada intencional. Curvas matematicamente suaves ainda podem parecer erradas se o objeto não tiver tempo de repousar.

## Easing, peso e sobreposição

- Escolha easing a partir da função: chegada precisa pode desacelerar sem bounce; objeto elástico pode ter overshoot discreto; câmera pesada tende a mudar menos abruptamente que um cursor.
- Use interpolação linear quando o movimento precisa ser constante, como um loop técnico; não a aplique por padrão a entrada e saída de elementos.
- Distribua inícios e chegadas de elementos relacionados. Um título pode começar, depois um cartão, depois um detalhe da UI. Os atrasos devem criar uma sequência perceptível, não uma cascata automática em toda cena.
- Distância, duração e escala precisam ser coerentes. Um objeto que percorre grande distância em poucos frames comunica energia e pode exigir motion blur; o mesmo tempo para um ajuste pequeno pode parecer lento.
- Anticipação e follow-through só ajudam quando tornam a ação mais física ou legível. Exageros repetidos parecem preset.
- Compartilhe o movimento base entre objetos ligados (por exemplo, dispositivo, tela e sombra) e anime detalhes internos em fases próprias. Um único `progress` aplicado a posição, escala, rotação e opacidade de todas as camadas costuma produzir movimento rígido.

### Valores de partida, não regras

Use estas faixas para iniciar uma prova e ajuste visualmente no contexto da peça.

| Evento | Ponto de partida em 30 fps | Verificação |
|---|---:|---|
| Pressão/recuperação de botão | 4–8 frames | há resposta sem parecer borracha? |
| Entrada de cartão | 10–18 frames | o cartão repousa antes de receber texto ou clique? |
| Atraso entre itens relacionados | 2–5 frames | a sequência parece intencional? |
| Aproximação de interface | 18–30 frames | o detalhe final permanece legível? |
| Confirmação de estado | 9–18 frames | o público consegue reconhecer o novo estado? |
| Revelação de gráfico | 20–36 frames | a direção segue a leitura dos dados? |

Converta frames ao fps efetivo. As faixas não foram medidas nos sete vídeos estudados.

## Transições ligadas à cena

Antes de escolher o efeito, identifique o elemento que fará a ponte. Priorize match cut, continuidade de posição, cartão que se amplia, máscara formada por objeto existente, movimento de câmera ou transformação de forma. Fades, wipes e slides são ferramentas válidas quando resolvem uma mudança específica; repetidos sem função, achatam a narrativa.

Planeje os estados de ambos os lados da transição no mesmo quadro de referência: posição do objeto, direção do movimento, escala, cor e ponto de atenção. Se dois planos se sobrepõem, confira quando cada informação fica legível e calcule a duração da composição com essa sobreposição.

Quando um objeto persistir entre cenas, mantenha-o em uma camada ou componente compartilhado durante a passagem, ou reconstrua estados de entrada/saída que coincidam no corte. Compare o frame anterior e o posterior em escala final. Máscara e blur só ajudam quando a direção e o foco já se conectam; não devem ocultar uma troca inexplicável.

## Tipografia em movimento

Separe frase, palavra ou caractere em nós animáveis somente quando a divisão acrescentar sentido ou sincronização. Mantenha as métricas finais estáveis: máscaras podem recortar a revelação, mas não devem mudar quebras de linha ou deslocar palavras já lidas. Para títulos curtos, experimente deslocamento pequeno, opacidade e máscara coordenados; para substituição de termos, preserve posição de leitura e dê um breve repouso ao termo novo. O texto em movimento pode ter blur discreto, mas seu estado de leitura precisa estar nítido. Teste no tamanho real, sobretudo em formato vertical.

## UI motion

Reconstrua em camadas animáveis somente o que precisa mudar. Uma tela estática pode permanecer imagem se isso preservar fidelidade e economizar trabalho; se cursor, botão, card, gráfico ou modal devem reagir, separe esses elementos. Use telas e fluxos reais como referência. Para cada microinteração:

1. O estado anterior está visível.
2. O alvo é reconhecível.
3. O gesto chega ao alvo.
4. O controle responde.
5. A consequência é mostrada.
6. O novo estado fica perceptível antes do corte.

Não faça o cursor acionar algo que pareça desconectado do resultado. Números animados devem terminar em valores válidos; gráficos não devem sugerir dados que o produto não possui.

## Arquitetura de projeto

Estrutura sugerida, adaptável ao tamanho do trabalho:

```text
src/
  Root.tsx                 registro das composições
  compositions/            peça principal e versões de formato
  scenes/                  cenas substanciais editáveis
  components/              tipografia, UI, mockups, cursor, gráficos
  motion/                  curvas, intervalos, câmeras e helpers úteis
  audio/                   mapa de áudio e camadas
  theme/                   tokens da marca
public/                     assets de imagem, vídeo, áudio e fontes locais
```

Não crie helpers para cada animação pequena. Abstraia quando a lógica se repete de fato ou quando um parâmetro precisa ser coordenado entre cenas. Separe dados de conteúdo e tokens de marca das constantes de movimento. Evite valores mágicos espalhados; mantenha durações e posições principais identificáveis.

Para várias cenas, use componentes separados e uma linha do tempo explícita. `Series` serve a sequências consecutivas, `Sequence` a camadas posicionadas livremente e `TransitionSeries` a cenas com transições. Em versões com Studio editável, mantenha cenas e camadas ajustáveis como nós JSX próprios. Registre cenas substanciais como composições conectadas quando o usuário precisar navegar sua timeline separadamente. Preserve uma fonte de verdade para marcos temporais compartilhados entre cenas, camadas e áudio, para que mudar uma duração não quebre a sincronização.

## Padrão de animação por frame

Use `useCurrentFrame()` e `useVideoConfig()` para calcular o movimento em todos os frames, inclusive entre os marcos de uma ação. A forma a seguir ilustra uma entrada com desaceleração; ajuste seus intervalos à cena. Confira a sintaxe conforme a versão instalada.

```tsx
import {Easing, interpolate, useCurrentFrame, useVideoConfig} from 'remotion';

export const FeatureCard = () => {
  const frame = useCurrentFrame();
  const {fps} = useVideoConfig();
  const enter = Math.round(0.45 * fps);

  return (
    <div
      style={{
        opacity: interpolate(frame, [0, enter], [0, 1], {
          extrapolateLeft: 'clamp',
          extrapolateRight: 'clamp',
          easing: Easing.bezier(0.16, 1, 0.3, 1),
        }),
        translate: interpolate(frame, [0, enter], ['0px 36px', '0px 0px'], {
          extrapolateLeft: 'clamp',
          extrapolateRight: 'clamp',
          easing: Easing.bezier(0.16, 1, 0.3, 1),
        }),
      }}
    >
      Resultado confirmado
    </div>
  );
};
```

Não use CSS `transition`, `animation` ou animações Tailwind como motor do movimento renderizado. Para propriedades editáveis no Studio, mantenha a interpolação diretamente no `style` do elemento quando apropriado. Use propriedades `scale`, `translate` e `rotate` separadas quando bastarem; reserve `transform` composto para perspectiva, skew ou ordem de transformação que exigem controle explícito.

## Mockups, profundidade e efeitos

- Comece com uma interface plana legível. Acrescente perspectiva depois de validar a informação.
- Separe dispositivo, tela, sombra e elementos que extrapolam a moldura. Prenda partes dependentes ao mesmo movimento base.
- Use parallax apenas quando houver camadas espaciais reconhecíveis. Movimento diferente sem lógica de profundidade parece desajuste.
- Halos e sombras devem preservar bordas e texto nítidos. Para motion blur e efeitos especiais, siga a orientação da versão Remotion disponível e confira custo de renderização.
- Se o render permitir amostragem temporal para motion blur, aplique-a só aos objetos rápidos e inspecione contorno, cauda e estado final. Um `filter: blur()` constante desfoca o objeto; não substitui automaticamente blur temporal de movimento. Evite blur ou glow que torne texto, logotipo e UI menos legíveis.
- Use efeitos de alto custo somente em regiões que mudam o resultado visual. Uma textura estática pode ser pré-renderizada como asset se isso simplificar a composição sem perder editabilidade importante.

## Performance e determinismo

O resultado de um frame deve depender do frame, das props e dos assets, não de tempo de relógio ou estado imprevisível. Evite `Math.random()` não determinístico por render, intervalos de navegador e trabalho caro repetido a cada frame. Pré-calcule dados que não mudam, dimensione assets para uso real e limite filtros custosos. Meça gargalos antes de reduzir qualidade. Verifique que um frame renderizado isoladamente corresponde ao mesmo frame no preview.
