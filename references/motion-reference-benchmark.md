# Padrão técnico de movimento — dez vídeos fornecidos

Leia ao planejar ou revisar uma nova peça de motion. Este documento transforma observações dos vídeos em decisões de animação e critérios de aceite; não é uma paleta, template ou licença para copiar marcas, interfaces e composições.

## Método e limites da análise

Foram inspecionados os sete clipes de `Vïdeos estudo codex/` (4 amostras visuais por segundo, com trechos adicionais a 15 fps), `inDrive-20s.mp4` (23,02 s), `VIDEO 2 (MOTION).mp4` (50 s) e `Motion podóloga 2811 - Samuel Andrade…mp4` (20,13 s), amostrados a 2 fps e com trechos adicionais a 15 fps. As três peças longas têm áudio não silencioso; os sete clipes curtos contêm faixas de áudio digitalmente silenciosas. Picos de energia das três faixas audíveis foram comparados a eventos visuais, mas a escuta perceptiva e a identificação dos sons não foram verificadas nesta análise.

Os arquivos finais mostram o resultado, não seus keyframes, curvas Bezier, plugins, shutter angle ou software de origem. Não atribua números exatos de easing, BPM, técnicas de After Effects ou causalidade sonora aos autores. Os intervalos abaixo são **pontos de partida para testes em uma peça nova**, não medições recuperadas das referências.

## O que cada vídeo ensina

| Referência | Observação de movimento | Princípio transferível | Limite a respeitar |
|---|---|---|---|
| `5CxMnrQYUpTzelHi2YC53BNMJAA.mp4` | A câmera aproxima a UI; cursor, menu e submenu respondem em cadeia. A grade surge após a seleção e o pipeline recebe uma revelação própria. | Separe movimento da câmera, do cursor e dos estados da interface; mostre a consequência antes de avançar. | Um close que corta o controle ou a confirmação enfraquece a compreensão. |
| `Hog2Dl431WVrVIPxSy5xoRsG1Y.mp4` | A busca vira uma grade em movimento; o cursor percorre produtos e um item se torna o foco antes do resumo. | Faça a câmera e a grade conduzirem o mesmo olhar; preserve a identidade espacial do item ao aproximá-lo. | Não substitua silenciosamente o objeto selecionado entre planos. |
| `Our work Motion Swell (1).mp4` | Cartões entram em perspectiva, convergem e se distribuem com atraso entre si; o centro ganha prioridade. | Anime um grupo coordenado com offsets individuais e desaceleração comum, depois reduza a movimentação para a leitura. | Perspectiva constante em conteúdo pequeno torna a UI ilegível. |
| `Our work Motion Swell (2).mp4` | Registros operacionais convergem para um estado concluído; gráfico e palavras isoladas alternam densidade. | Uma ação visual deve produzir um estado reconhecível; contraste entre passagens densas e pausas dá ritmo. | Efeito luminoso e zoom não substituem dados legíveis. |
| `Our work Motion Swell (3).mp4` | Resposta do chat progride, produtos aparecem após o texto, marca e gráficos entram em blocos distintos. | Faça texto, produto e evidência aparecerem na ordem causal; reserve um momento de repouso para cada resultado. | A quantidade de ideias em poucos segundos pode sobrecarregar; simplifique quando o benefício não for reconhecido. |
| `Our work Motion Swell (4).mp4` | Muitos painéis flutuam sob câmera mais lenta; um gráfico recebe close e números mudam em outra cadência. | Use velocidades diferentes para câmera, UI e dados; eleja um protagonista antes do zoom. | Não transforme todo o mosaico em um único bloco rígido nem atribua widgets externos ao produto. |
| `Our work Motion Swell.mp4` | Texto é digitado, cursor aciona Generate, surgem código e interface em perspectiva. | Encadeie intenção → ação → processamento → resultado, com cursor e UI em camadas independentes. | O resultado precisa corresponder ao pedido; código decorativo não prova função real. |
| `inDrive-20s.mp4` | Tipografia abre a ideia; o telefone e o mapa reaparecem, a rota desenhada orienta o deslocamento do carro, e o CTA conclui. Há pausas deliberadas entre ações. | Mantenha um motivo visual reconhecível entre cenas e dê tempo para o público entender escolha, preço, motorista e confirmação. | A peça alterna movimento com quadros estáveis; não tente mover tudo continuamente. |
| `VIDEO 2 (MOTION).mp4` | Tipografia, ícones, listas, luz, profundidade e cortes rápidos criam energia; palavras são substituídas com blur e glow. | Use contraste entre acentos rápidos e repouso; ligue efeitos a mudanças de mensagem e hierarquia. | O blur/glow intenso e texto pequeno reduzem legibilidade em alguns momentos; não os adote como padrão universal. |
| `Motion podóloga 2811 - Samuel Andrade…mp4` | Textos curtos e cápsulas entram em sequência; fotos e demonstração dão lugar ao CTA e à marca. | Em formato vertical, priorize leitura, espaçamento e prova visual antes de acelerar o ritmo. | Entradas por fade e longas pausas são simples; esta peça não deve ser a única referência para curvas e transições complexas. |

Para a sequência narrativa dos sete primeiros, veja também [referências estudadas](studied-videos.md). Amostras visuais dos três vídeos adicionais: [inDrive](frames/indrive-middle.jpg), [VIDEO 2](frames/video2-overview.jpg) e [podóloga](frames/podologa-overview.jpg).

## Regras técnicas extraídas do conjunto

1. **Velocidade desenhada, não só posição interpolada.** Para cada deslocamento principal, defina início, aceleração, região de maior velocidade, desaceleração e repouso. Um elemento não deve andar distâncias idênticas por frame durante toda a entrada, salvo movimento propositalmente constante como scroll ou viagem contínua. Compare a trajetória em frames consecutivos e ajuste a curva quando houver tranco ou velocidade mecânica.
2. **Grupos coordenados com atraso útil.** No card fan, mosaico e UI, os elementos compartilham direção e estado final, mas não começam nem terminam todos juntos. Use um grupo/câmera base e offsets pequenos apenas onde a ordem ajuda a leitura. O movimento secundário deve apoiar o foco, não competir com ele.
3. **Continuidade espacial e causal.** Antes de cortar, registre posição, escala, direção, cor e foco do objeto que conduz a próxima cena. Preserve ao menos uma relação perceptiva ou faça um corte brusco deliberado. Na UI, cursor → contato → resposta → resultado devem ser distinguíveis.
4. **Texto é parte da coreografia.** Revele por frase, palavra ou caractere conforme o sentido. Uma máscara, deslocamento curto ou mudança de foco pode guiar a leitura; não anime cada letra separadamente por hábito. Palavra-chave e imagem/prova devem repousar juntas pelo tempo necessário para serem compreendidas.
5. **Câmera, profundidade e efeitos têm hierarquia.** Mova a câmera para eleger uma evidência, não para agitar um layout estático. Ancore camadas relacionadas ao mesmo movimento base. Use blur de movimento durante deslocamentos rápidos e preserve texto e UI nítidos no repouso; halos, partículas e textura ficam abaixo da informação.
6. **Ritmo alterna ação e compreensão.** Os exemplos combinam acentos curtos com pausas, em vez de movimento máximo a cada frame. Meça a duração da leitura no formato final. Um corte pode ser rápido, mas o resultado da ação precisa permanecer reconhecível.
7. **Áudio pertence à ação, quando existir.** Nas três peças longas, há picos de energia próximos de mudanças visuais, por exemplo a entrada de fotos em `inDrive` (~7–8 s), a passagem para o logotipo em `VIDEO 2` (~25 s) e a entrada de conteúdo em `podóloga` (~10,7 s). Isto apoia marcar beats visuais e sonoros na mesma timeline. Não conclua qual efeito ou instrumento causou cada pico sem escuta. Os sete clipes curtos não fornecem referência sonora utilizável.

## Parâmetros de partida para uma nova peça a 30 fps

Use os intervalos abaixo para construir um primeiro animatic; ajuste pela distância, tamanho, carga de leitura e energia da trilha. Não trate estes números como propriedades medidas nos vídeos.

| Evento | Primeira tentativa | Inspeção obrigatória |
|---|---:|---|
| Resposta pequena de UI, pressão e recuperação | 4–8 frames | contato e consequência legíveis |
| Entrada de cartão ou palavra curta | 10–18 frames | início com intenção e desaceleração perceptível |
| Atraso entre elementos relacionados | 2–5 frames | ordem clara, sem cascata automática |
| Reposicionamento de câmera ou close de UI | 18–30 frames | foco preservado; estado final nítido |
| Sobreposição entre cenas conectadas | 4–12 frames | primeiro e último frames não expõem bordas nem duplicam foco |
| Confirmação ou estado de resultado | 9–18 frames de repouso **após** a chegada | compreensão em velocidade normal; aumente se houver texto |

Teste uma curva de chegada rápida com repouso suave, como `cubic-bezier(0.22, 1, 0.36, 1)`, ou uma curva de aceleração e desaceleração equilibradas, como `cubic-bezier(0.76, 0, 0.24, 1)`, apenas como protótipos. Um único easing para todos os objetos produz aparência de preset. Para movimentos encadeados, ajuste a velocidade no limite dos trechos para evitar uma parada ou reversão involuntária. Em Remotion, derive valores do frame e verifique a API da versão instalada.

## Aceite para movimento profissional

- Assista ao vídeo inteiro em velocidade normal e descreva o foco de cada batida sem pausar. Se o olhar precisar procurar a cena seguinte, corrija staging ou transição.
- Inspecione entradas, saídas e cortes em frames consecutivos. A posição, escala, rotação, opacidade e ordem das camadas devem mudar de modo intencional; saltos de um frame exigem explicação narrativa ou correção.
- Veja a peça no tamanho final. O texto essencial deve estar nítido no repouso, mesmo após blur, perspectiva ou glow; valores e interfaces devem ser reais ou identificados como demonstração.
- Compare o início, meio e fim. O acabamento não pode existir só no primeiro impacto: ritmo, tipografia, marca, áudio e transições precisam manter coerência até o CTA.
- Se houver áudio, escute o mix e confirme no render que acentos visuais e sonoros realmente coincidem, que a voz permanece inteligível e que caudas não são truncadas. Se não houver áudio, a peça deve continuar completa visualmente.
