# Exercícios de LeetCode: pandas

O objetivo desta lista não é necessariamente resolver os problemas da forma mais eficiente ou elegante possível. O objetivo é ganhar familiaridade com a API do pandas: criação e seleção de colunas, filtragem com máscaras booleanas, junções, agrupamentos, agregações, ordenação e operações sobre strings. Use os problemas como pretexto para escrever e testar código com DataFrames.

**Não use IA de forma nenhuma para resolver os exercícios.** Nem para gerar a solução, nem para revisar, nem para dar dicas de implementação. O aprendizado da API só acontece se o código sair da sua cabeça. A documentação oficial é a fonte de consulta permitida:

- Referência da API do pandas: https://pandas.pydata.org/docs/reference/index.html#api

---

## 1. Combine Two Tables (175)

https://leetcode.com/problems/combine-two-tables/description/

Nível: Easy. Categoria: combinação de tabelas.

Técnica: junção à esquerda (left join) entre as tabelas de pessoas e de endereços pela chave `personId`, preservando pessoas sem endereço cadastrado, seguida da seleção apenas das colunas pedidas.

Funções relevantes da API:
- `DataFrame.merge`: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.merge.html
- `DataFrame.drop`: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.drop.html

## 2. Duplicate Emails (182)

https://leetcode.com/problems/duplicate-emails/description/

Nível: Easy. Categoria: consulta.

Técnica: identificar valores repetidos em uma coluna com uma máscara booleana e depois eliminar as repetições do resultado, para que cada email duplicado apareça uma única vez.

Funções relevantes da API:
- `DataFrame.duplicated`: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.duplicated.html
- `DataFrame.drop_duplicates`: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.drop_duplicates.html

## 3. Customer Placing the Largest Number of Orders (586)

https://leetcode.com/problems/customer-placing-the-largest-number-of-orders/description/

Nível: Easy. Categoria: consulta.

Técnica: contagem de frequência por cliente e seleção do cliente com a maior contagem.

Funções relevantes da API:
- `DataFrame.value_counts`: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.value_counts.html

## 4. Swap Sex of Employees (627)

https://leetcode.com/problems/swap-sex-of-employees/description/

Nível: Easy. Categoria: modificação.

Técnica: atualização de uma coluna aplicando uma função elemento a elemento que troca `'m'` por `'f'` e vice-versa, sem criar tabelas intermediárias.

Funções relevantes da API:
- `DataFrame.transform`: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.transform.html

## 5. Average Selling Price (1251)

https://leetcode.com/problems/average-selling-price/description/

Nível: Easy. Categoria: consulta com operação.

Técnica: associar cada venda ao preço vigente na data da compra (a data precisa cair dentro do intervalo `start_date` a `end_date`), calcular a média ponderada do preço pelas unidades vendidas por produto e arredondar para duas casas. Atenção aos produtos sem nenhuma venda, que devem aparecer com média 0.

Funções relevantes da API:
- `DataFrame.itertuples`: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.itertuples.html
- `DataFrame.loc`: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.loc.html#pandas.DataFrame.loc
- `DataFrame.groupby`: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.groupby.html
- `DataFrame.round`: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.round.html

## 6. Nth Highest Salary (177)

https://leetcode.com/problems/nth-highest-salary/description/

Nível: Medium. Categoria: consulta e ordenação.

Técnica: remover salários repetidos, ordenar em ordem decrescente e acessar a N-ésima posição. É preciso tratar o caso em que não existem N salários distintos (ou N inválido), retornando nulo, e respeitar o nome de coluna exigido na saída.

Funções relevantes da API:
- `DataFrame.reset_index`: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.reset_index.html

## 7. Investments in 2016 (585)

https://leetcode.com/problems/investments-in-2016/description/

Nível: Medium. Categoria: consulta, filtro e operação.

Técnica: combinar dois filtros baseados em contagem. O valor de `tiv_2015` precisa se repetir em pelo menos outro registro, e o par (`lat`, `lon`) precisa ser único na tabela. Sobre as linhas que satisfazem as duas condições, soma-se `tiv_2016` e arredonda-se para duas casas.

## 8. Capital Gain/Loss (1393)

https://leetcode.com/problems/capital-gainloss/description/

Nível: Medium. Categoria: operação.

Técnica: transformar cada operação em um valor com sinal (compra negativa, venda positiva) e somar por ação com agrupamento.

## 9. DNA Pattern Recognition (3475)

https://leetcode.com/problems/dna-pattern-recognition/description/

Nível: Medium. Categoria: substring.

Técnica: operações vetorizadas sobre strings (acessor `.str`) para gerar colunas indicadoras a partir de prefixos, sufixos e padrões contidos na sequência, incluindo um padrão de repetição que pede expressão regular.

## 10. Human Traffic of Stadium (601)

https://leetcode.com/problems/human-traffic-of-stadium/description/

Nível: Hard. Categoria: filtro complexo.

Técnica: filtrar as linhas com público de pelo menos 100 e identificar sequências de `id` consecutivos. A diferença entre `id`s sucessivos indica onde uma sequência é quebrada, e a soma acumulada dessas quebras gera um rótulo de grupo para cada sequência. Mantêm-se apenas os grupos com três ou mais linhas.

Funções relevantes da API:
- `DataFrame.diff`: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.diff.html
- `DataFrame.cumsum`: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.cumsum.html
