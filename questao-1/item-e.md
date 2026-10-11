# Questão 1 — Item (e): tensão com a rua coberta de neve

Como $V$ é booleana, vamos calcular a probabilidade de $V=t$ e sua complementar para $V=f$. Abreviamos a evidência $Str=snow\_covered$ por $S$.

## Dados utilizados

Usamos as probabilidades escolhidas no [item (c)](item-c.md):

$$
P(Flw=t)=0{,}20,\qquad P(Flw=f)=0{,}80,
$$

$$
P(R=t\mid S,Flw=t)=0{,}90,\qquad
P(R=t\mid S,Flw=f)=0{,}60,
$$

$$
P(V=t\mid R=t)=0{,}10,\qquad
P(V=t\mid R=f)=0{,}98.
$$

Pela independência entre $Str$ e $Flw$, observar neve não altera a probabilidade de desgaste:

$$
P(Flw=t\mid S)=0{,}20,\qquad P(Flw=f\mid S)=0{,}80.
$$

## 1. Marginalizar o desgaste para obter o deslizamento

Pela lei da probabilidade total, somamos os dois estados de $Flw$:

$$
\begin{aligned}
P(R=t\mid S)
={}&P(R=t\mid S,Flw=t)P(Flw=t\mid S)\\
&+P(R=t\mid S,Flw=f)P(Flw=f\mid S)\\
={}&0{,}90\cdot0{,}20+0{,}60\cdot0{,}80\\
={}&0{,}18+0{,}48\\
={}&0{,}66.
\end{aligned}
$$

Consequentemente,

$$
P(R=f\mid S)=1-0{,}66=0{,}34.
$$

## 2. Marginalizar o deslizamento para obter a tensão

Novamente pela lei da probabilidade total,

$$
P(V=t\mid S)=\sum_{r\in\{t,f\}}P(V=t\mid R=r,S)P(R=r\mid S).
$$

O enunciado fornece $P(V\mid R,Str)=P(V\mid R)$. Portanto, conhecido $R$, podemos retirar a condição sobre a rua do primeiro fator:

$$
\begin{aligned}
P(V=t\mid S)
={}&P(V=t\mid R=t)P(R=t\mid S)\\
&+P(V=t\mid R=f)P(R=f\mid S)\\
={}&0{,}10\cdot0{,}66+0{,}98\cdot0{,}34\\
={}&0{,}066+0{,}3332\\
={}&\boxed{0{,}3992=39{,}92\%}.
\end{aligned}
$$

## 3. Conferência pelos quatro caminhos

A mesma soma pode ser aberta nas quatro combinações de desgaste e deslizamento:

| $Flw$ | $R$ | $P(Flw\mid S)P(R\mid S,Flw)P(V=t\mid R)$ |
|---|---|---:|
| $t$ | $t$ | $0{,}20\cdot0{,}90\cdot0{,}10=0{,}018$ |
| $t$ | $f$ | $0{,}20\cdot0{,}10\cdot0{,}98=0{,}0196$ |
| $f$ | $t$ | $0{,}80\cdot0{,}60\cdot0{,}10=0{,}048$ |
| $f$ | $f$ | $0{,}80\cdot0{,}40\cdot0{,}98=0{,}3136$ |

Logo,

$$
0{,}018+0{,}0196+0{,}048+0{,}3136=0{,}3992.
$$

Essa abertura usa a CPT $P(V\mid R)$ da rede adotada.

## 4. Distribuição final

$$
P(V=f\mid S)=1-0{,}3992=\boxed{0{,}6008=60{,}08\%}.
$$

| Estado de $V$ | $P(V\mid Str=snow\_covered)$ |
|---|---:|
| $t$ — apresenta tensão | $0{,}3992$ ($39{,}92\%$) |
| $f$ — não apresenta tensão | $0{,}6008$ ($60{,}08\%$) |

As probabilidades somam $0{,}3992+0{,}6008=1$. A probabilidade a priori de neve, $P(Str=snow\_covered)=0{,}10$, não multiplica a resposta, pois a rua coberta de neve já é uma condição conhecida. As tabelas de $B$, $K$ e $Li$ também não entram: elas somam 1 ao serem marginalizadas, e não há evidência observada nesses nós.

**Resposta:** com as probabilidades adotadas, o dínamo apresenta tensão em uma rua coberta de neve com probabilidade de **39,92%**. O resultado numérico depende das escolhas livres do item (c).
