---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: Operace ApplyMultiplyControlledAnd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: ac3972287d55ed2df85e1d88510918cc5202c711
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844840"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="d8695-102">Operace ApplyMultiplyControlledAnd</span><span class="sxs-lookup"><span data-stu-id="d8695-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="d8695-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d8695-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d8695-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d8695-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d8695-105">Implementuje Toffoli bránu s více řízenými hodnotami za předpokladu, že cílový qubit je inicializovaný 0.</span><span class="sxs-lookup"><span data-stu-id="d8695-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="d8695-106">Operace souseda předpokládá, že cílový qubit bude resetován na hodnotu 0.</span><span class="sxs-lookup"><span data-stu-id="d8695-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="d8695-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="d8695-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="d8695-108">ovládací prvky: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d8695-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d8695-109">Qubits ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="d8695-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d8695-110">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d8695-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d8695-111">Cílový qubit</span><span class="sxs-lookup"><span data-stu-id="d8695-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="d8695-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d8695-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

