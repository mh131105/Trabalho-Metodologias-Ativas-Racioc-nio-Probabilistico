# Questão 1 — Item (c): valores plausíveis

A rede adotada é $Str\to R\leftarrow Flw$, $R\to V$, $V\to Li$, $B\to Li$ e $K\to Li$, com os nós de origem conjuntamente independentes. A CPT de $Li$ é preservada conforme o enunciado.

## Distribuições a priori

| $Str$ | $P(Str)$ |
|---|---:|
| `dry` | $0{,}60$ |
| `wet` | $0{,}30$ |
| `snow_covered` | $0{,}10$ |

$$
0{,}60+0{,}30+0{,}10=1.
$$

Escolhemos um cenário em que ruas secas são mais frequentes que ruas molhadas e ruas com neve. Essas frequências são hipotéticas e não descrevem o clima de uma cidade específica.

| Nó | $P(t)$ | $P(f)$ |
|---|---:|---:|
| $Flw$ | $0{,}20$ | $0{,}80$ |
| $B$ | $0{,}95$ | $0{,}05$ |
| $K$ | $0{,}98$ | $0{,}02$ |

Assim, há 20% de probabilidade de desgaste do volante, 95% de a lâmpada estar em boas condições e 98% de o cabo estar em boas condições.

## CPT de $R$

| $Str$ | $Flw$ | $P(R=t\mid Str,Flw)$ | $P(R=f\mid Str,Flw)$ |
|---|---|---:|---:|
| `dry` | $f$ | $0{,}02$ | $0{,}98$ |
| `dry` | $t$ | $0{,}10$ | $0{,}90$ |
| `wet` | $f$ | $0{,}20$ | $0{,}80$ |
| `wet` | $t$ | $0{,}50$ | $0{,}50$ |
| `snow_covered` | $f$ | $0{,}60$ | $0{,}40$ |
| `snow_covered` | $t$ | $0{,}90$ | $0{,}10$ |

Para um volante sem desgaste, o risco de deslizamento aumenta de $0{,}02$ para $0{,}20$ e depois para $0{,}60$ ao passar de rua seca para molhada e com neve. Para um volante desgastado, aumenta de $0{,}10$ para $0{,}50$ e depois para $0{,}90$. Em cada condição de rua, o desgaste aumenta a probabilidade de deslizamento.

## CPT de $V$

| $R$ | $P(V=t\mid R)$ | $P(V=f\mid R)$ |
|---|---:|---:|
| $f$ | $0{,}98$ | $0{,}02$ |
| $t$ | $0{,}10$ | $0{,}90$ |

Sem deslizamento, o dínamo apresenta tensão com probabilidade de 98%. Com deslizamento, essa probabilidade cai para 10%. Não a fixamos em zero porque pode haver contato residual ou deslizamento parcial.

## CPT de $Li$: valores do enunciado

| $V$ | $B$ | $K$ | $P(Li=t\mid V,B,K)$ | $P(Li=f\mid V,B,K)$ |
|---|---|---|---:|---:|
| $t$ | $t$ | $t$ | $0{,}99$ | $0{,}01$ |
| $t$ | $t$ | $f$ | $0{,}01$ | $0{,}99$ |
| $t$ | $f$ | $t$ | $0{,}01$ | $0{,}99$ |
| $t$ | $f$ | $f$ | $0{,}001$ | $0{,}999$ |
| $f$ | $t$ | $t$ | $0{,}30$ | $0{,}70$ |
| $f$ | $t$ | $f$ | $0{,}005$ | $0{,}995$ |
| $f$ | $f$ | $t$ | $0{,}005$ | $0{,}995$ |
| $f$ | $f$ | $f$ | $0$ | $1$ |

Os valores não nulos com $V=f$ pertencem à tabela fornecida e não foram substituídos por um modelo determinístico de circuito.

## Normalização e coerência

Todas as probabilidades estão no intervalo $[0,1]$. Em cada linha booleana, a probabilidade de $f$ é o complemento da probabilidade de $t$; por exemplo,

$$
P(R=f\mid Str=snow\_covered,Flw=t)=1-0{,}90=0{,}10,
$$

$$
P(Li=f\mid V=t,B=f,K=f)=1-0{,}001=0{,}999.
$$

A independência conjunta das origens garante que as probabilidades de $B$ e $K$ não dependam de $R$ ou de $V$. As CPTs de $V$ e de $Li$ também respeitam as independências condicionais indicadas: $V$ depende apenas de $R$, e o efeito de $R$ sobre $Li$ passa por $V$.

**Resposta:** as seis distribuições faltantes ficam numericamente especificadas, e a sétima permanece igual à do enunciado. São esses valores que serão usados no [item (e)](item-e.md).
