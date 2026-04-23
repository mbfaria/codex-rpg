# Codex RPG

Coletânea pessoal de personagens e histórias de RPG de mesa. Cada personagem
vive numa subpasta com seu próprio site estático — a raiz é um hub que
indexa os personagens.

## Personagens

- **[Pierrot](pierrot/)** — Monge do Véu Partilhado (D&D 5e, Monk 10,
  Way of the Open Hand, Haunted One).

## Estrutura

```text
codex-rpg/
├── index.html          # hub — lista de personagens
├── pierrot/            # site do Pierrot
│   ├── index.html
│   ├── styles.css
│   └── assets/
├── README.md
└── .gitignore
```

Cada pasta de personagem é autocontida: HTML, CSS e assets próprios.
Adicionar um personagem novo é só criar `nome-do-personagem/` com seu
`index.html` e linkar a partir do hub.

## Fontes privadas

As fontes brutas de cada personagem (históricos de sessões de criação,
fichas em PDF, notas soltas) são privadas e **não ficam versionadas** —
veja `.gitignore`. Toda a lore dos sites vem dessas fontes, mas elas
em si ficam fora do repositório.

## Ver localmente

Sem build step. Abra `index.html` direto no navegador, ou sirva por HTTP
pra garantir que fontes externas e caminhos relativos funcionem em
todos os navegadores:

```bash
python -m http.server 8080
# depois: http://localhost:8080
```

## Créditos de imagem

Cada site de personagem cita dentro dele as imagens externas que usa
(em geral do [Wikimedia Commons](https://commons.wikimedia.org/), em
domínio público ou sob licença livre).

## Licença

Textos e arte autoral: uso pessoal. Imagens externas: conforme créditos
de cada página.
