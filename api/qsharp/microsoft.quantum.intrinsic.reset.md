---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Operace Reset
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: 61b5e4ccdf009dcb6c639e3d8e23bc73a6e475b5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198669"
---
# <a name="reset-operation"></a><span data-ttu-id="d4560-102">Operace Reset</span><span class="sxs-lookup"><span data-stu-id="d4560-102">Reset operation</span></span>

<span data-ttu-id="d4560-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="d4560-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="d4560-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d4560-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d4560-105">V případě jednoho qubitu je měří a zajišťuje, že je ve stavu | 0 ⟩, takže je možné ho bezpečně uvolnit.</span><span class="sxs-lookup"><span data-stu-id="d4560-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="d4560-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d4560-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="d4560-107">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d4560-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d4560-108">Qubit, jehož stav má být resetován na $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="d4560-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d4560-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d4560-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

