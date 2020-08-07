---
title: Jordánsko – reWigner reprezentace
description: Přečtěte si o reprezentaci Wigner, která mapuje operátory Hamiltonian na jednotnou matrici, která se dá snadněji implementovat na počítač s procesorem.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9f1455ebbecf6a3500ec11a5196e7662455c9a78
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869507"
---
# <a name="jordan-wigner-representation"></a>Jordánsko – reWigner reprezentace

I když se druhý quantized Hamiltonians pohodlně prezentuje v $a ^ \dagger $ (vytváření) a $a $ (Annihilation), tyto operace nejsou základní operace v počítačích s více operačními čísly.
V důsledku toho by v případě, že chceme, aby je implementovali na počítač s více společnostmi, musíme namapovat operátory na jednotnou matrici, která se dá implementovat na počítač s více než jednou.
Jordánsko – Wigner reprezentace poskytuje jednu takovou mapu.
Existují však i další, jako je například reprezentace Bravyi – Kitaev a jejich vlastní relativní výhody a nevýhody.
Hlavní výhodou Wigner reprezentace je jeho jednoduchost.

Reprezentací Jordánsko-Wigner je přímo předána k odvození.
Odvolání, že stav $ \ket {0} _J $ znamená, že $j Orbital $ je prázdný a $ \ket {1} _J $ znamená, že je obsazený.
To znamená, že qubits může přirozeně ukládat povolání daného číselníku Orbital.
Pak to máme $a ^ \ dagger_j \ket {0} _J = \ket {1} _J $ a $a ^ \ dagger_j \ket {1} _J = $0.
Je snadné ověřit, že \begin{Align} a ^ \ dagger_j &= \begin{bmatrix}0 & 0 \\ \ 1 &0 \end{bmatrix} = \frac{X_j-iY_j} {2} , \nonumber \\ \\ a_j &= \begin{bmatrix}0 & 1 \\ \ 0 &0 \end{bmatrix} = \frac{X_j + iY_j} {2} , \end{align} kde $X _J $ a $Y _j $ jsou operátory Pauli-$X $ a-$Y $ fungující na qubit $j $.

>[!NOTE]
> Ve Q# stavu $ \ket {0} $ představuje + 1 eigenstate operátoru $Z $. V některých oblastech fyzika $ \ket {0} $ představuje stav s nízkou spotřebou energie, tedy i-1 eigenstate operátoru $Z $. Některé vzorce se proto mohou od oblíbené literatury lišit.

V knihovně chemie používáme $ \ket {0} $ k reprezentaci neobsazeného číselníku Orbital.
To ukazuje, že pro jednoduché Orbital se snadno reprezentují operátory vytváření a Annihilation v souvislosti s jednotnými matricemi, které počítače rozumí.
Všimněte si, že zatímco $X $ a $Y $ jsou jednotkové $a ^ \dagger $ a $a $ nejsou.
Později uvidíme, že to nepředstavuje výzvu pro simulaci.

Jedním z problémů, které zůstává, je to, že i když výše uvedená konstrukce funguje pro jeden Orbital, to se pro systémy se dvěma nebo více číselníky nezdařila.
Vzhledem k tomu, že Fermions jsou antisymmetic, víme, že $a ^ \ dagger_j a ^ \ dagger_k =-a ^ \ dagger_k a ^ \ dagger_j $ pro všechny $j $ a $k $.
Nicméně $ $ \left (\frac{X_j-iY_j} {2} \right) \left (\frac{X_k-iY_k} {2} \right) = \left (\frac{X_k-iY_k} \right) {2} \left (\frac{X_j-iY_j} {2} \right).
$ $ Jinými slovy, dva operátory vytváření nedělají anti-dojíždění podle potřeby.
To je možné odstranit, pokud je to jasné, pokud je to elegantní.
Je potřeba si uvědomit, že Pauli operátory přirozeně anti-dojíždění.
Konkrétně $XZ =-ZX $ a $YZ =-ZY $.
Proto můžeme připravovat $Z $ Operators do konstrukce operátoru, abychom mohli emulovat správné řešení pro dojíždění.
Úplná konstrukce je následující: 

\begin{Align} a ^ \ dagger_1 &= \left (\frac{X-iY} {2} \right) \otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1, \\ \\ ^ \ dagger_2 &= Z\otimes\left (\frac{X-iY} {2} \right) \otimes 1 \ otimes 1 \otimes \cdots \otimes 1, \\ \\ a ^ \ dagger_3 &= Z\otimes Z\otimes \left (\frac{X-iY} {2} \right) \otimes 1 \otimes \cdots \otimes 1, \\ \\ & \Vdots \\ \\ a ^ \ dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left (\frac{X-iY} {2} \right). \label{eq:JW} \end{align}

Je také vhodné vyjádřit číselné operátory $n _j $, a to z podmínek operátorů Pauli.
Naštěstí, po provedení této náhrady zruší řetězce $Z $ Operators (označované jako Jordánsko-Wigner řetězce).
Po ukončení tohoto volání (a opětovném volání tohoto $X _jY_j = iZ_j $) máme \begin{Equation} n_j = a ^ \ dagger_j a_j = \frac{(1-Z_j)} {2} .
\end{equation}


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a>Sestavování Hamiltonians v Jordánsko – Wigner reprezentace

Jakmile jsme vyvolali reprezentaci Wigner, která překládá Hamiltonian na součet operátorů Pauli, je přímá dopřed.
Jeden z nich musí nahradit každý z $a ^ \dagger $ a $a $ Operators v Hamiltonianu Fermionic s řetězci Pauli-Operators uvedených výše.
Když jedna tato náhrada provede, je v rámci Hamiltonian jenom pět tříd podmínek.
Tyto pět tříd odpovídají různým způsobům, jak můžeme vybrat $p, q $ a $p, q, r, s $ v rámci jednoho těla a podmínek obou těla v Hamiltonian.
Tyto pět tříd, pro případ, kdy $p>q>r>s $ a orbitals s reálnými hodnotami jsou

\begin{align} H_ {PP} a_p ^ \dagger a_p &= \ sum_p \frac{H_ {PP}} {2} (1-Z_p) \\ \\ H_ {pq} (a_p ^ \dagger a_q + a ^ \ dagger_q a_p) &= \frac{H_ {pq}} {2} \left (\ prod_ {j = q + 1} ^ {p-1} Z_j \right) \left (X_pX_q + Y_pY_q \right) \\ \\ H_ {pqqp} n_p n_q &= \frac{H_ {pqqp}} {4} \left (1-Z_p-Z_q + Z_pZ_q \right) \\ \\ H_ {pqqr} &= \frac{H_ {pqqr}} {2} \left (\ prod_ {j = r + 1} ^ {p-1} Z_j \right) \left (X_pX_r + Y_pY_r \right) \left (\frac{1-Z_q} {2} \right) \\ \\ H_ {pqrs} &= \frac{H_ {pqrs}} {8} \ prod_ {j = s + 1} ^ {r-1} Z_j \ prod_ {k = q + 1} ^ {p-1} Z_k \Big (XXXX-XXYY + XYXY\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big) \end{align}

Při generování takových Hamiltonians stačí použít tato náhradní pravidla, takže by to bylo neproveditelné pro velké molekuly, které se můžou skládat z milionů Hamiltonian podmínek.
Alternativně můžeme automaticky sestavit `JordanWignerEncoding` dané `FermionHamiltonian` znázornění Hamiltonian.

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

Po sestavení Hamiltonians v tomto formuláři můžeme použít hostitele simulačních algoritmů pro simulaci počtu procesorů k zkompilování aplikace vygenerované $e ^ {iHt} $ do sekvence základních bran (v rámci některé uživatelsky definované tolerance chyb).
Probereme dvě nejoblíbenější metody pro simulaci, qubitization a Trotter – vzorce Suzuki v dokumentaci s algoritmem. Implementace obou metod poskytujeme v knihovně simulace Hamiltonian.
