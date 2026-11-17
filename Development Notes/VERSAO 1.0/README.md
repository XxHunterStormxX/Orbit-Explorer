# Orbit Explorer – VERSÃO 1.0

Versão final do jogo para o NASA Space Apps Challenge.

**Link para jogar:** https://xxhunterstormxx.github.io/Orbit-Explorer/Development%20Notes/Orbit_Explorer_1.0.html
(o link antigo, `Orbit_Explorer_BETA.html`, continua funcionando com o mesmo jogo)

## Novidade da 1.0: cores das estruturas por nível
- **A base principal muda de cor** a cada nível: **cinza** (1), **azul** (2), **verde** (3), **roxo** (4) e **dourado** (5). São as cores que já existem no layout.
- **Árvore com 5 níveis:** cada nível da base abre uma **fileira nova** na árvore ("NÍVEL 2 · AZUL", "NÍVEL 3 · VERDE"...). Os níveis ainda fechados aparecem com cadeado e mostram qual nível da base pedem.
- Cada fileira tem **um nó por galho** (Água, Comida, Oxigênio, Energia e Ciência). Desbloquear um nó:
  - **pinta todos os prédios daquele galho** no mapa com a cor nova. As partes de metal mudam de cor; as luzes, o vidro e as plantas continuam iguais.
  - dá **+25% de produção por nível** aos prédios daquele galho (até +100% no dourado).
- Cada nó pede **o nível de cor anterior** e o **nível da base**.

  | Nível | Custo |
  |---|---|
  | Azul | 400 Ciência |
  | Verde | 1.500 Ciência |
  | Roxo | 5.000 Ciência |
  | Dourado | 15.000 Ciência |

- O nó já mostra o prédio **pintado com a cor** que ele vai ter.
- Ao subir a base, aparece o aviso "A base ganhou uma cor nova!".
- O tutorial da Árvore explica as cores (inglês, português e espanhol).

## Cores dos recursos
**Água** e **Energia** eram dois azuis parecidos.
- **Energia** agora é **amarela** (⚡), em todo o jogo: HUD, botão do Painel Solar, cards e tutorial.
- **Comida** ficou **laranja**, para não confundir com o amarelo da Energia.

## Testes
- Prints do mapa (base roxa no nível 4 e prédios pintados) e da árvore inteira (níveis 2 a 5).
- Robô jogando 7 minutos sozinho: **nenhum erro**.

## Tudo o que o jogo tem na 1.0
Abertura animada, menu com ranking mundial (Firebase), apelido com filtro de palavrões, tutorial, 3 idiomas, 3 dificuldades, cliques com melhorias e Auto Clicker, árvore de habilidades com 5 níveis de cor, prédios com upgrade individual, nível da base, eventos com dados reais da NASA, escudo contra radiação, música gerada na hora e salvamento automático.
