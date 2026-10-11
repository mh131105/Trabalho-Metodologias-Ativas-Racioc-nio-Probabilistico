# Inteligência Artificial — Questão 1

Resolução dos cinco itens da atividade de raciocínio probabilístico sobre o diagnóstico de um farol de bicicleta movido a dínamo. O desenvolvimento utiliza raciocínio causal, tabelas de probabilidades, d-separação e a lei da probabilidade total, com os cálculos apresentados por escrito.

## Resoluções em Markdown

- [Item (a): rede bayesiana causal](questao-1/item-a.md)
- [Item (b): tabelas de probabilidades](questao-1/item-b.md)
- [Item (c): valores plausíveis](questao-1/item-c.md)
- [Item (d): ausência da aresta entre a rua e a luz](questao-1/item-d.md)
- [Item (e): cálculo da probabilidade de tensão com neve](questao-1/item-e.md)

## Documento consolidado

- [PDF com a resolução completa](output/pdf/resolucao-questao-1.pdf)
- [Fonte LaTeX do PDF](resolucao-questao-1.tex)

Os oito valores da CPT de `Li` foram preservados conforme a tabela presente no PDF do enunciado. As demais probabilidades são escolhas ilustrativas explicitadas no item (c). Para esses valores, o item (e) resulta em **P(V = t | Str = snow_covered) = 0,3992 = 39,92%**.

A estrutura adotada segue a interpretação causal do problema e pressupõe independência conjunta dos nós de origem. O texto distingue essa hipótese da independência apenas aos pares informada no enunciado.

Fonte do exercício: *IA-Atividade_Metodologias_Ativas-RaciocinioProb.pdf*, questão 1, disciplina Inteligência Artificial, 2º Trabalho, 11/10/2026, professor Edjard Mota, Universidade Federal do Amazonas.
