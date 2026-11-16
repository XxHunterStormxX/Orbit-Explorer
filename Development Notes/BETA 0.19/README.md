# Orbit Explorer – BETA 0.19

## Aba Data: gráfico dos recursos
- **Gráfico "Your resources • last 3 minutes":**
  - Uma linha para cada recurso: água, energia, oxigênio e comida.
  - Cada evento aparece como uma linha tracejada vermelha com o triângulo de aviso no topo.
  - O nome e o valor ficam escritos no fim de cada linha. Passando o mouse, aparece uma linha guia com os valores daquele segundo e o nome do evento, se houver.
  - As cores vêm de uma paleta testada para daltonismo. A energia ficou laranja no gráfico (no HUD é azul-acinzentado), porque o azul dela e o da água ficavam parecidos demais.
- **Tabela "Made and used every second":** quanto cada recurso ganha e gasta sozinho por segundo, com o total em ▲ verde ou ▼ vermelho. Os cliques não entram na conta.
- **Lista "Events and your choices":** os últimos 8 eventos, com o horário e a escolha feita (ou "Waited it out").
- **Uma conta só:** o ganho e o gasto agora saem da mesma função no jogo, nas taxas do HUD e no gráfico, então os números nunca discordam.

## Radiação e escudo
| | Antes | Agora |
|---|---|---|
| Radiação subindo | 0,22/s | 0,45/s (cerca de 2×, e mais nas fases 2 e 3) |
| Tempestade solar | 2,2/s | 3,0/s |
| Escudo limpando | −1,3/s | −4/s |
| Gasto do escudo | 4 de energia/s | 8 de energia/s (Optimized Shield reduz 10% por nível) |

O escudo zera a radiação rápido, mas o painel solar sozinho não sustenta o gasto. Por isso as Power Plants passam a ter função real. No modo fácil (Explorer) tudo isso é 28% mais fraco.
