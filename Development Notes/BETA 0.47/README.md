# Orbit Explorer – BETA 0.47 (ranking mundial no ar)

## Ranking online ligado
O jogo agora está conectado ao **Firebase Firestore** (projeto `orbit-explorer-56f4e`). **Todo mundo que abrir o link**, em qualquer computador ou celular, entra no mesmo ranking.
- A tabela do menu mostra **"Ranking mundial: todo mundo que joga, em qualquer aparelho."**
- O fim de jogo mostra **"Ranking mundial: posição N"**.
- Sem internet, o jogo volta sozinho para o ranking do aparelho.

## Regras de segurança (`firestore.rules`)
As regras foram refeitas para o editor do Firebase aceitar: a função ficou dentro do bloco principal e sem acentos. Elas já estão publicadas no projeto. Testes feitos direto no servidor:

| Teste | Resultado |
|---|---|
| Ler o ranking | aceito |
| Gravar um tempo válido | aceito |
| Gravar apelido com palavrão | **recusado** |
| Gravar tempo absurdo (999.999 s) | **recusado** |
| Trocar um recorde por um tempo menor | **recusado** |
| Apagar um tempo | **recusado** |

## Apelidos sem acento
O servidor só aceita letras de A a Z, números, espaço, - e _. Por isso o jogo **tira os acentos** do apelido: JÚLIA vira JULIA, JOÃO vira JOAO.

## Teste completo pelo jogo
Partida com o apelido TESTE: o tempo foi enviado, o fim de jogo mostrou "NOVO RECORDE! · Ranking mundial: posição 1" e a tabela do menu carregou o ranking mundial. **Nenhum erro.**
