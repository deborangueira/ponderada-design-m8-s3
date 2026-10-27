# Ponderada de design M8 · S3: planejamento

> **Status (27/10/2026):** só o escopo foi combinado. A execução fica para depois da aula de sexta-feira, quando sai o slide da S3. O slide deve ser revisado antes de começar, porque pode mudar o escopo, como aconteceu na S2.

## Enunciado (resumo)

**Objetivo.** Projetar uma funcionalidade de IA que continue útil quando a IA erra, quando não tem certeza ou quando o serviço está fora do ar.

**Atividade.**

1. Escolher um atrito real da jornada do grupo e justificar por que IA resolve melhor que uma regra fixa.
2. Montar a matriz de estados: sucesso, incerteza, erro da IA, falha parcial e serviço indisponível. Cada estado de falha deve vir de um cenário de exceção da simulação ou do ATAM.
3. Prototipar uma tela por estado, mostrando o que o servidor vê, o que pode fazer e como conclui a tarefa sem a IA.
4. Marcar nas telas as diretrizes de interação humano-IA (Amershi et al., 2019): fonte, correção, reversão e controle humano.
5. Descrever as salvaguardas: quem responde pela decisão, o que fica registrado e quais dados a IA não pode usar (LGPD).

**Entrega.** PDF com justificativa, matriz, telas (Figma) e salvaguardas, mais a declaração de uso de IA.

**Nota zero se faltar:** os 5 estados, cada um com tela, e a funcionalidade situada na jornada do e-Cidade.

| Critério | Peso |
|---|:-:|
| Pertinência da IA (atrito real e comparação com alternativa sem IA) | 2,0 |
| Matriz de estados (5 ou mais, cada falha ligada a um cenário de exceção) | 3,0 |
| Protótipo dos estados (incerteza que diz o que conferir, correção, reversão, tarefa concluível sem IA, diretrizes visíveis) | 3,5 |
| Salvaguardas (responsabilização, registro e LGPD) | 1,5 |

## Decisões já tomadas

- **Jornada:** cadastro de exame laboratorial, a mesma da S2. A parte "fiscal" do enunciado é ignorada, como na S2. Ponte possível: o procedimento SIGTAP define o valor SUS e o faturamento (BPA).
- **Atrito:** sugestão por IA do **procedimento SIGTAP** do exame. Fica na etapa 5 do blueprint da S2 (cruzamento X1).
  - **Por que IA e não regra:** a descrição do laboratório ("HEMOGRAMA") não bate com o texto oficial do SIGTAP, que tem milhares de procedimentos e muda a cada competência mensal. A busca exata atual falha, e uma regra de/para precisaria ser mantida à mão.
  - **Por que não a prontidão da S2:** ela é uma regra fixa, e IA ali seria pior.

## Ideias para a execução

**Estados**

| Estado | Ideia de tela |
|---|---|
| Sucesso | Sugestão com fonte (texto oficial, código e competência SIGTAP) |
| Incerteza | Dois candidatos próximos, com o que conferir |
| Erro da IA | Procedimento errado, com correção e reversão |
| Falha parcial | SIGTAP desatualizado ou procedimento desativado (CS-06) |
| Indisponível | Volta para a busca manual atual |

**Cenários de exceção disponíveis no projeto do grupo**

- Simulação CS-04 a CS-07 (`g03/docs/Projeto.md` §4.2.1): ativação incompleta, setor removido, procedimento desativado e laboratório incompatível.
- Limitações do ATAM (§5.2.2 a §5.2.4).
- A §8.2 (EX-01…) ainda está vazia. Combinar com o grupo para usar os mesmos IDs.

**LGPD.** O cadastro de exame não usa dado de paciente. A IA não pode usar resultados nem requisições.
