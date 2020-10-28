---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZ
title: Operace _JWOptimizedZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZ
qsharp.summary: Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.
ms.openlocfilehash: 8bbd4af0389a7b748be11dc50bacd2c178521adc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708920"
---
# <a name="_jwoptimizedz-operation"></a><span data-ttu-id="b6a53-102">Operace _JWOptimizedZ</span><span class="sxs-lookup"><span data-stu-id="b6a53-102">_JWOptimizedZ operation</span></span>

<span data-ttu-id="b6a53-103">Obor názvů: [Microsoft. Prohledávejte. Research. chemie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b6a53-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="b6a53-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6a53-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b6a53-105">Aplikuje RZ rotaci s C-neštychem do dvojité fáze odhadu fáze.</span><span class="sxs-lookup"><span data-stu-id="b6a53-105">Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.</span></span>

```qsharp
operation _JWOptimizedZ (angle : Double, parityQubit : Qubit, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="b6a53-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="b6a53-106">Input</span></span>

### <a name="angle--double"></a><span data-ttu-id="b6a53-107">uhel: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b6a53-107">angle : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b6a53-108">Úhel otáčení RZ</span><span class="sxs-lookup"><span data-stu-id="b6a53-108">Angle of Rz rotation.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="b6a53-109">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b6a53-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b6a53-110">Qubit, která určuje znaménko času vývoje.</span><span class="sxs-lookup"><span data-stu-id="b6a53-110">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="b6a53-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b6a53-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="b6a53-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6a53-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

