---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 73b031f1082d0a12975abad074b07184dcbabdbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230017"
---
# <a name="purifiedmixedstate-function"></a>PurifiedMixedState – funkce

Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí operaci, která připraví čištění daného smíšeného stavu.
"Vyčištěný smíšený stav" odkazuje na stavy formuláře | ψ ⟩ = σi √ PI | i ⟩ | uvolňování ⟩ určené vektorem koeficientů {PI}. Stavy tohoto formuláře se dají snížit na smíšené stavy ρ ≔ PI | i ⟩ ⟨ i | trasováním v registru "uvolnění paměti" (to znamená smíšený stav, který je šikmý v výpočetních intervalech).

https://arxiv.org/pdf/1805.03662.pdf?page=15Další diskuzi najdete v tématu.

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Popis

Pomocí techniky paměti pro paměťovou jednotku vystupuje danou matici hustoty a vrátí tuto reprezentaci jako operaci přípravy stavu.

Konkrétně v případě, že seznam $N $-efektivnosti $ \ alpha_j $, tato funkce vrátí operaci, která pomocí techniky paměti pro práci s procesory připraví aproximaci $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ pro smíšený stav $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ FRAC {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{align} $ $, kde každá $p _j $ je sblížená s daným koeficientem $ \ alpha_j $, například $ $ \begin{align} \left | p_j – \frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ for each $j $.

Při předání registru indexu a registru qubits paměti ve stavu $ \ket {0} \ket{00\cdots 0} tato vrácená operace připraví oba Registry do čištění $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _J}, \end{align} $ $ tak, aby resetování a zrušení přidělení uvolňování paměti vypravilo požadovanou přípravu v rámci cílové chyby $ \epsilon $.

## <a name="input"></a>Vstup

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

Cílová chyba $ \epsilon $.


### <a name="coefficients--double"></a>koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]

Pole $N $ koeficientů určujících pravděpodobnost základních stavů.
Záporná čísla $-\ alpha_j $ se budou považovat za pozitivní $ | \ alpha_j | $.



## <a name="output--mixedstatepreparation"></a>Výstup: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

Operace, která připraví $ \tilde \rho $ jako čištění do společného indexu a registru pro uvolňování paměti.

## <a name="remarks"></a>Poznámky

Koeficienty poskytované této operaci jsou normalizovány po 1 normě, což znamená, že koeficienty jsou vždy považovány za Popis platné distribuce pravděpodobnosti kategorií.

## <a name="references"></a>Reference

- Kódování elektronického spektra v Okruhech v případě využití lineární T, Babbush, Craig Gidney, Dominic W. bobulovin, Nathan Wiebe, Jarrod McClean, Alexandru bledější, Austin Fowlera, Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Viz také

- [Microsoft. Přípravno. Preparation. PurifiedMixedStateWithData](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)