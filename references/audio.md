# Trilha, voz e sound design

Leia quando o vídeo tiver música, voz, efeitos ou quando o usuário pedir avaliação sonora. Se o trabalho for silencioso, preserve a decisão.

## Mapa de áudio antes da mixagem

Para cada momento importante, defina:

| Campo | Decisão |
|---|---|
| Evento visual | O que muda e por que importa? |
| Função do áudio | Preparar, confirmar, energizar, conectar ou oferecer pausa? |
| Fonte | Música, voz, efeito, ambiência ou silêncio? |
| Posição | O som começa antes, junto ou depois da mudança visual? |
| Duração | Onde termina ou se dissolve? |
| Prioridade | Ele compete com a voz ou com outra informação? |

Não associe automaticamente um whoosh a cada entrada. Um efeito perde valor quando tudo recebe o mesmo tratamento. Reserve impactos para viradas narrativas, cliques para ações que precisam de confirmação e texturas para continuidade ou atmosfera. O som pode atravessar um corte e preparar a cena seguinte; o deslocamento deve ser intencional.

## Escolher a trilha

Analise energia, instrumentos, pulso, pausas, mudanças e clima antes de posicionar cenas. BPM ajuda a localizar eventos, mas não dita todos os cortes. Uma narrativa curta pode usar alguns acentos musicais e deixar movimentos secundários independentes. Se a trilha não cresce com a peça, ajuste edição ou escolha musical; não force efeitos sobre a música para simular progressão.

Use apenas material fornecido, licenciado ou cujo uso esteja autorizado. Registre a fonte da faixa e das licenças no projeto quando necessário. Não associe uma marca a uma faixa conhecida sem autorização.

## Voz e inteligibilidade

Se houver locução, ela é uma camada narrativa principal. Ajuste o espaço para cada frase e evite revelar texto essencial em competição com outra fala importante. Escute o mix em volume baixo: a mensagem deve permanecer compreensível. Reduza música e efeitos sob a voz em vez de apenas aumentar o volume da locução. Não atribua números fixos de loudness como regra universal sem conhecer o canal de entrega e suas especificações.

## Implementação Remotion

Na versão Remotion consultada para esta skill, `<Audio>` de `@remotion/media` aceita `src`, `from`, `trimBefore`, `trimAfter`, `volume` e outros controles. Assets locais ficam em `public/` e podem ser referenciados por `staticFile()`. Verifique a versão instalada. Exemplo mínimo:

```tsx
import {Audio} from '@remotion/media';
import {staticFile} from 'remotion';

export const Soundtrack = () => (
  <>
    <Audio src={staticFile('audio/music.mp3')} volume={0.55} />
    <Audio src={staticFile('audio/confirm.wav')} from={96} volume={0.7} />
  </>
);
```

Os volumes do exemplo não são um padrão de mixagem. Ajuste ouvindo a peça completa. Para envelopes de volume, use interpolação ligada ao frame, com extrapolação controlada. Mantenha um mapa de entradas sonoras para não perder sincronização após mudar a duração de uma cena.

## Revisão auditiva

1. Ouça com atenção aos primeiros e últimos 0,5 segundo. Há cortes secos ou caudas truncadas?
2. Ouça em nível baixo. Voz e ações sonoras essenciais continuam claras?
3. Ouça sem olhar. Música e efeitos contam uma progressão coerente ou parecem colados em elementos isolados?
4. Veja sem som. A peça ainda comunica a ação e o resultado? O áudio reforça a história, não deve consertar uma história visual confusa.
5. Verifique ruído, picos desconfortáveis, efeitos repetidos, sobreposição de sons parecidos e silêncio acidental.
6. Em versões de plataforma, confira as exigências específicas de formato, duração e nível de áudio antes de exportar.

Na análise dos dez vídeos fornecidos, as faixas dos sete clipes curtos estavam digitalmente silenciosas. As três peças longas tinham áudio não silencioso e alguns picos de energia próximos a mudanças visuais, mas a escuta perceptiva e a identidade dos sons não foram verificadas. Use [o estudo técnico](motion-reference-benchmark.md) para o que foi observado e não atribua efeitos, instrumentos ou BPM específicos a essas referências.
