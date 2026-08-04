# Gerador de RTF · Teleprompter Cifra Club

Ferramenta de pré-produção que transforma o roteiro da aula em dois entregáveis:

- o arquivo `.tpp` que abre direto no **Teleprompter Pro**
- a **lista de cenas** já formatada para colar no fluxograma

É um arquivo HTML único. Não instala nada, não precisa de internet: dois cliques e abre no navegador.

## Arquivos

| Arquivo | O que é |
|---|---|
| `gerador-tp.html` | A ferramenta. É este que você abre e usa. |
| `README.md` | Este texto. |

## Como usar

1. Abra o `gerador-tp.html` (duplo clique).
2. Monte o roteiro no campo de texto.
3. Preencha o **nome da aula** — ele define o nome do arquivo gerado.
4. Clique em **Processar roteiro**.
5. Na aba **Teleprompter**, confira a prévia e clique em **Baixar .tpp**.
6. Na aba **Fluxograma**, clique em **Copiar lista de cenas** e cole no documento.

## Montando o roteiro

Cada cena começa com um rótulo em linha própria, e o texto vem embaixo:

```
LOC 01
Texto da primeira locução...

ACORDES 01
Bm  F#7
Texto da fala dos acordes...

LOC 02
Texto da segunda locução...
```

### Botões de cena

A barra acima do campo de texto tem um botão para cada tipo: **LOC, ACORDES, RITMO, DEDIL, TAB, TOCA, TOCA SOLO**.

Clique e o rótulo entra já numerado, na posição do cursor. A numeração continua sozinha — primeiro clique em LOC insere `LOC 01`, o seguinte insere `LOC 02`, e assim por diante. O cursor fica na linha de baixo, pronto para você escrever a fala.

### Desfazer, Refazer e Renumerar

- **Desfazer** (ou `Ctrl+Z`) volta qualquer alteração, inclusive um **Limpar** feito sem querer.
- **Refazer** (ou `Ctrl+Y`) reaplica o que foi desfeito.
- **Renumerar** conserta a sequência quando ela fica torta — se você apagar uma cena do meio e sobrar `LOC 01, LOC 03, LOC 04`, ele arruma para `01, 02, 03`. Mexe só nos rótulos, nunca no texto das falas.

## O que vai para cada lugar

**Teleprompter (.tpp)** — só as cenas **LOC** e **ACORDES**, que são as que têm fala. Saem com as LOCs primeiro e as ACORDES depois, cada rótulo marcado como `<> LOC 01` para o Teleprompter reconhecer. Os pontinhos no começo e no fim são o respiro de rolagem; a quantidade é ajustável no campo **Pontos**.

**Fluxograma** — todas as cenas, inclusive as que não têm texto. A lista sai sempre nesta ordem:

```
LOC → ACORDES → RITMO → DEDIL → TAB → TOCA → TOCA SOLO
```

Os tipos que não existirem no roteiro são pulados. Entre um grupo e outro entra uma linha em branco.

A cópia já vai formatada para o documento: fundo `#efefef`, fonte Courier New 11, borda fina preta, texto centralizado. É só colar.

## Nome dos arquivos

Preenchendo o **nome da aula**, a ferramenta monta os dois nomes do padrão de pré-produção:

- **Nome pro TP e pro Fluxo** — minúsculo, sem acento nem pontuação, com underscore no lugar dos espaços, mantendo o número da aula na frente. `Aula 2.6. Aplicando os intervalos` vira `2.6_aplicando_os_intervalos`.
- **Nome pro Fluxo** — o nome da aula como você escreveu.

Cada um tem um botão de copiar ao lado. O arquivo baixado usa esse mesmo nome, com a terminação `.tpp` acrescentada. O botão **Baixar como .rtf** gera o mesmo conteúdo com a terminação antiga, caso precise.

## Levando para outro computador

É um arquivo só, então qualquer caminho serve: pen drive, e-mail, Drive, ou baixando aqui do repositório (abra o `gerador-tp.html` e clique em **Download raw file**).

Sugestões para o dia a dia:

- guarde numa pasta fixa, não em Downloads
- crie um atalho na área de trabalho, ou abra o arquivo e aperte `Ctrl+D` para deixar nos favoritos do navegador

## Atualizando a ferramenta

Este repositório é o backup da versão boa. Depois de alterar o arquivo:

1. No GitHub, clique em **Add file → Upload files**.
2. Arraste o arquivo novo — com o mesmo nome, ele substitui o antigo.
3. **Commit changes**.
4. Copie a versão nova para as outras máquinas.
