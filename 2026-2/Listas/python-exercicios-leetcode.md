# Exercícios de LeetCode

O objetivo desta lista não é necessariamente resolver os problemas da forma mais eficiente ou elegante possível. O objetivo é ganhar familiaridade com a sintaxe e o funcionamento do Python: manipulação de listas, strings, dicionários, laços, recursão e as estruturas de controle da linguagem. Use os problemas como pretexto para escrever e testar código Python.

**Não use IA de forma nenhuma para resolver os exercícios.** Nem para gerar a solução, nem para revisar, nem para dar dicas de implementação. O aprendizado da sintaxe só acontece se o código sair da sua cabeça.

---

## 1. Find the Index of the First Occurrence in a String

https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/description/

Técnica: busca em string por força bruta (varredura com dois índices). Se quiser ir além, é o problema clássico de introdução ao algoritmo KMP (Knuth-Morris-Pratt), mas não é necessário para resolver o exercício.

Built-ins relevantes (para referência, não para resolver diretamente):
- `str.find`: https://docs.python.org/3/library/stdtypes.html#str.find

## 2. Two Sum

https://leetcode.com/problems/two-sum/description/

Técnica: tabela hash (dicionário) para busca em O(1) do complemento de cada elemento.

Built-ins relevantes:
- `dict`: https://docs.python.org/3/library/stdtypes.html#dict
- `enumerate`: https://docs.python.org/3/library/functions.html#enumerate

## 3. Longest Substring Without Repeating Characters

https://leetcode.com/problems/longest-substring-without-repeating-characters/description/

Técnica: janela deslizante (sliding window) com um conjunto ou dicionário para controlar os caracteres já vistos na janela atual.

Built-ins relevantes:
- `set`: https://docs.python.org/3/library/stdtypes.html#set
- `dict`: https://docs.python.org/3/library/stdtypes.html#dict

## 4. Search in Rotated Sorted Array

https://leetcode.com/problems/search-in-rotated-sorted-array/description/

Técnica: busca binária adaptada. Em cada passo é preciso decidir qual metade do vetor está ordenada para saber onde continuar a busca.

## 5. Valid Sudoku

https://leetcode.com/problems/valid-sudoku/description/

Técnica: verificação com conjuntos (um por linha, um por coluna, um por bloco 3x3) para detectar repetição.

Built-ins relevantes:
- `set`: https://docs.python.org/3/library/stdtypes.html#set
- `collections.defaultdict`: https://docs.python.org/3/library/collections.html#collections.defaultdict

## 6. Rotate Image

https://leetcode.com/problems/rotate-image/description/

Técnica: manipulação de matriz in-place, normalmente via transposição seguida de espelhamento de linhas (ou de colunas).

Built-ins relevantes:
- `zip`: https://docs.python.org/3/library/functions.html#zip (útil para transposição, `zip(*matriz)`)
- fatiamento de listas (`lista[::-1]`): https://docs.python.org/3/library/stdtypes.html#sequence-types-list-tuple-range

## 7. Edit Distance

https://leetcode.com/problems/edit-distance/description/

Técnica: programação dinâmica. É o problema clássico da distância de Levenshtein, com tabela bidimensional indexada pelos prefixos das duas strings.

Built-ins relevantes:
- `functools.lru_cache`, caso opte por uma versão recursiva com memoização: https://docs.python.org/3/library/functools.html#functools.lru_cache

## 8. Remove Duplicates from Sorted Array II

https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/description/

Técnica: dois ponteiros, um de leitura e um de escrita, aproveitando que o vetor já está ordenado.

## 9. Permutations

https://leetcode.com/problems/permutations/description/

Técnica: backtracking. Construir a permutação incrementalmente, marcando elementos usados e desfazendo a escolha ao retroceder.

Built-ins relevantes (use apenas para conferir sua resposta, não para resolver):
- `itertools.permutations`: https://docs.python.org/3/library/itertools.html#itertools.permutations

## 10. Combinations

https://leetcode.com/problems/combinations/description/

Técnica: backtracking, similar ao de Permutations, mas controlando um índice de início para evitar combinações repetidas.

Built-ins relevantes (use apenas para conferir sua resposta, não para resolver):
- `itertools.combinations`: https://docs.python.org/3/library/itertools.html#itertools.combinations

## 11. Subsets

https://leetcode.com/problems/subsets/description/

Técnica: backtracking (construção incremental do subconjunto) ou, alternativamente, enumeração por máscara de bits sobre os índices do vetor.

Built-ins relevantes (use apenas para conferir sua resposta, não para resolver):
- `itertools.chain` combinado com `itertools.combinations`: https://docs.python.org/3/library/itertools.html#itertools.chain
