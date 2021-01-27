---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: Operace ResetAll
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: 2b8e7fc0e7881d8c1bd6f14c150476262b7a2b19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849323"
---
# <a name="resetall-operation"></a><span data-ttu-id="f94fb-102">Operace ResetAll</span><span class="sxs-lookup"><span data-stu-id="f94fb-102">ResetAll operation</span></span>

<span data-ttu-id="f94fb-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="f94fb-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="f94fb-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f94fb-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f94fb-105">Přihlaste se k poli qubits, změřte je a ujistěte se, že jsou ve stavu | 0 ⟩ tak, aby je bylo možné bezpečně uvolnit.</span><span class="sxs-lookup"><span data-stu-id="f94fb-105">Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.</span></span>

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f94fb-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f94fb-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="f94fb-107">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f94fb-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f94fb-108">Pole qubits, jehož stavy mají být obnoveny na $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="f94fb-108">An array of qubits whose states are to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f94fb-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f94fb-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

