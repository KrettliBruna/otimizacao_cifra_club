# Pré e Pós-produção · Cifra Club

Ferramenta única, em um arquivo HTML, que cobre três tarefas do fluxo de aulas:

1. **Roteiro & TP** — monta o roteiro por cena, gera o `.tpp` do Teleprompter Pro e a lista de cenas do fluxograma
2. **Conversão do XML** — reescreve o XML do DaVinci para o Premiere
3. **Organização da pasta da aula** — distribui os arquivos nas subpastas certas

Abre no navegador, sem instalar nada. As partes 2 e 3 precisam do **Chrome ou Edge** e da página aberta **pelo link do site** (a permissão de pasta não funciona com o arquivo solto).

---

## Aba 1 · Roteiro & TP

### Montando o roteiro

Cada cena começa com um rótulo em linha própria, e o texto vem embaixo:

```
LOC 01
Texto da primeira locução...

ACORDES 01
Bm  F#7
Texto da fala dos acordes...
```

**Botões de cena** — LOC, ACORDES, RITMO, DEDIL, TAB, TOCA, TOCA SOLO. Cada clique insere o rótulo já numerado na posição do cursor, continuando a contagem daquele tipo.

**Desfazer** (`Ctrl+Z`) e **Refazer** (`Ctrl+Y`) — voltam qualquer alteração, inclusive um Limpar feito sem querer.

**Renumerar** — conserta a sequência quando fica torta. Mexe só nos rótulos, nunca no texto.

### Conferência automática

Ao processar, a página compara o texto colado com o texto que foi parar no arquivo do TP e mostra as duas contagens. Se não bater, ela avisa em vermelho — não use o arquivo nesse caso.

Ela também alerta quando há texto **antes da primeira cena**, que não entra em lugar nenhum, e quando há fala em cenas que não vão pro Teleprompter.

### O que sai

**Arquivo do TP (.tpp)** — só as cenas LOC e ACORDES, com as LOCs primeiro. Cada rótulo marcado como `<> LOC 01`. Os pontinhos das pontas são o respiro de rolagem, ajustável no campo **Pontos**.

**Lista de cenas** — todas as cenas, na ordem `LOC → ACORDES → RITMO → DEDIL → TAB → TOCA → TOCA SOLO`, com linha em branco entre os grupos.

A lista sai em **duas colunas de 14 linhas**, no formato da tabela do documento: preenche a primeira coluna de cima a baixo e continua na segunda, que sempre começa numa cena — se a virada cair numa linha de separação, ela é descartada. Cada coluna tem seu próprio botão de copiar, para você colar uma de cada vez. Se as cenas passarem de 28 linhas, a página avisa em vermelho quantas sobraram.

A cópia já vai formatada: fundo `#efefef`, Courier New 11, borda fina preta, centralizado.

### Nomes dos arquivos

Preenchendo o nome da aula, a página monta os dois nomes do padrão:

- **Nome pro TP e pro Fluxo** — `Aula 2.6. Aplicando os intervalos` vira `2.6_aplicando_os_intervalos`
- **Nome pro Fluxo** — a aula como você digitou

O `.tpp` baixado usa o primeiro, com a terminação acrescentada. O conteúdo é RTF por dentro — só o nome termina em `.tpp`, que é o que o Teleprompter Pro espera.

---

### Salvar o .tpp direto numa pasta

O botão **Salvar na pasta…** grava o arquivo do TP sem passar por Downloads. Na primeira vez ele pergunta onde; depois disso a pasta escolhida fica em uso e aparece o nome dela ao lado.

Para mudar de destino há dois caminhos: o botão **Trocar pasta**, que abre a escolha na hora, e o botão **Limpar**, que solta a pasta — assim a próxima aula começa perguntando de novo.

## Aba 2 · Pasta da aula

O DaVinci já cria a pasta da aula e a `Assets`. O resto acontece aqui.

**1 · Escolher pasta da aula** — aponte para a pasta que o DaVinci criou. A permissão fica lembrada; o Chrome pede uma confirmação rápida a cada nova sessão.

**2 · Arraste os arquivos:**

| Quadro | Destino |
|---|---|
| XML do DaVinci | convertido, em `premiere/` |
| Projeto de áudio | conteúdo da pasta, em `sonar/` |
| Fluxo (iCloud) | raiz da pasta, renomeado para `fluxo` |

As subpastas nascem sozinhas. Aceita arquivos soltos ou pastas inteiras, inclusive arrastadas direto da rede.

**Áudio exportado é automático.** Ao soltar o projeto de áudio, a página procura dentro de `sonar/` uma pasta com "audio" e "export" no nome e copia os arquivos de dentro dela, soltos, para `Assets/`. O botão **Procurar áudio export** roda essa busca manualmente, se precisar.

**Fila automática** — cópias de pasta pesada rodam uma de cada vez. Vocé pode soltar o projeto de áudio de várias aulas seguidas: as demais ficam marcadas como *na fila* e começam sozinhas quando a anterior termina, cada uma na velocidade cheia. Disco e rede não ficam mais rápidos com cópias simultâneas — ficam mais lentos —, por isso a fila. XML e fluxo, que são arquivos únicos, não esperam a fila.

**Painel de etapas** — cada aula vira um cartão com as quatro etapas do processo (`premiere`, `sonar`, `Assets`, `fluxo`) e o estado de cada uma: pendente, em andamento com a contagem de arquivos, concluída ou com erro. As aulas ficam lado a lado, e o histórico guarda as seis últimas.

**Várias aulas ao mesmo tempo** — cada tarefa fica presa à pasta que estava escolhida quando você soltou o arquivo. Pode trocar de aula enquanto uma cópia grande ainda roda: ela continua até o fim, no lugar certo, inclusive a busca automática do áudio exportado. O contador ao lado dos botões mostra quantas cópias estão em andamento, e cada linha do histórico diz de qual aula veio.

**Verificação de cópia** — depois de gravar cada arquivo, a página confere se o tamanho bate com o original. Se não bater, ela para e diz qual arquivo saiu incompleto.

### O que a conversão do XML faz

Reescreve o arquivo para o Premiere procurar os vídeos pelo nome que está na timeline do DaVinci (LOC…, RITMO…, TOCA…), acrescentando `.mov`. Também zera o timecode da sequência e corrige `anamorphic`, `fielddominance` e os filtros de motion. O resultado sai com `_corrigido` no fim do nome; o XML original nunca é alterado.

---

## Manutenção

O repositório é o backup da versão boa. Para atualizar: **Add file → Upload files**, arraste o arquivo com o mesmo nome, **Commit changes**. O site atualiza sozinho em cerca de um minuto — use `Ctrl+F5` ao abrir para não ver a versão guardada em cache.
