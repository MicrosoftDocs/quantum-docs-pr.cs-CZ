---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 07a4ed5fe99dedb333246f7161d157dcd01a01da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841080"
---
# <a name="arrangedqubits-function"></a>ArrangedQubits – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Uspořádání ovládacího prvku, cíle a pomocníka qubits podle indexu

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a>Popis

Vrátí pole qubit s cílem v indexu 0 a ovládací prvek i na indexu 2 ^ i.  Pomocná qubits se vloží do všech ostatních pozic v poli.

## <a name="input"></a>Vstup

### <a name="controls--qubit"></a>ovládací prvky: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)




### <a name="helper--qubit"></a>pomocný objekt: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--qubit"></a>Výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

