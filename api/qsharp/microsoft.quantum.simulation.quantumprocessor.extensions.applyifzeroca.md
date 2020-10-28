---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroCA
title: Operace ApplyIfZeroCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroCA
qsharp.summary: ''
ms.openlocfilehash: 978964888a89ca46847ae7aa01a2c180ee322436
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709369"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="a9cdb-102">Operace ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="a9cdb-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="a9cdb-103">Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="a9cdb-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="a9cdb-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9cdb-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfZeroCA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl + Adj), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="a9cdb-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="a9cdb-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="a9cdb-106">measurementResult: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="a9cdb-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-ctl--adj"></a><span data-ttu-id="a9cdb-107">onResultZeroOp: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL a ADJ</span><span class="sxs-lookup"><span data-stu-id="a9cdb-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="a9cdb-108">zeroArg: 'T</span><span class="sxs-lookup"><span data-stu-id="a9cdb-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="a9cdb-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9cdb-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a9cdb-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a9cdb-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a9cdb-111">'S</span><span class="sxs-lookup"><span data-stu-id="a9cdb-111">'T</span></span>

