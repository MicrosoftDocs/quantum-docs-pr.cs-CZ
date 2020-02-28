---
title: Kvantová orákula
description: Přečtěte si, jak pracovat s a definovat i ty Oracle, operace s černým polem, které se používají jako vstup pro jiný algoritmus.
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
ms.openlocfilehash: 1d1d0b0903db8e994166c3e8a5798f70742a1c7e
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904923"
---
# <a name="quantum-oracles"></a>Nejenom Oracle

Oracle $O $ je operace "Black Box", která se používá jako vstup pro jiný algoritmus.
Tyto operace se často definují pomocí klasické funkce $f: \\{0, 1\\} ^ n \to \\{0, 1\\} ^ m $, který přebírá $n $-bit binárního vstupu a vytváří $m $ bitový binární výstup.
Provedete to tak, že zaberete konkrétní binární vstup $x = (x_{0}, x_{1}, \dots, x_ {n-1}).
Můžeme označit qubit stavy jako $ \ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_ {n-1}} $.

Můžeme se nejdřív pokusit o definování $O $ tak, že $O \ket{x} = \ket{f (x)} $, ale má několik problémů.
První, $f $ může mít jinou velikost vstupu a výstupu ($n \Ne m $), což použití $O $ by změnilo počet qubits v registru.
Za druhé, i když $n = m $, funkce nemusí být inverzi: Pokud $f (x) = f (y) $ pro některé $x \Ne y $, pak $O \ket{x} = O\ket {y} $, ale $O ^ \dagger O\ket {x} \Ne O ^ \dagger O\ket {y} $.
To znamená, že nebudeme moct vytvořit sousedící operaci $O ^ \dagger $ a Oracle musí mít pro ně definované sousedící.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Definování systému Oracle jeho účinkem na výpočetní bázi – stavy
S oběma uvedenými problémy se můžeme zabývat tím, že zavedete druhý registr $m $ qubits a podržíte naši odpověď.
Pak nadefinujeme účinek Oracle na všechny stavy výpočtů na bázi: pro všechny $x \in \\{0, 1\\} ^ n $ a $y \in \\{0, 1\\} ^ m $,

$ $ \begin{align} O (\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f (x)}.
\end{align} $ $

Nyní $O = O ^ \dagger $ podle konstrukce, proto jsme vyřešili obě předchozí problémy.

> [!TIP]
> Pokud chcete vidět, že $O = O ^ {\dagger} $, Všimněte si, že $O ^ 2 = \boldone $, protože $a \oplus b \oplus b = a $ for All $a, b \in \{0, 1\}$.
> V důsledku toho $O \ket{x} \ket{y \oplus f (x)} = \ket{x} \ket{y \oplus f (x) \oplus f (x)} = \ket{x} \ket{y} $.

Důležité je, abyste definovali Oracle tímto způsobem pro každý výpočetní stav $ \ket{x}\ket{y} $, který definuje, jak $O $ chovat pro jakýkoliv jiný stav.
Postup je ihned ze skutečnosti, že $O $, stejně jako všechny provozní operace, je lineární ve stavu, ve kterém funguje.
Zvažte operaci Hadamard, například, která je definována $H \ket{0} = \ket{+} $ a $H \ket{1} = \ket{-}$.
Pokud chceme zjistit, jak $H $ funguje na $ \ket{+} $, můžeme použít $H $ je lineární,

$ $ \begin{align} H\ket {+} & = \frac{1}{\sqrt{2}} H (\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0}-\ket{1}) = \ket{0}.
\end{align} $ $

V případě definování našeho Oracle $O $ můžeme podobně použít jakýkoliv stav $ \ket{\psi} $ v $n + m $ qubits může být zapsaný jako

$ $ \begin{align} \ket{\psi} & = \ sum_ {x \in \\{0, 1\\} ^ n, y \in \\{0, 1\\} ^ m} \Alpha (x, y) \ket{x} \ket{y} \end{align} $ $

kde $ \Alpha: \\{0, 1\\} ^ n \times \\{0, 1\\} ^ m \to \mathbb{C} $ představuje koeficienty stavu $ \ket{\psi} $. Rozdíl

$ $ \begin{align} O \ket{\psi} & = O \ sum_ {x \in \\{0, 1\\} ^ n, y \in \\{0, 1\\} ^ m} \Alpha (x, y) \ket{x} \ket{y} \\\\ & = \ sum_ {x \in \\{0, 1\\} ^ n, y \in \\{0, 1\\} ^ m} \Alpha (x, y) O \ket{x} \ket{y} \\\\ & = \ sum_ {x \in \\{0; 1\\} ^ n , y \in \\{0, 1\\} ^ m} \Alpha (x, y) \ket{x} \ket{y \oplus f (x)}.
\end{align} $ $

## <a name="phase-oracles"></a>Fáze Oracle
Další možností je kódování $f $ do Oracle $O $, a to použitím _fáze_ založené na vstupu do $O $.
Můžeme například definovat $O $, což je $ $ \begin{align} O \ket{x} = (-1) ^ {f (x)} \ket{x}.
\end{align} $ $ Pokud fáze Oracle funguje na prvním registru ve stavu výpočtu $ \ket{x} $, pak je tato fáze globální fází, a proto nepozorovatelná.
Takové Oracle ale může být velmi výkonný prostředek, pokud se aplikuje na nadpozici nebo jako kontrolované operace.
Představte si třeba fázi orcale $O _f $ pro qubit funkci s jedním $f $.
Pak $ $ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1})/\sqrt{2} \\\\ & = ((-1) ^ {f (0)} \ket{0} + (-1) ^ {f (1)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f (0)} (\ket{0} + (-1) ^ {f (1)-f (0)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket{+}.
\end{align} $ $

Obecně platí, že obě zobrazení Oracle lze rozšířit tak, aby představovalo klasické funkce, které vracejí reálné hodnoty místo pouze jednoho bitu.

Volba nejlepšího způsobu implementace Oracle závisí intenzivně na tom, jak se tento Oracle bude používat v daném algoritmu.
Například [algoritmus Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) spoléhá na rozhraní Oracle implementované prvním způsobem, zatímco [algoritmus Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) spoléhá na rozhraní Oracle implementované druhým způsobem.


Pro další podrobnosti doporučujeme diskuzi v [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).
