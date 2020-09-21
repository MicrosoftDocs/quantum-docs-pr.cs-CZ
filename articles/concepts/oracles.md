---
title: počet, ve kterém se nacházejí Oracle s popisem: Naučte se pracovat s Oracle, operacemi s černým polem, které se používají jako vstup pro jiný algoritmus.
Autor: cgranade UID: Microsoft.. koncepty. Oracle MS. Author: chgranad MS. Date: 07/11/2018 MS. téma: No-Loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---
# <a name="quantum-oracles"></a>Nejenom Oracle

Oracle $ O $ je operace "černého pole", která se používá jako vstup pro jiný algoritmus.
Tyto operace se často definují pomocí klasické funkce $ f: \\ { 0, 1 \\ } ^ n \to \\ { 0, 1 \\ } ^ m, $ která přebírá $ n $ -bit binárního vstupu a vytváří $ $ binární výstup m-bit.
Provedete to tak, že zaberete konkrétní binární vstup $ x = (X_ { 0 } , x_ { 1 } , \dots X_ { n-1 } ) $ .
Qubit je možné označit jako $ \ket { \vec { x } } = \ket { X_ { 0 } } \otimes \ket { X_ { 1 } } \otimes \cdots \otimes \ket { X_ { n-1 } } $ .

Můžeme se nejdřív pokusit o definování $ o $ , aby bylo $ o \ket { × } = \ket { f (x) } $ , ale to má několik problémů.
V prvním $ případě $ může mít jazyk f jinou velikost vstupu a výstupu ( $ n \ne m $ ), takže při použití $ $ hodnoty O by došlo ke změně počtu qubits v registru.
Druhý, i když $ n = m $ , funkce nemusí být inverzi: Pokud $ f (x) = f (y) $ pro určitý $ x \ne y $ , pak $ o \ket { x } = o y, \ket { } $ ale $ o ^ \dagger o \ket { x } \ne o ^ \dagger o \ket { y } $ .
To znamená, že nebudeme moct vytvořit sousedící operaci $ O ^ a \dagger $ Oracle musí mít pro ně definované sousedící.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Definování systému Oracle jeho účinkem na výpočetní bázi – stavy
S oběma uvedenými problémy se můžeme vypořádat tím, že zavedete druhý registr $ m $ qubits a podržíte naši odpověď.
Pak definujeme účinek Oracle ve všech stavech výpočetního základu: u všech $ x \in \\ { 0, 1 \\ } ^ n $ a $ y \in \\ { 0, 1 \\ } ^ m $ ,

$$
\begin{align}
    O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .
\end{align}
$$

Nyní $ o o = ^ \dagger $ podle konstrukce, proto jsme vyřešili obě předchozí problémy.

> [!TIP]
>Chcete-li vidět, že o ^ $ = { \dagger } $ $ 2, = \boldone $ od $ \oplus b \oplus b = a $ pro všechny $ a, b \in \: :: No-Loc ({):: 0, 1 \: :: No-Loc (})::: $ .
>V důsledku toho se $ O \ket { x } \ket { a \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .

V důležitém případě je třeba definovat Oracle tímto způsobem pro každý výpočetní stav x y, a to $ \ket { } \ket { } $ i $ v případě $ , že funguje pro jakýkoliv jiný stav.
Z toho vyplývá bezprostředně z faktu, že $ o $ , stejně jako všechny operace v provozu, je lineární ve stavu, ve kterém funguje.
Zvažte operaci Hadamard, například, která je definována v $ h \ket { 0 } = \ket { + } $ a $ h \ket { 1 } = \ket { - } $ .
Pokud chceme zjistit $ , jak h $ působí $ \ket { + } $ , můžeme použít tento $ h $ lineární,

$$
\begin{align}
H \ket { + } & = \frac { 1 } { \sqrt { 2 } } h ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + h \ket { 1 } )\\\\
           &= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .
\end{align}
$$

V případě definování našeho Oracle $ o $ můžeme obdobně použít jakýkoliv stav $ \ket { \psi } $ na $ n + m $ qubits, jak je možné zapsat

$$
\begin{align}
\ket{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y}
\end{align}
$$

kde $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C } $ představuje koeficienty stavu $ \ket { \psi } $ . Tedy,

$$
\begin{align}
O \ket { \psi } & = o \sum _ { × \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\
             &= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y \oplus f (x) } .
\end{align}
$$

## <a name="phase-oracles"></a>Fáze Oracle
Alternativně můžeme $ jazyk f kódovat $ do Oracle $ o použitím $ _fáze_ založené na vstupu na hodnotu $ o $ . Můžeme například definovat, jak by $ $$$
\begin{align}
    O \ket { × } = (-1) ^ { f (x) } \ket { x } .
\end{align}
$$
Pokud fáze Oracle působí na začátku v rámci výpočetního stavu $ \ket { x } $ , pak je tato fáze globální fází, takže nebudeme pozorně sledovat.
Takové Oracle ale může být velmi výkonný prostředek, pokud se aplikuje na nadpozici nebo jako kontrolované operace.
Představte si třeba fázi Oracle $ O_f $ pro qubit funkci $ f $ .
Stisknutím $$
\begin{align}
    O_f \ket{+}
        &=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\
        &=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\
        &=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\
        &=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } .
\end{align}
$$

Obecně platí, že obě zobrazení Oracle lze rozšířit tak, aby představovalo klasické funkce, které vracejí reálné hodnoty místo pouze jednoho bitu.

Volba nejlepšího způsobu implementace Oracle závisí intenzivně na tom, jak se tento Oracle bude používat v daném algoritmu.
Například [algoritmus Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) spoléhá na rozhraní Oracle implementované prvním způsobem, zatímco [algoritmus Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) spoléhá na rozhraní Oracle implementované druhým způsobem.


Pro další podrobnosti doporučujeme diskuzi v [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).
