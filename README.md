# Pierrot — O Véu que Permanece

Lorebook cinematográfico de página única do personagem **Pierrot**, monge do
Véu Partilhado.

> As fontes brutas (histórico de sessões de criação + ficha D&D 5e) são
> privadas e **não são versionadas** neste repositório — veja `.gitignore`.
> O site é estritamente fiel a essas fontes; nada foi inventado.
> Lacunas identificadas estão listadas dentro do próprio site, na seção
> **Questões em Aberto**.

## Estrutura

```text
PierrotMonk/
??? index.html              Página única com todas as 14 seções narrativas
??? styles.css              Tema dark-monástico cinemático, timeline, responsivo
??? assets/
?   ??? icons/
?   ?   ??? mask-pierrot.svg       Máscara do Caminho do Silêncio
?   ?   ??? mask-arlequina.svg     Máscara do Caminho do Riso
?   ?   ??? mask-colombino.svg     Máscara do Caminho da Palavra
?   ??? images/             (reservado para fallbacks locais)
??? README.md
??? .gitignore
```

## Como visualizar localmente

Não há build step. Basta abrir `index.html` em qualquer navegador moderno.

Se preferir servir via HTTP (recomendado para que as fontes do Google
carreguem corretamente em todos os navegadores):

```bash
# Python 3
python -m http.server 8080
# Depois acesse http://localhost:8080
```

```bash
# Node (com npx)
npx http-server -p 8080
```

## Imagens — créditos

Todas as imagens são do [Wikimedia Commons](https://commons.wikimedia.org/)
e estão em domínio público ou sob licença livre. As referências no HTML usam
o endpoint `Special:FilePath`, que é estável e retorna a versão corrente do
arquivo com redimensionamento automático.

| Uso no site | Arquivo | Autor / data | Licença |
|-------------|---------|--------------|---------|
| Hero        | [`Jean-Antoine_Watteau_-_Pierrot,_dit_autrefois_Gilles.jpg`](https://commons.wikimedia.org/wiki/File:Jean-Antoine_Watteau_-_Pierrot,_dit_autrefois_Gilles.jpg) | Jean-Antoine Watteau, c. 1718-1719 | Domínio público |
| II · Monastério | [`Taktshang.jpg`](https://commons.wikimedia.org/wiki/File:Taktshang.jpg) | Paro Taktsang, Butão | Wikimedia Commons |
| IV · Arlequina | [`SAND_Maurice_Masques_et_bouffons_01.jpg`](https://commons.wikimedia.org/wiki/File:SAND_Maurice_Masques_et_bouffons_01.jpg) | Maurice Sand, *Masques et bouffons*, 1862 | Domínio público |
| IV · Colombino | [`SAND_Maurice_Masques_et_bouffons_03.jpg`](https://commons.wikimedia.org/wiki/File:SAND_Maurice_Masques_et_bouffons_03.jpg) | Maurice Sand, *Masques et bouffons*, 1862 | Domínio público |
| VI · A Partida | [`Ama_Dablam.jpg`](https://commons.wikimedia.org/wiki/File:Ama_Dablam.jpg) | Ama Dablam, Himalaia | Wikimedia Commons |
| VII · A Queda | [`Rievaulx_Abbey_ruins.jpg`](https://commons.wikimedia.org/wiki/File:Rievaulx_Abbey_ruins.jpg) | Ruínas da Abadia de Rievaulx | Wikimedia Commons |
| XI · Reconstrução | [`Thiksey_Monastery.jpg`](https://commons.wikimedia.org/wiki/File:Thiksey_Monastery.jpg) | Mosteiro de Thiksey, Ladakh | Wikimedia Commons |

As três máscaras em SVG (`assets/icons/mask-*.svg`) são autorais e podem ser
livremente editadas.

## Deploy gratuito

### 1. Cloudflare Pages com repositório **privado** (recomendado — mais "escondido")

Mantém o código em um repo privado no GitHub e ainda publica o site gratuitamente
em uma URL pública não indexável facilmente. Ideal para conteúdo pessoal.

```bash
git init
git add .
git commit -m "Pierrot lorebook: estrutura inicial"
git branch -M main
git remote add origin https://github.com/<seu-usuario>/<nome-do-repo>.git
git push -u origin main
```

No GitHub, ao criar o repositório, marque **Private**.

Depois, em <https://dash.cloudflare.com/> → **Workers & Pages** → **Create** →
**Pages** → **Connect to Git**:

1. Autorize o acesso ao repositório privado.
2. Build command: *(vazio)*
3. Build output directory: `/` (raiz)
4. Deploy.

O site ficará em `https://<nome-do-projeto>.pages.dev`. Cada `git push`
regenera automaticamente. Se quiser ainda mais privacidade, é possível
proteger a URL com **Cloudflare Access** (login por e-mail / one-time-pin).

### 2. Netlify com repositório privado

Mesma ideia do Cloudflare Pages, também suporta repos privados no plano free:

1. Em <https://app.netlify.com/> clique em **Add new site → Import an existing project**.
2. Autorize e selecione o repositório privado.
3. Build command vazio, publish directory `/`.
4. Deploy. URL final: `https://<slug>.netlify.app`.

Bônus: é possível proteger o site com senha (plano free tem senha por site
em deploys específicos; senha por ambiente é pago).

### 3. GitHub Pages (só funciona com repositório **público** no plano free)

```bash
git init
git add .
git commit -m "Pierrot lorebook: estrutura inicial"
git branch -M main
git remote add origin https://github.com/<seu-usuario>/<nome-do-repo>.git
git push -u origin main
```

No GitHub: **Settings → Pages → Deploy from a branch**, branch `main`,
pasta `/ (root)`. O site fica em
`https://<seu-usuario>.github.io/<nome-do-repo>/`.

### 4. Netlify Drop (sem Git, só pra testar rápido)

1. Acesse <https://app.netlify.com/drop>.
2. Arraste a pasta inteira do projeto para a área indicada.
3. O site fica online em segundos em uma URL `*.netlify.app`.

## Regras editoriais

- **Fidelidade narrativa total.** Todo texto narrativo vem (parafraseado ou
  literal) da fonte privada; as citações entre aspas são apenas as que
  já existem nela.
- **Nomenclatura consolidada:** *Véu Partilhado* (monastério), *Os do
  Riso / Silêncio / Palavra* (caminhos), *Mão Limpa* (caminho atual de
  Pierrot), *Luvas da Tempestade* (equipamento), *campo anti-entrópico*
  (fenômeno).
- **Criatividade restrita** à apresentação (HTML, CSS, escolha e disposição
  das imagens Wikimedia, microcopy de navegação). Nada de lore nova.
- **Lacunas** são tratadas explicitamente dentro do site (seção *Questões em
  Aberto*), não preenchidas por invenção.
