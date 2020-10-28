---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Operace Reset
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: c89cbbce49e294e56abc11b3b0492d2ed8e980a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707112"
---
# <a name="reset-operation"></a><span data-ttu-id="680e9-102">Operace Reset</span><span class="sxs-lookup"><span data-stu-id="680e9-102">Reset operation</span></span>

<span data-ttu-id="680e9-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="680e9-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="680e9-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="680e9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="680e9-105">V případě jednoho qubitu je měří a zajišťuje, že je ve stavu | 0 ⟩, takže je možné ho bezpečně uvolnit.</span><span class="sxs-lookup"><span data-stu-id="680e9-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="680e9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="680e9-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="680e9-107">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="680e9-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="680e9-108">Qubit, jehož stav má být resetován na $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="680e9-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="680e9-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="680e9-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

