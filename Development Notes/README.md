# Orbit Explorer – Development Notes

## ⭐ Versão final

**A versão final do jogo está dentro desta pasta:** [`Orbit_Explorer_Final_Version.html`](Orbit_Explorer_Final_Version.html)

**Link para jogar:** https://xxhunterstormxx.github.io/Orbit-Explorer/Development%20Notes/Orbit_Explorer_Final_Version.html

O link antigo, `Orbit_Explorer_BETA.html`, continua funcionando e abre o mesmo jogo.

## O que mudou depois da 1.0
- **Cores para as 13 estruturas:** a cada nível da base (2 a 5), a árvore abre uma fileira com os 13 prédios. Cada nó pinta aquele prédio no mapa (azul, verde, roxo e dourado) e o deixa mais forte:
  - **+25% de produção por cor:** Ice Drill, Farm Tunnel, Oxygen Generator, Power Plant, Science Lab, Space Antenna, Food Greenhouse e Foldable Solar Panels.
  - **Água e oxigênio:** com o Water Recycler e os Air Filters, a tripulação gasta menos.
  - **Escudo:** com o Optimized Shield, ele gasta menos energia.
  - **Storage Depot:** +250 de espaço em todas as barras por cor.
  - **Habitat Module:** +5 vagas para astronautas por cor.
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
