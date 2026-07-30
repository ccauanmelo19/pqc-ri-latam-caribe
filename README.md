# pqc-ri-latam-caribe

Dados de suporte do artigo "Avaliação Exploratória da Prontidão da Infraestrutura de Rede
para Criptografia Pós-Quântica em DNSSEC e TLS na América Latina e Caribe", submetido ao
Encom 2026 (XVI Conferência Nacional em Comunicações, Redes e Segurança da Informação).

**Autores:** Cauan M. Sousa, Rafael W. Cavalcanti, Mariana B. M. Sabino, Sabrina O. Sousa,
Matheus V. P. Santos, Edmar C. Gurjão, Leocarlos B. S. Lima.

Projeto de pesquisa PIBIC, LABMET/UFCG.

## Conteúdo do repositório

Este repositório disponibiliza os dados completos usados para calcular o índice PQC-RI
(PQC Readiness Index) proposto no artigo, permitindo a reprodução integral dos resultados
apresentados na Tabela III.

- **`pqc-ri-metodologia.md`**: descrição da fórmula do PQC-RI, tabela de pesos por critério,
  regra de arredondamento dos escores finais e versão/data da planilha. Ponto de partida
  recomendado para entender os demais arquivos.

- **`pqc-ri-notas-justificativas.csv`**: formato longo, uma linha por combinação
  operadora × critério (56 linhas no total). Contém o peso e a nota atribuída em cada um
  dos sete critérios, a fonte que fundamenta cada nota, e uma justificativa textual de
  como a evidência disponível foi convertida na nota atribuída.

- **`pqc-ri-resultados.csv`**: uma linha por operadora (8 linhas), com o resultado
  intermediário (soma ponderada em escala 0–4) e o resultado final do PQC-RI em escala
  0–100, tanto no valor exato quanto arredondado para número inteiro, além da
  classificação estrutural correspondente.

- **`pqc-ri-fontes-equipamentos.csv`**: especificações técnicas (CPU, RAM, perfil) e fonte
  documental (datasheet do fabricante) de cada modelo de equipamento de borda usado na
  Tabela II do artigo.

## Como citar

Se utilizar estes dados, cite o artigo correspondente (Encom 2026) e/ou este repositório.
