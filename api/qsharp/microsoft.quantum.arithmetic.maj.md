---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: Operace MAJ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 356689baa6d47b7b93a393f3672991bb589f6921
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222758"
---
# <a name="maj-operation"></a>Operace MAJ

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


To aplikuje operaci na místní většinu na 3 qubits.

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Pokud budeme poznamenat stav cílové qubit jako $ \ket{z} $ a vstupní stavy vstupních qubits jako $ \ket{x} $ a $ \ket{y} $, pak tato operace provede následující transformaci: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{maj} (x, y, z)} $.

## <a name="input"></a>Vstup

### <a name="input0--qubit"></a>input0: [qubit](xref:microsoft.quantum.lang-ref.qubit)

První vstupní qubit


### <a name="input1--qubit"></a>input1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Druhý vstup qubit.


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, na který se použije většina funkce.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

