---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f5cce3429b72f0ff6e00c2079241272881512da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704497"
---
# <a name="arrangedqubits-function"></a>ArrangedQubits – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


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

