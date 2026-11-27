# Site da ACCROC

Site da **ACCR do Outeiro da Cortiçada, IPSS**: Associação Centro de Convívio e Recreio do Outeiro da Cortiçada.

É um site simples (HTML, CSS e um pouco de JavaScript), sem base de dados, alojado gratuitamente no **GitHub Pages**.

## Páginas

| Endereço | Ficheiro | Conteúdo |
|---|---|---|
| `/` | `index.html` | Início: próximos eventos, o que fazemos, notícias e donativos |
| `/associacao/` | `associacao/index.html` | Quem somos, percurso, missão/visão/valores, órgãos sociais, donativos |
| `/a-nossa-terra/` | `a-nossa-terra/index.html` | História da vila, pontos de interesse, como chegar |
| `/centro-de-dia/` | `centro-de-dia/index.html` | Separadores: O Centro de Dia · Documentação · Parcerias |
| `/contactos/` | `contactos/index.html` | Associação (sede) e Centro de Dia, formulário |

Atalhos úteis: `/centro-de-dia/#documentacao` abre logo os relatórios e contas, e `/associacao/#apoiar` abre os donativos.

## Pastas

```
assets/css/site.css      estilos comuns (cabeçalho, menu, telemóvel)
assets/js/site.js        menu, separadores, eventos, notícias, formulário
assets/img/              fotos e brasão (nomes fixos)
documentos/              relatorios-de-contas/, estatutos/ e atas/ (PDF)
data/noticias.json       últimas notícias (geradas a partir do Facebook)
data/eventos.json        próximos eventos (gerados a partir do Facebook)
scripts/facebook.mjs     programa que vai buscar os posts ao Facebook
.github/workflows/       tarefa automática que corre o programa a cada 3 horas
```

## Como mudar uma foto

As fotos têm **nomes fixos**. Para trocar uma, envia-se uma nova com **o mesmo nome** para `assets/img/` (no GitHub: abrir a pasta → *Add file* → *Upload files*).

| Ficheiro | Onde aparece |
|---|---|
| `assets/img/brasao.png` | Brasão no cabeçalho (falta a versão em boa resolução) |
| `assets/img/centro-de-dia-2.jpg` | Fundo do topo das páginas · cartão e foto do Centro de Dia |
| `assets/img/igreja-2.jpg` | Fundo do topo de "A Nossa Terra" |
| `assets/img/igreja-4.jpg` | Foto da secção História |
| `assets/img/igreja.jpg` | Ponto de interesse: Igreja Matriz |
| `assets/img/fonte.jpg` | Ponto de interesse: Fonte de Nossa Senhora da Ribeira |
| `assets/img/parque-merendas.jpg` | Ponto de interesse: Parque de Merendas |
| `assets/img/jardim-da-vila.jpg` | Ponto de interesse: Jardim da Vila |
| `assets/img/lavadouros.jpg` | Ponto de interesse: Lavadouros |
| `assets/img/casa-da-palmeira.jpg` | Ponto de interesse: Casa da Palmeira |
| `assets/img/quinta-da-corticada.jpg` | Ponto de interesse: Quinta da Cortiçada |
| `assets/img/junta.jpg` | Ponto de interesse: Junta de Freguesia |
| `assets/img/atletismo.jpg` | Página inicial, cartão Cultura e Desporto (foto da CM Rio Maior; crédito na foto) |

Também guardadas, para usar mais tarde: `quinta-da-corticada-2.jpg`, `igreja-3.jpg`, `jardim-da-vila-2.jpg`, `jardim-da-vila-3.jpg`, `lavadouros-2.jpg`, `junta-no-natal.jpg`.
Os nomes seguem os da pasta de fotos, em minúsculas e sem espaços (ex.: "Igreja 2.jpg" → `igreja-2.jpg`).

Os quadrados azul-claros com texto entre [parênteses retos] são lugares para fotos e textos ainda por pôr.

## Notícias e eventos (a partir do Facebook)

A associação publica só no Facebook (https://www.facebook.com/accrouteirodacorticadaipss) e o site atualiza-se sozinho.

- **Notícias:** os 3 últimos posts aparecem na página inicial.
- **Eventos:** os posts com cartaz, `#ACCROC` e uma linha `Data:` aparecem no cartão "Próximos eventos". Saem sozinhos quando a data passa.

Regra para um evento aparecer no site:

```
Festas da Aldeia 2027          ← 1.ª linha: nome do evento
Data: 20/06/2027               ← obrigatório (dia/mês/ano)
Local: Largo da aldeia         ← opcional
Venham todos! #ACCROC          ← obrigatório: #ACCROC
```
(e o **cartaz** como foto do post)

Um post com `#ACCROC` mas **sem** a linha `Data:` aparece como notícia normal, por isso pode usar-se `#ACCROC` em todos os posts.

### Ligar ao Facebook (feito uma vez, por um administrador da página)

1. Criar uma app gratuita em https://developers.facebook.com e gerar uma **chave de página** (*Page access token*) com a permissão `pages_read_engagement`. Uma chave de página obtida a partir de uma chave de utilizador de longa duração não expira.
2. No GitHub: **Settings → Secrets and variables → Actions → New repository secret**, e criar:
   - `FB_PAGE_ID`: o ID numérico da página de Facebook
   - `FB_PAGE_TOKEN`: a chave de página
3. Em **Actions → "Atualizar do Facebook" → Run workflow**, correr a primeira vez à mão.

Sem estes dois segredos a tarefa não faz nada, e o site continua a mostrar os exemplos.

## Publicar (GitHub Pages)

**Settings → Pages → Build and deployment → Source: "Deploy from a branch" → Branch: `main` / `(root)` → Save.**

Ao fim de 1 a 2 minutos, o site fica em `https://agostinho1998.github.io/ACCROC/`.

### Domínio próprio (mais tarde)

Quando o `accroc.eu.org` for aprovado (ou se se comprar um `.pt`):
1. **Settings → Pages → Custom domain** → escrever o domínio → Save.
2. No DNS do domínio, criar um registo `CNAME` de `www` para `agostinho1998.github.io`. Para o domínio sem `www`, criar os registos `A` indicados na documentação do GitHub Pages.
3. Ativar **Enforce HTTPS**.

## Novos relatórios e contas

Para publicar um relatório novo: pôr o PDF em `documentos/relatorios-de-contas/` com o nome `AAAA-relatorio-de-contas.pdf` (e `AAAA-anexo-demonstracoes-financeiras.pdf`) e acrescentar o link em `centro-de-dia/index.html`, no separador Documentação. O Claude pode tratar disto.

## Por fazer

- [ ] Fotos e brasão em boa resolução
- [ ] Textos entre [parênteses retos]: utentes, inscrição, descrições dos pontos de interesse, órgãos sociais
- [ ] Relatórios e contas 2023–2025
- [x] Copiar os PDF dos relatórios do Wix para o site (`documentos/`)
- [ ] Ligar ao Facebook (secção acima)
- [ ] Confirmar o IBAN com a tesouraria
