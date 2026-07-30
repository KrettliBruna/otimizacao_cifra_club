# Pré-produção Cifra Club

Ferramenta para gerar o arquivo `.rtf` usado no Teleprompter Pro, a partir do roteiro das aulas.

## Arquivos

- **gerador-rtf-tp.html** — abra este arquivo em qualquer navegador (funciona offline, sem instalar nada). Cole o roteiro já organizado por cena (LOC 01, ACORDES 01...) e gere o `.rtf` pronto pra usar no botão **Load** do Teleprompter Pro.
- **regras_opcao_tp_e_fluxo.md** — regras de nomeação de arquivos (OPCAO TP e OPCAO FLUXO) usadas no fluxo de pré-produção.

## Como usar

1. Baixe/abra o `gerador-rtf-tp.html` (duplo clique abre no navegador padrão).
2. Cole o roteiro no campo de texto, com cada cena em uma linha (ex: `LOC 01`) e o texto embaixo.
3. Clique em **Processar roteiro**.
4. Confira a prévia.
5. Clique em **Baixar .rtf** e carregue no Teleprompter Pro pelo botão **Load**.

## Formato esperado do roteiro colado

```
LOC 01
Texto da primeira locução...

ACORDES 01
Bm  F#7
Texto da fala dos acordes...

LOC 02
Texto da segunda locução...
```

Só cenas **LOC** e **ACORDES** entram no `.rtf`. As demais (TOCA, RITMO, DEDIL, TAB) podem aparecer sem texto, só para compor a lista de cenas do fluxograma.

## Atualizando entre computadores

Quando editar a ferramenta em um PC e quiser levar a versão atualizada para o outro:

1. No repositório do GitHub, clique em **Add file → Upload files**.
2. Arraste o arquivo atualizado (substitui o antigo).
3. No outro PC, baixe o ZIP atualizado (**Code → Download ZIP**) ou copie o arquivo direto da página do GitHub.
