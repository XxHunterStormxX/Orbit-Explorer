# Orbit Explorer – BETA 0.40

## Idiomas: English, Português e Español
As configurações (SETTINGS no menu) ganharam a opção **IDIOMA / LANGUAGE** com três botões: **English**, **Português** e **Español**.

- **O jogo inteiro é traduzido:** abertura, menu, configurações, tutorial, HUD, botões de clique, Construir, Árvore, Base, Dados (inclusive o gráfico), alertas do topo, eventos com sirene e suas escolhas, textos flutuantes, janela do prédio, fim de jogo, fontes da NASA e dicas dos botões.
- **Troca na hora:** escolher outro idioma muda tudo imediatamente, até no meio de uma partida.
- **Fica salvo:** o idioma é lembrado no navegador junto com as outras configurações.
- **Tutorial:** as 12 páginas foram reescritas em português e espanhol (não é tradução automática).
- **Acentos:** conferidos nas duas fontes pixel (Á, ç, ñ, í...).

### O que continua em inglês, de propósito
- O nome do jogo **ORBIT EXPLORER**, **NASA Space Apps Challenge** e **Tutorial**.
- Os níveis de dificuldade **Explorer / Astronaut / Commander** (são "patentes" do jogo).
- **ON / OFF** no botão do escudo (cabe no espaço pequeno).
- Os títulos de estudos e relatórios reais da NASA (NTRS, ISS, DONKI), que são documentos oficiais em inglês.

### Como funciona por dentro
- O jogo continua escrito em inglês. Um dicionário com cerca de 400 frases (inglês → português → espanhol) troca cada texto quando ele aparece na tela.
- Números e nomes de prédios, eventos e níveis da base entram como "coringas", então frases como "Parabéns! Perfuratriz de Gelo foi construído!" funcionam com qualquer prédio e qualquer número.
- Para adicionar um texto novo no futuro, basta incluir uma linha no dicionário `I18N`.

## Backups
Seguindo a regra de backups (com 10, apagar os 9 mais antigos), foram apagados os backups locais 0.28 a 0.36.
