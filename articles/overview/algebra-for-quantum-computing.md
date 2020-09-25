---
title: Lineární algebra pro kvantové výpočty
description: Přečtěte si o základních konceptech lineární algebry, které jsou potřeba pro pochopení kvantových výpočtů
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.algebra
no-loc:
- Q#
- $$v
ms.openlocfilehash: bff1da475f87278bc9e769805b3fe0fe8704d47a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835124"
---
# <a name="linear-algebra-for-quantum-computing"></a>Lineární algebra pro kvantové výpočty

Jazykem kvantových výpočtů je lineární algebra. I když ji nepotřebujete nutně znát k implementaci nebo psaní kvantových programů, velmi často se používá k popisu stavů qubitů a kvantových operací a k odhadu toho, co kvantový počítač udělá v reakci na posloupnost instrukcí.

Stejně jako znalost [základních konceptů kvantové fyziky](xref:microsoft.quantum.overview.understanding) vám pomůže lépe pochopit kvantové výpočty, znalost základů lineární algebry vám usnadní pochopení toho, jak kvantové algoritmy fungují. Přinejmenším se vám budou hodit **vektory** a **násobení matic**. Pokud si potřebujete oživit znalosti těchto algebraických konceptů, tady je pár kurzů, které vám s tím pomůžou:

- [Kurz Jupyter Notebook o lineární algebře](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/LinearAlgebra)
- [Kurz Jupyter Notebook o komplexní aritmetice](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ComplexArithmetic)
- [Lineární algebra pro kvantové výpočty](https://cds.cern.ch/record/1522001/files/978-1-4614-6336-8_BookBackMatter.pdf)
- [Základy lineární algebry](https://www.math.ubc.ca/~carrell/NB.pdf)
- [Úvod do kvantových výpočtů](https://www.codeproject.com/Articles/5155638/Quantum-Computation-Primer-Part-1#exploring-quantum-superposition)

## <a name="vectors-and-matrices-in-quantum-computing"></a>Vektory a matice v kvantových výpočtech

V článku [Principy kvantových výpočtů](xref:microsoft.quantum.overview.understanding) jsme se dozvěděli, že qubit může být ve stavu 1 nebo 0 nebo v superpozici těchto stavů. Pomocí lineární algebry můžeme stav qubitu popsat jako vektor, zapsaný jako jednosloupcová **matice** $\begin{bmatrix} a \\\\  b \end{bmatrix}$. To se také označuje jako **kvantový stavový vektor** a musí splňovat podmínku $|a|^2 + |b|^2 = 1$.  

Prvky matice představují pravděpodobnost, že qubit zkolabuje do jedné nebo druhé hodnoty, přičemž $|a|^2$ je pravděpodobnost kolapsu na nulu a $|b|^2$ je pravděpodobnost kolapsu na jedničku. Všechny následující matice reprezentují platné stavové vektory:

$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}, \begin{bmatrix} 0 \\\\  1 \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix}, \text{ and }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}.$$

V [kvantových počítačích a kvantových simulátorech](xref:microsoft.quantum.overview.simulators) jste si také všimli, že se k úpravě stavu qubitů používají kvantové operace.  Kvantové operace je také možné reprezentovat pomocí matice. Když se na qubit použije kvantová operace, vynásobí se matice, které reprezentují qubit a danou operaci a výsledná matice pak představuje nový stav qubitu.  

Tady jsou dvě běžné kvantové operace a jejich popis pomocí násobení matic.


[Operace `X`](xref:microsoft.quantum.intrinsic.x) je reprezentovaná Pauliho maticí $X$,

$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix},$$
    
a slouží k převrácení stavu qubitu z 0 na 1 (nebo naopak), například

$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}.$$

[Operace ' H '](xref:microsoft.quantum.intrinsic.h) je reprezentována Hadamardovou transformací $H$,

$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix},$$

 a převede qubit do takové superpozice stavů, ve které má stejnou pravděpodobnost kolapsu do obou stavů, jak je znázorněno níže:

$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}.$$

Matice, která představuje kvantovou operaci, musí mít jedinou vlastnost – musí být **unitární**. Matice je unitární, když je její **inverzní** matice rovna její **hermitovsky sdružené** matici.

## <a name="representing-two-qubit-states"></a>Reprezentace stavů dvou qubitů

Ve výše uvedených příkladech se stav jednoho qubitu popisoval pomocí jednosloupcové matice $\begin{bmatrix} a \\\\ b \end{bmatrix}$ a použití operace na ni bylo popsáno vynásobením dvou matric. Kvantové počítače ale můžou mít víc než jeden qubit, jak tedy popíšeme kombinovaný stav dvou qubitů? 

Pamatujte, že každý qubit je vektorový prostor, takže se nedají jednoduše vynásobit. Místo toho použijeme **tenzorový součin**, což je operace, která ze dvou vektorových prostorů vytvoří nový vektorový prostor, a zapisuje se symbolem $\otimes$. Například tenzorový součin stavů dvou qubitů $\begin{bmatrix} \\\\ b \end{bmatrix}$ a $\begin{bmatrix} c \\\\ d \end{bmatrix}$ se vypočítá jako

$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}. $$

Výsledkem je čtyřřádková matice, kde každý prvek představuje pravděpodobnost. Například $ac$ je pravděpodobnost, že oba qubity zkolabují do 0 a 0, $ad$ je pravděpodobnost kolapsu do 0 a 1 a tak dále. 

Stejně jako musí stav jednoho qubitu $\begin{bmatrix} a \\\\  b \end{bmatrix}$ splňovat podmínku $|a|^2 + |b|^2 = 1$, aby reprezentoval platný kvantový stav, musí i stav dvou qubitů $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ splňovat podmínku $|ac|^2 + |ad|^2 + |bc|^2+ |bd|^2 = 1$.

## <a name="summary"></a>Souhrn

Lineární algebra je standardní jazyk pro popis kvantových výpočtů a kvantové fyziky. I když vám [knihovny](xref:microsoft.quantum.libraries) zahrnuté v sadě Microsoft Quantum Development Kit pomůžou spouštět pokročilé kvantové algoritmy i bez hlubšího pochopení příslušné matematiky, je přesto důležitá k urychlení vašich začátků a k vytvoření pevných základů, na kterých mžete dál stavět.

## <a name="next-steps"></a>Další kroky

[Instalace sady QDK](xref:microsoft.quantum.install)
