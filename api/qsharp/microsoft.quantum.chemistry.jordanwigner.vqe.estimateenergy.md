---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: Operace EstimateEnergy
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: fb59071ed05234d4a19cd97598bf479489b9985c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214411"
---
# <a name="estimateenergy-operation"></a>Operace EstimateEnergy

Obor názvů: [Microsoft. JordanWigner. chemie.. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Vyhodnotí energii v molekule sečtením energie, kterou přispěly jednotlivé Jordan-Wigner podmínek.

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a>Popis

Tato operace implicitně spoléhá na konvenci indexování s číselníkem.

## <a name="input"></a>Vstup

### <a name="jwhamiltonian--jordanwignerencodingdata"></a>jwHamiltonian: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Jordan-Wigner Hamiltonian.


### <a name="nsamples--int"></a>nSamples: [int](xref:microsoft.quantum.lang-ref.int)

Počet vzorků, které se mají použít pro odhad termínu očekávání.



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)

Odhadovaná energie molekuly