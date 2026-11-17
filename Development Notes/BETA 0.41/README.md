# Orbit Explorer – BETA 0.41 (revisão final)

Revisão completa do código para a versão final. **Nenhuma função foi removida.** O jogo funciona igual, só que mais leve e mais rápido.

## Arquivo 17% menor (3,45 MB → 2,87 MB)
- **Sprites em WebP sem perdas:** as 30 imagens dos prédios, da base, do foguete e do rover estavam em PNG. Agora estão em WebP, como o terreno já estava. Comparei pixel por pixel cada imagem antes e depois: a diferença visível é zero.
- **2 sprites que nunca apareciam no jogo foram removidos** (uma estufa em cúpula e uma torreta antiga, cerca de 220 KB).
- Isso deixa o jogo mais rápido de abrir, principalmente no celular.

## Mais leve enquanto joga
- **HUD só reescreve o que mudou:** antes, a cada segundo, uns 100 textos eram reescritos mesmo iguais (valores, custos, "Agora/Próximo" de cada card), e cada reescrita fazia o navegador recalcular a tela e retraduzir o texto. Agora cada texto só é atualizado quando o valor muda de verdade.
- **Mapa pausado atrás do menu:** o mapa da colônia era redesenhado 20 vezes por segundo mesmo com o menu na frente. Agora ele para no menu e volta sozinho no zoom de entrada do jogo.
- **CSS limpo:** foram removidas regras de recursos antigos que não existem mais (legenda e vinheta do mapa, sombras sem uso).

## Revisão e testes
- Procurei funções sem uso: nenhuma.
- Um robô jogou sozinho 10 minutos de jogo em português: comprou prédios, abriu a árvore inteira, subiu a base para o nível 2, chegou a 51 astronautas e passou por 29 eventos, **sem nenhum erro**. Outra rodada de 4 minutos em inglês também não teve erros.
- Também conferidos: a abertura completa, o menu e a troca de idioma.
