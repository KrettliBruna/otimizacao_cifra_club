# Regras de Formatação de Nomes de Aulas

Este documento define dois padrões de conversão de nomes de aulas, usados no fluxo de trabalho de pré-produção do Bru (Cifra Club). Basta dizer "OPCAO TP" ou "OPCAO FLUXO" que o Claude deve aplicar a regra correspondente, sem precisar reexplicar.

---

## OPCAO TP

**Quando usar:** transformar os nomes das aulas em nomes de arquivo para o Teleprompter.

**Regra:**
- Minúsculas
- Sem acentos, cedilha ou pontuação
- Espaços, hífens e pontos extras viram underscore (`_`)
- Mantém o número da aula no início
- Extensão final: `.tpp`
- Não pode mudar nenhuma palavra do conteúdo original

**Padrão:** `X.X_xxxxxx_xxx_xxxxxx_xx_xxxxxx.tpp`

**Exemplo:**
- Original: `Aula 2.6. Aplicando os intervalos em melodias`
- Convertido: `2.6_aplicando_os_intervalos_em_melodias.tpp`

---

## OPCAO FLUXO

**Quando usar:** gerar uma lista dos nomes originais das aulas, pronta para copiar e colar no Google Docs mantendo a formatação.

**Regra:**
- Mantém os nomes **originais** das aulas (com acentos, cedilha e pontuação — sem nenhuma conversão)
- Gerar como artifact HTML
- Fonte: Courier New
- Tamanho: 18pt
- Negrito
- Texto centralizado
- O estilo deve ser aplicado individualmente em cada linha (um `<span>` por linha), não só no `<div>` pai — isso garante que a formatação não se perca ao copiar e colar no Google Docs

**Exemplo de estrutura HTML por linha:**
```html
<span style="font-family: 'Courier New', Courier, monospace; font-size: 18pt; font-weight: bold;">Aula 2.6. Aplicando os intervalos em melodias</span><br>
```
