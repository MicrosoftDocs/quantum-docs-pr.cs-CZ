---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: fc7bf8e6157af079ae4233ef45e67ce8ddfb8fe3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854280"
---
# <a name="purifiedmixedstatewithdata-function"></a>PurifiedMixedStateWithData – funkce

Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí operaci, která připraví čištění daného kombinovaného stavu, entangled s registrem reprezentujícím danou kolekci dat.
"Vyčištěný smíšený stav s daty" odkazuje na stav formuláře σi √ PI | i ⟩ | XI ⟩ | uvolňování ⟩, kde každé XI je BITSTRING kódování dalších dat přidružených k registru | i ⟩.

https://arxiv.org/pdf/1805.03662.pdf?page=15Další diskuzi najdete v tématu.

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Popis

Pomocí techniky paměti pro paměťovou jednotku vystupuje danou matici hustoty a vrátí tuto reprezentaci jako operaci přípravy stavu.

Konkrétně je uveden seznam $N $ koeficientů $ \ alpha_j $ a BITSTRING $ \vec{x}_j $ přidružených k jednotlivým koeficientům. Tato funkce vrátí operaci, která pomocí techniky paměti pro procesory dopraví aproximaci $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {N-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _J} \bra{\vec{x}_j} \end{align} $ $ smíšeného stavu $ $ \begin{align} \rho = \sum_{j = 0} ^ {N-1} \ FRAC {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}, \end{align} $ $, kde každá $p _j $ je aproximací daného součinitele $ \ alpha_j $, například $ $ \begin{align} \left | p_j – \frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ for each $j $.

Při předání registru indexu a registru pro uvolňování paměti qubits, zpočátku ve stavu $ \ket {0} \ket{00\cdots 0}, vrácená operace připraví Registry do čištění $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _J} \ket{\text{garbage} _J}, \end{align} $ $, což resetuje a ruší registraci uvolnění paměti, vypíše požadovanou přípravu do cílové chyby $ \epsilon $.

## <a name="input"></a>Vstup

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

Cílová chyba $ \epsilon $.


### <a name="coefficients--doublebool"></a>koeficienty: ([Double](xref:microsoft.quantum.lang-ref.double),[bool](xref:microsoft.quantum.lang-ref.bool)[]) []

Pole $N $ koeficienty určující pravděpodobnost základních stavů společně s BITSTRING $ \vec{x} _j $ asociované s každým koeficientem.
Záporná čísla $-\ alpha_j $ se budou považovat za pozitivní $ | \ alpha_j | $.



## <a name="output--mixedstatepreparation"></a>Výstup: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

Operace, která připraví $ \tilde \rho $ jako čištění do společného indexu a registru pro uvolňování paměti.

## <a name="remarks"></a>Poznámky

Koeficienty poskytované této operaci jsou normalizovány po 1 normě, což znamená, že koeficienty jsou vždy považovány za Popis platné distribuce pravděpodobnosti kategorií.

## <a name="references"></a>Reference

- Kódování elektronického spektra v Okruhech v případě využití lineární T, Babbush, Craig Gidney, Dominic W. bobulovin, Nathan Wiebe, Jarrod McClean, Alexandru bledější, Austin Fowlera, Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Viz také

- [Microsoft. Přípravno. Preparation. PurifiedMixedState](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)