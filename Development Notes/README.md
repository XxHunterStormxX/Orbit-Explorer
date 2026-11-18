# Orbit Explorer – Development Notes

## ⭐ Versão final

**A versão final do jogo está dentro desta pasta:** [`Orbit_Explorer_Final_Version.html`](Orbit_Explorer_Final_Version.html)

**Link para jogar:** https://xxhunterstormxx.github.io/Orbit-Explorer/Development%20Notes/Orbit_Explorer_Final_Version.html

O link antigo, `Orbit_Explorer_BETA.html`, continua funcionando e abre o mesmo jogo.

## O que mudou depois da 1.0
- **Prédios coloridos para as 13 estruturas:** a cada nível da base (2 a 5), a árvore abre uma fileira com os 13 prédios (azul, verde, roxo e dourado).
  - Cada nó da árvore **libera a versão colorida** daquela estrutura na aba **Build**.
  - Cada cor tem o **seu próprio card no Build**, no mesmo padrão dos outros (imagem pintada com a cor, "Built", Now/Next, custo e botão Build), logo depois do card original. As cores ainda não liberadas aparecem com **cadeado**.
  - **Preço:** quanto mais alta a cor, mais caro. A primeira compra custa o preço base × 8 (azul), × 25 (verde), × 80 (roxo) ou × 250 (dourado). Cada nova compra da mesma cor sobe ×1,4.
  - **Força:** cada prédio colorido vale **2 (azul), 3 (verde), 5 (roxo) ou 8 (dourado)** prédios normais. Ele produz mais, faz a tripulação gastar menos água ou oxigênio, faz o escudo gastar menos ou dá mais espaço, conforme a estrutura.
  - Os prédios coloridos aparecem no mapa com a sua cor.
  - Desbloquear uma cor na árvore custa 150, 500, 1.500 e 4.000 de Ciência.
- **Radiação progressiva:** sobe +20% por nível da base e, depois de 4 minutos de jogo, +10% por minuto, até dobrar. Assim os níveis altos continuam desafiadores.
- **Base principal mais exigente:** cada nível pede mais prédios. Do nível 2 em diante, ela também pede prédios coloridos da cor do nível (azul no 2, verde no 3, roxo no 4) de Ice Drill, Farm Tunnel, Oxygen Generator, Power Plant e Science Lab.
- **Ranking com astronautas:** além do tempo, a tabela mostra quantos astronautas a base chegou a ter, para incentivar manter mais gente viva.
- **Medidor de radiação:** a radiação saiu da fileira de recursos (ela é um perigo, não um recurso) e virou um medidor próprio ao lado da vida, estilo contador Geiger: barra em segmentos do verde ao vermelho e fundo listrado de perigo. Ele pisca em vermelho a partir de 75.
- **Celular:** a Árvore encolhe para caber inteira na tela, e no iPhone tocar rápido não dá mais zoom. As abas de baixo aparecem sem precisar rolar, e os botões de clique ficaram menores (ícone no canto), deixando mais espaço para ver a base.

## Organização da pasta
| Item | O que é |
|---|---|
| `Orbit_Explorer_Final_Version.html` | **Versão final do jogo** |
| `Orbit_Explorer_BETA.html` | Mesmo jogo, mantido para o link antigo funcionar |
| `VERSAO 1.0/` | A versão 1.0 com o README dela |
| `BETA 0.N/` | Histórico de cada versão de desenvolvimento, cada uma com README |
| `firestore.rules` | Regras do ranking mundial (Firebase), dentro de `VERSAO 1.0/` |
| `README_INTERNO_ORBIT_EXPLORER.md` e `PATCH_NOTES_ORBIT_EXPLORER_0.10.md` | Notas internas antigas |
