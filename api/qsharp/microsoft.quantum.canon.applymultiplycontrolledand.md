---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: Operace ApplyMultiplyControlledAnd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: feca28d394e4af31eb4ffe737111d00ede45e27e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705192"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="9c536-102">Operace ApplyMultiplyControlledAnd</span><span class="sxs-lookup"><span data-stu-id="9c536-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="9c536-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9c536-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9c536-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9c536-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9c536-105">Implementuje Toffoli bránu s více řízenými hodnotami za předpokladu, že cílový qubit je inicializovaný 0.</span><span class="sxs-lookup"><span data-stu-id="9c536-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="9c536-106">Operace souseda předpokládá, že cílový qubit bude resetován na hodnotu 0.</span><span class="sxs-lookup"><span data-stu-id="9c536-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="9c536-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="9c536-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="9c536-108">ovládací prvky: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9c536-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9c536-109">Qubits ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="9c536-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9c536-110">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9c536-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9c536-111">Cílový qubit</span><span class="sxs-lookup"><span data-stu-id="9c536-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="9c536-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9c536-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

