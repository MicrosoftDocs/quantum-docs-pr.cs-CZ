---
uid: Microsoft.Quantum.Research.Chemistry.OptimizedTrotterStepOracle
title: OptimizedTrotterStepOracle – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: OptimizedTrotterStepOracle
qsharp.summary: Returns optimized Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: 523a31564ae5f054fd60161f9981c43d3467f3d9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842276"
---
# <a name="optimizedtrottersteporacle-function"></a>OptimizedTrotterStepOracle – funkce

Obor názvů: [Microsoft. Prohledávejte. Research. chemie](xref:Microsoft.Quantum.Research.Chemistry)

Balíček: [Microsoft. prostudoval. Research. chemie](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Vrátí optimalizovanou operaci kroku Trotter a parametry nezbytné ke spuštění.

```qsharp
function OptimizedTrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a>Vstup

### <a name="qsharpdata--jordanwignerencodingdata"></a>qSharpData: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Hamiltonian popsané podle `JordanWignerEncodingData` formátu.


### <a name="trotterstepsize--double"></a>trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)

Velikost kroku Trotter integrátoru.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Pořadí Trotter integrátoru.



## <a name="output--intdoublequbit--unit--is-adj--ctl"></a>Výstup: ([int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL))

Řazená kolekce členů `Int` , kde: je počet přidělených qubits, `Double` je `1.0/trotterStepSize` a operace je krok Trotter.