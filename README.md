# Espaço Jovem — Loja Salesiana

Site estático (HTML5 + CSS3 + JavaScript puro, sem frameworks) para a vitrine digital da loja jovem salesiana. Funciona apenas abrindo o `index.html` — não precisa de servidor, build ou instalação.

## Estrutura de pastas

```
loja-salesiana/
├── index.html      → todo o conteúdo e estrutura das seções
├── style.css       → identidade visual, cores, layout e responsividade
├── script.js       → menu mobile, animações de scroll e ano do rodapé
├── images/         → todas as fotos de produto já recortadas em PNG transparente
└── README.md       → este arquivo
```

## Como abrir o site

Basta dar duplo clique no arquivo `index.html` (ou arrastar para o navegador). Como é tudo estático, também funciona perfeitamente no GitHub Pages: suba os 4 arquivos/pastas para o repositório e ative o Pages apontando para a branch principal.

## O que já está pronto e preenchido

- **Logo**: aplicada no header (`images/logo-transparente.png`) e no footer (`images/logo-espacojovem-mao.png`), ambas já com fundo transparente.
- **Chaveiros** (R$ 15,00 cada): Dom Bosco, Maria Auxiliadora e Madre Mazzarello — fotos reais recortadas com fundo removido.
- **Copos "Raízes"** (R$ 15,00 cada): rosa, azul claro e azul escuro — fotos reais recortadas com fundo removido.
- **Camisetas** (R$ 60,00 cada): preta, rosa e branca já publicadas com foto real; **3 modelos "em breve" já reservados no grid**, prontos para receber as próximas fotos que você disse que vai enviar.
- **Outros**: os pins de Crocs Dom Bosco e Mazzarello (R$ 20,00 cada) já com foto recortada; os demais itens (caderno, caneca, garrafa, terço, adesivos, boné, brinde) seguem como placeholders ilustrados, à espera de fotos e preços.
- **Vocacional**: botão que leva ao site oficial da Pastoral Vocacional FMA (https://vocacaosalesiana.org.br/fma-sao-paulo/), junto do botão de WhatsApp.
- **Localização**: Inspetoria Nossa Senhora Aparecida — Rua Três Rios, 362, Bom Retiro, São Paulo/SP, com botão "Como chegar" já apontando para o endereço no Google Maps.
- **Redes sociais**: Instagram (@espacojovemfma), Facebook e Spotify já com os links reais, nos três lugares em que aparecem (hero, seção Sobre e footer). O YouTube continua como placeholder (não foi enviado o link).
- **Contato do footer**: e-mail pastoral@fmabap.com.br já aplicado. O telefone continua como placeholder.

## O que ainda falta preencher

Está tudo marcado no `index.html` com comentários `<!-- SUBSTITUA: ... -->`. Os pontos que restam:

### 1. Número de WhatsApp
Todos os botões de compra ainda usam o número de exemplo `https://wa.me/5511999999999?text=...`. Troque `5511999999999` pelo número real da loja (formato `55` + DDD + número, sem espaços) em **todo o arquivo** — é o mesmo número em todos os botões, então um "localizar e substituir" no editor resolve de uma vez.

### 2. As 3 camisetas que faltam
Na seção **Camisas**, há 3 blocos `<article class="product-card placeholder reveal">` já reservados (Modelo 4, 5 e 6). Quando as fotos chegarem:
1. Recorte cada camiseta com fundo removido (mesmo padrão das 3 já publicadas) e salve em `images/` (ex.: `camiseta-modelo4.png`).
2. Copie um bloco das camisetas já prontas (com `<img>`, nome, descrição, preço e link do WhatsApp) e cole no lugar do placeholder correspondente.

### 3. YouTube
Ainda não veio o link do canal. Troque `https://youtube.com/@SEU_CANAL` (aparece na seção Sobre e no footer) assim que tiver.

### 4. Telefone do footer
Troque `(11) 99999-9999` pelo número real de contato (pode ser o mesmo do WhatsApp).

### 5. Produtos restantes de "Outros"
Caderno, caneca, garrafa, terço, adesivos, boné e brinde surpresa ainda estão com ícone ilustrado no lugar de foto, sem preço definido. Quando tiver as fotos e valores, siga o mesmo padrão dos pins de Crocs (imagem recortada + `.product-footer` com preço e botão).

### 6. Mapa da localização
No lugar do bloco `.localizacao-mapa` (hoje mostra "Mapa em breve"), você pode colar um `<iframe>` do Google Maps quando tiver o link de incorporação do endereço.

### 7. Texto da seção Vocacional
O texto foi escrito como inspiração geral sobre discernimento vocacional salesiano — vale revisar e ajustar com as informações oficiais antes de publicar, já que o botão agora linka para o site oficial da Pastoral Vocacional FMA.

## Como adicionar um novo produto (padrão geral)

Em qualquer seção de produtos, copie um bloco `<article class="product-card ...">...</article>` inteiro, cole abaixo do último item da mesma seção e troque:
- a imagem (`<img src="images/...">`) — coloque o arquivo PNG (de preferência com fundo já removido) dentro de `images/`
- o fundo da moldura (`tint-cyan`, `tint-pink`, `tint-lime`, `tint-yellow`, `tint-navy` ou `tint-neutral`, para fotos reais)
- nome, descrição, categoria (`<h3>`, `<p>`, `.product-tag`)
- preço (`.product-price`) e o link do WhatsApp

## Cores e tipografia (para ajustes rápidos)

Todas as cores estão centralizadas no topo do `style.css`, dentro de `:root`:

```css
:root {
  --cyan: #00B7C6;
  --pink: #FF3E86;
  --lime: #AFD91A;
  --yellow: #FFC93C;
  --navy: #16264A;
  --white: #FFFFFF;
  --background: #FAFAF8;
  --radius: 26px;
}
```

Mudar qualquer um desses valores atualiza a cor em todo o site automaticamente. As fontes usadas são **Baloo 2** (títulos) e **Nunito** (textos), carregadas do Google Fonts — gratuitas para uso comercial.

## Sobre as fotos de produto já recortadas

Todas as imagens em `images/` já foram processadas para remover o fundo original (fundo liso dos chaveiros e camisetas, fundo de cortiça dos copos, e o print de tela dos pins de Crocs) e salvas como PNG com transparência. Em alguns recortes mais complexos (copos e pins) pode haver uma pequena imperfeição de borda — se quiser um acabamento 100% perfeito, uma ferramenta de remoção de fundo dedicada (ex. remove.bg) ou um design profissional pode refinar esses recortes específicos.

## Dúvidas comuns

- **O menu mobile não abre com frameworks?** Não, é JavaScript puro (`script.js`), sem dependências.
- **Preciso de banco de dados?** Não, é um site 100% estático — a "vitrine" funciona só com HTML.
- **Posso hospedar no GitHub Pages?** Sim, é exatamente para isso que a estrutura foi pensada.
