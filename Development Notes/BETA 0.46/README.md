# Orbit Explorer – BETA 0.46 (ranking no menu, filtro de palavrões e ranking online)

## Ranking sempre visível no menu
- O ranking agora é uma **tabela fixa no canto esquerdo do menu**, não mais um painel escondido.
- Colunas: **#**, **apelido** (com o nível da base e a dificuldade) e **tempo**. Os 3 primeiros ficam em ouro, prata e bronze, e o seu apelido tem borda verde.
- A tabela se atualiza sozinha quando o menu aparece e quando você volta do jogo.
- Em telas menores que 1200 px (celular e tablet), ela fica **embaixo das opções do menu**.

## Filtro de palavrões
- Bloqueia apelidos com palavrões em **português, inglês e espanhol**.
- Também pega os truques mais comuns: acentos, números no lugar de letras (P0RR4, M3RD4), símbolos (F@CK, P*TA) e letras repetidas (MERRRDA).
- Palavras curtas (CU, PAU, ROLA...) só são barradas sozinhas, para não bloquear nomes normais como ESCUDO, CURIOSO, ROLANDO ou COCKPIT.
- O apelido aceita só letras, números, espaço, - e _.
- Se o apelido for barrado, aparece "Esse apelido não é permitido. Escolha outro!".

## Ranking online (pronto, falta ligar o Firebase)
- O código do ranking mundial está pronto e usa o **Firebase Firestore** (grátis).
- Enquanto o Firebase não estiver configurado, o jogo usa o **ranking deste aparelho**, como antes.
- Depois de ligado:
  - a tabela do menu mostra o **ranking mundial**;
  - o fim de jogo mostra "Ranking mundial: posição N";
  - sem internet, volta sozinho para o ranking do aparelho.
- O tempo é enviado no fim de jogo, ao voltar ao menu e a cada 30 segundos de partida.
- **Segurança (`firestore.rules`):** o servidor só aceita apelidos válidos e sem palavrões, tempos entre 1 segundo e 24 horas, e só **substitui um tempo por outro maior**. Ninguém consegue apagar nada.

## Testes
- 13 palavrões e variações barrados; 12 nomes normais **aceitos** (ESCUDO, COCKPIT, PICANHA, FAGNER...).
- 3 jogadores seguidos com recordes e posições certos, e a tabela atualizada no menu.
- Prints no desktop e no celular, **nenhum erro**.
