# Questão 1 — Item (d): ausência de aresta entre `Str` e `Li`

**Pedido:** mostrar que a rede não contém uma aresta entre a condição da rua e a luz ligada.

## Caminho causal existente

Na rede adotada, a condição da rua altera a probabilidade de deslizamento, que altera a geração de tensão, que influencia a luz:

$$
Str\longrightarrow R\longrightarrow V\longrightarrow Li.
$$

Portanto, há um efeito **indireto**. Os pais de $Li$ são exatamente $V$, $B$ e $K$, como também indica a CPT fornecida no enunciado. A rua não é um pai da luz.

## Justificativa por d-separação

O único caminho entre $Str$ e $Li$ passa por $R$ e $V$. Ao condicionar em $V$, um nó não colisor nesse caminho, bloqueamos o caminho. Pela propriedade de d-separação da rede,

$$
Str\perp Li\mid V.
$$

Mesmo quando a lâmpada e o cabo também são conhecidos,

$$
P(Li\mid Str,V,B,K)=P(Li\mid V,B,K).
$$

Conhecidos os pais da luz, informar a condição da rua não muda sua probabilidade. A condição $P(Li\mid V,R)=P(Li\mid V)$ do enunciado também é compatível com essa mediação: ao conhecer a tensão, saber se o dínamo desliza não acrescenta informação sobre a luz.

## Verificação pela fatoração

Escreva $s$, $v$, $b$ e $k$ para valores fixados de $Str$, $V$, $B$ e $K$. Na fatoração da rede, o único fator que envolve $Li$ é $P(Li\mid v,b,k)$. Ao somar os estados não observados de $Flw$ e $R$ e normalizar, esse fator pode sair da soma, resultando em

$$
P(Li\mid s,v,b,k)=P(Li\mid v,b,k).
$$

Se $B$ e $K$ não forem observados, a independência conjunta das origens permite marginalizar:

$$
P(Li\mid V=v,Str=s)
=\sum_{b\in\{t,f\}}\sum_{k\in\{t,f\}}
P(Li\mid v,b,k)P(B=b)P(K=k).
$$

O lado direito não depende de $s$ e é igual a $P(Li\mid V=v)$.

## Conclusão

Na estrutura causal escolhida, toda influência da rua sobre a luz é transmitida por $R$ e $V$. Assim, **não há aresta direta $Str\to Li$**. Também não há aresta inversa $Li\to Str$, pois o estado da luz não causa a condição da rua.

A ausência da aresta não significa que $Str$ e $Li$ sejam independentes sem condicionamento: o caminho indireto continua ativo quando $V$ não é observado. A conclusão refere-se à rede causal adotada; as independências fornecidas, isoladamente, não demonstram que ela seja a única estrutura possível.
