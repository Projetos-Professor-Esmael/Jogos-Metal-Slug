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
