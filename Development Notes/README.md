# Orbit Explorer – Development Notes

## ⭐ Versão final

**A versão final do jogo está dentro desta pasta:** [`Orbit_Explorer_Final_Version.html`](Orbit_Explorer_Final_Version.html)

**Link para jogar:** https://xxhunterstormxx.github.io/Orbit-Explorer/Development%20Notes/Orbit_Explorer_Final_Version.html

O link antigo, `Orbit_Explorer_BETA.html`, continua funcionando e abre o mesmo jogo.

## O que mudou depois da 1.0
- **Prédios coloridos para as 13 estruturas:** a cada nível da base (2 a 5), a árvore abre uma fileira com os 13 prédios (azul, verde, roxo e dourado).
  - Cada nó da árvore **libera a versão colorida** daquela estrutura na aba **Build**.
  - Cada card do Build tem a linha **"Versões coloridas"**: cada cor tem o seu botão, o seu preço e o seu contador.
  - **Preço:** quanto mais alta a cor, mais caro. A primeira compra custa o preço base × 4 (azul), × 12 (verde), × 35 (roxo) ou × 100 (dourado). Cada nova compra da mesma cor sobe ×1,3.
  - **Força:** cada prédio colorido vale **2 (azul), 3 (verde), 5 (roxo) ou 8 (dourado)** prédios normais. Ele produz mais, faz a tripulação gastar menos água ou oxigênio, faz o escudo gastar menos ou dá mais espaço, conforme a estrutura.
  - Os prédios coloridos aparecem no mapa com a sua cor.
  - Desbloquear uma cor na árvore custa 150, 500, 1.500 e 4.000 de Ciência.
- **Radiação progressiva:** sobe +20% por nível da base e, depois de 4 minutos de jogo, +10% por minuto, até dobrar. Assim os níveis altos continuam desafiadores.

## Organização da pasta
| Item | O que é |
|---|---|
| `Orbit_Explorer_Final_Version.html` | **Versão final do jogo** |
| `Orbit_Explorer_BETA.html` | Mesmo jogo, mantido para o link antigo funcionar |
| `VERSAO 1.0/` | A versão 1.0 com o README dela |
| `BETA 0.N/` | Histórico de cada versão de desenvolvimento, cada uma com README |
| `firestore.rules` | Regras do ranking mundial (Firebase), dentro de `VERSAO 1.0/` |
| `README_INTERNO_ORBIT_EXPLORER.md` e `PATCH_NOTES_ORBIT_EXPLORER_0.10.md` | Notas internas antigas |
