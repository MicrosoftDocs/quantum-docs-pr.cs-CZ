---
uid: Microsoft.Quantum.Random.NormalDistribution
title: NormalDistribution – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814187"
---
# <a name="normaldistribution-function"></a>NormalDistribution – funkce

Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vrací normální rozdělení s daným významem a odchylkou.

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Vstup

### <a name="mean--double"></a>střední hodnota: [Double](xref:microsoft.quantum.lang-ref.double)




### <a name="variance--double"></a>Variance: [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--continuousdistribution"></a>Výstup: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)



## <a name="example"></a>Příklad

Následující kreslí 10 vzorků od normálního rozdělení se střední odchylkou 2 a směrodatnou odchylku 0,1:

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a>Viz také

- [Microsoft. prohodilá. StandardNormalDistribution](xref:Microsoft.Quantum.Random.StandardNormalDistribution)