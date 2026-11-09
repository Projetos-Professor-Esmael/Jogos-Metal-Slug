# Operação Ferro & Fogo

Run-and-gun 2D em HTML, CSS e JavaScript puro (canvas), baseado no GDD. São 9 fases: 3 níveis (Fácil, Médio, Difícil) com 3 fases cada. Cada fase termina com um chefe, e vencer libera a próxima.

## Publicar no GitHub Pages

1. Crie um repositório e envie `index.html` e este `README.md` para a branch `main`.
2. Em **Settings > Pages**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`.
3. Abra `https://SEU-USUARIO.github.io/NOME-DO-REPO/` após cerca de um minuto.

Para testar localmente basta abrir o `index.html` no navegador.

## Controles

| Ação | Entrada |
|---|---|
| Mover | A / D ou setas esquerda e direita |
| Pular | W, Espaço ou seta para cima |
| Descer de plataforma | S ou seta para baixo |
| Mirar | Mouse (360 graus) |
| Atirar | Botão esquerdo |
| Granada | Botão direito |
| Pausa | P ou Esc |
| Som | M |
| Tela cheia | F |

## Celular

Em telas de toque aparecem controles na tela: analógico à esquerda (andar, e para cima mira para cima), botão de tiro grande à direita (arraste dentro dele para mirar em qualquer ângulo), pular, descer de plataforma, granada, entrar/sair de veículo (E), Slug Attack (Q) e pausa. Os botões são montados por uma função recursiva a partir da árvore `TUI` no fim do `index.html`, então basta editar esses dados para reorganizar o layout.

## Estilo Metal Slug

- **Veículos** (tecla E): Metal Slug SV-001 (tanque, com Slug Attack na tecla Q), Slugoid (robô de saltos altos com vulcan), Slug Flyer (voa com W/S) e camelo armado. Quando o veículo perde toda a vida, você é ejetado.
- **Armas** (letras nos itens): Heavy Machine Gun, Flame Shot, Rocket Launcher, Shotgun e Laser, com munição limitada.
- **Obeso**: comer 🍗 aumenta tamanho e dano dos tiros, mas reduz a velocidade por alguns segundos.
- **Zumbi**: tiros verdes de drones transformam Rafe por 10 s, com imunidade a balas e jato de sangue.
- **Prisioneiros**: soltam arma, dão vida e granadas e lançam uma onda de energia.
- **Cenário destrutível**: caixas, barris e arbustos escondem comida, armas, vida ou prisioneiros.
- **Rota alta**: no meio de cada fase, uma sequência de plataformas leva a um prêmio (Laser e 1000 pontos).

## Backup de progresso

O GitHub Pages não tem banco de dados, então o progresso fica no `localStorage` do navegador. Ele some se você limpar os dados do site ou trocar de aparelho.

- **Exportar backup** (menu inicial) baixa um arquivo `.json` com fases concluídas e melhores pontuações.
- **Importar backup** lê esse arquivo e restaura o progresso, validando o formato antes de aplicar.

## Regras resumidas

- Vida: 5 (Fácil), 4 (Médio) ou 3 (Difícil) corações. Dano por contato e por projéteis, com invulnerabilidade breve após o hit.
- Prisioneiros dão vida e granadas. Elites podem soltar boost de cadência, e drones podem soltar vida.
- Combo: +0,1 por abate em sequência (sem tomar dano, janela de 3 s). Teto x3 em Fácil e Médio, x4 em Difícil.
- Bônus de tempo ao derrotar o chefe.

## Estrutura

Arquivo único (`index.html`) com CSS e JS embutidos. As fontes vêm do Google Fonts e os gráficos são desenhados por código, então não há dependência de imagens externas que possam quebrar.
