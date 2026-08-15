# Calculadora ICMS-ST – Material de Construção (Decreto nº 31.270/2013 – SEFAZ-CE)

Ferramenta HTML de página única (sem dependências externas, sem build) para calcular o ICMS por Substituição Tributária com carga líquida nas operações com material de construção, ferragens e ferramentas no Ceará, conforme o Decreto nº 31.270/2013 e alterações — atualizada com a redação dada pelo Decreto nº 35.807/2023.

**Repositório:** [github.com/silvioalbqrq/dec-31270-2013](https://github.com/silvioalbqrq/dec-31270-2013)
**Site publicado:** https://silvioalbqrq.github.io/dec-31270-2013/

## O que a calculadora faz

Três abas:

1. **Atacadista / Varejista (Art. 3º)** — calcula o ICMS-ST devido pelo estabelecimento atacadista ou varejista sobre o valor do documento fiscal, aplicando MVA (padrão 35%, ou 50% em transferências) e o percentual de carga líquida do Anexo III, conforme:
   - Tipo de contribuinte (atacadista/varejista)
   - Origem da mercadoria (próprio Estado/exterior, Norte-NE-CO-ES, Sul-SE exceto ES)
   - Faixa de carga tributária efetiva do produto (7%, 9,72%, 12%, 20%, 25%, 28%)
   - Adicional para remetente optante pelo Simples Nacional (Art. 3º, §2º): +3% (interno), +4% (Sul/SE) ou +6% (Norte/NE/CO/ES)

2. **Indústria / Fabricante (Art. 2º e 2º-A)** — calcula o ICMS-ST retido pelo estabelecimento industrial em operações internas:
   - Geral (material de construção, ferragens e ferramentas): carga líquida de 7,64% sobre valor da operação + MVA 45%
   - Cerâmica/barro cozido (CNAEs 2342-7/02 e 2349-4/99): carga líquida de 4,49% + MVA 45%
   - Ajuste proporcional automático (Art. 2º-B) quando a alíquota efetiva do produto for diferente de 20%

3. **Tabela Anexo III** — tabela de referência estática com os percentuais de carga líquida da ST por tipo de contribuinte, faixa de mercadoria e origem, mais notas explicativas.

## Base legal e atualização dos percentuais

Os percentuais do Anexo III foram conferidos em **15/08/2026** contra o texto consolidado do Decreto nº 31.270/2013, na redação dada pelo **Decreto nº 35.807/2023** (que alinhou o Anexo III à alíquota interna geral de 20% do ICMS-CE, em vigor desde 2024). A faixa antiga de 18% foi removida da calculadora, pois não existe mais na legislação vigente — restou apenas a faixa de 20%.

| Item | Situação |
|---|---|
| Faixas 7%, 12% e 20% (atacadista e varejista) | Atualizadas para os valores vigentes do Decreto 35.807/2023 |
| Faixas 9,72%, 25% e 28% | Já estavam corretas (sem alteração desde a redação original) |
| Indústria geral (7,64%) e cerâmica (4,49%) | Confirmadas como vigentes, sem alteração |
| Ajuste proporcional (referência 20%) | Confirmado conforme Art. 2º-B / §6º do Art. 1º |

## O que a calculadora **não** cobre

- **FECOP** (Fundo Estadual de Combate à Pobreza) — incide separadamente (Art. 3º, §1º, II: 2,58% interno / 3% Norte-NE-CO-ES / 3,20% Sul-SE) e **não** está incluído no valor calculado.
- Percentuais diferenciados para entrada interestadual predominante (Art. 1º, §3º) — aplicável a atacadistas com Regime Especial de recolhimento misto.
- Regras de exclusão do regime (Art. 6º): vestuário, joias, eletrônicos/eletrodomésticos/móveis fora do CNAE típico, mercadorias a 25%/28% em certas hipóteses, mercadoria isenta ou já com carga reduzida.
- Regime Especial de Tributação (Art. 5º) com carga ajustada à carga tributária efetiva.

Para esses casos, consulte a legislação vigente e/ou a SEFAZ-CE diretamente.

## Proteção de código-fonte

O site inclui bloqueio de:
- Menu de contexto (clique-direito)
- Atalhos `Ctrl+U` (ver código-fonte), `Ctrl+S` (salvar página), `F12` e `Ctrl+Shift+I/J/C` (abrir DevTools)
- Detecção simples de DevTools aberto (por variação incomum das dimensões da janela)

**Isso não bloqueia a seleção nem a cópia (`Ctrl+C`) de conteúdo visível** — textos, valores da tabela e resultados de cálculo continuam podendo ser copiados normalmente. A proteção é um dissuasor client-side; não impede 100% um usuário determinado a inspecionar o HTML por outros meios (ex.: extensões de navegador, ferramentas externas).

## Estrutura técnica

- Arquivo único `index.html` (HTML + CSS + JS embutidos, sem dependências externas)
- Sem frameworks, sem build step
- Compatível com qualquer navegador moderno; responsivo (breakpoint em 560px)

## Aviso legal

Esta ferramenta é uma ajuda de cálculo baseada na legislação pública do Decreto nº 31.270/2013 e alterações conhecidas até a data de conferência acima. Não substitui consultoria tributária, Regime Especial, ou a interpretação oficial da SEFAZ-CE. Percentuais podem ser alterados por decretos posteriores — sempre confira a redação vigente.
