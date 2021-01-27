---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: ed70d9f24af06f8918083307c98a5f6c4671f1c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852944"
---
# <a name="inputencoder-function"></a>InputEncoder – funkce

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Vzhledem k sadě koeficientů a tolerance vrátí operaci přípravy stavu, která připraví každý koeficient jako odpovídající amplitudu výpočetního stavu.

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>Vstup

### <a name="coefficients--double"></a>koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]

Koeficienty, které mají být zakódovány do vstupního stavu.



## <a name="output--stategenerator"></a>Výstup: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Operace přípravy stavu, která připraví dané koeficienty jako vstupní stav daného registru.