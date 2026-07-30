# Metodologia de cálculo do PQC-RI (PQC Readiness Index)

**Versão da planilha:** 2.0
**Data de atualização:** 29 de julho de 2026
**Artigo associado:** "Avaliação Exploratória da Prontidão da Infraestrutura de Rede para Criptografia Pós-Quântica em DNSSEC e TLS na América Latina e Caribe", submetido ao Encom 2026 (XVI Conferência Nacional em Comunicações, Redes e Segurança da Informação).

## Fórmula

PQC-RI = 25 × Σ(i=1 a 7) (w_i × n_i)

Onde:
- **w_i** = peso normalizado do critério i (Σw_i = 1,0)
- **n_i** ∈ [0,4] = nota atribuída à operadora nesse critério, em que 0 representa a pior condição observada e 4 a melhor condição observada entre os oito casos analisados
- A constante 25 converte o resultado da escala [0,4] para a escala [0,100]

## Pesos e critérios (w_i)

| Código | Critério | Peso |
|---|---|---|
| A | RAM mínima do CPE (menor RAM entre os modelos publicamente documentados no parque ativo) | 0,25 |
| B | Heterogeneidade do parque de equipamentos | 0,15 |
| C | Controle de firmware | 0,20 |
| D | Risco de fragmentação UDP (MTU) | 0,15 |
| E | Maturidade institucional/técnica | 0,10 |
| F | Dependência de infraestrutura externa única | 0,05 |
| G | Suporte corporativo/institucional | 0,10 |

Os pesos foram definidos por julgamento especializado dos autores, priorizando critérios diretamente relacionados à capacidade técnica de implantação de PQC (RAM e controle de firmware somam 0,45 do peso total). Representam uma proposta inicial, passível de refinamento futuro por consulta estruturada a especialistas ou técnicas formais de decisão multicritério (ex. AHP).

## Escala de pontuação de cada critério (n_i)

Ver arquivo `pqc-ri-notas-justificativas.csv` para a escala detalhada de cada critério, junto com a nota, fonte e justificativa atribuídas a cada uma das 8 operadoras.

## Regra de arredondamento

Os escores finais (coluna `Score_PQC-RI_0a100_exato` no arquivo `pqc-ri-resultados.csv`) são arredondados para valores inteiros usando arredondamento comercial (0,5 arredonda para cima), disponíveis na coluna `Score_PQC-RI_0a100_arredondado`. Essa decisão reflete o caráter estrutural e exploratório do índice: a precisão de um décimo poderia sugerir um grau de exatidão não compatível com a natureza qualitativa de seis dos sete critérios avaliados (todos exceto RAM mínima, que é diretamente factual).

## Faixas de classificação

Aplicadas sobre o escore arredondado (0 a 100):

| Faixa | Classificação |
|---|---|
| 0–20 | Muito desfavorável |
| 21–40 | Desfavorável |
| 41–60 | Intermediária |
| 61–80 | Favorável |
| 81–100 | Muito favorável |

## Estrutura dos arquivos deste repositório

- `pqc-ri-notas-justificativas.csv`: formato longo, uma linha por combinação operadora × critério (56 linhas), contendo peso, nota, fonte e justificativa textual de como a evidência disponível foi convertida na nota atribuída.
- `pqc-ri-resultados.csv`: uma linha por operadora (8 linhas), com o resultado intermediário (soma ponderada em escala 0-4) e o resultado final (escala 0-100, exato e arredondado).
- `pqc-ri-fontes-equipamentos.csv`: especificações técnicas (CPU, RAM, perfil) e fonte documental (datasheet do fabricante) de cada modelo de equipamento de borda usado na Tabela II do artigo.
- `pqc-ri-metodologia.md`: este documento.

## Limitações declaradas

Este índice é uma avaliação estrutural agregada baseada em inferência técnica fundamentada a partir de fontes públicas, não constituindo medição direta ou experimental da infraestrutura das operadoras analisadas. Ver Seção V (Limitações do Estudo) do artigo para discussão completa.
