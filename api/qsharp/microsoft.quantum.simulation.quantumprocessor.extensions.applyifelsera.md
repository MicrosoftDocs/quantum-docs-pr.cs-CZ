---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRA
title: Operace ApplyIfElseRA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRA
qsharp.summary: ''
ms.openlocfilehash: 11427026d66fc6f46f05004db4dae6f9fa05d921
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855665"
---
# <a name="applyifelsera-operation"></a><span data-ttu-id="6a784-102">Operace ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="6a784-102">ApplyIfElseRA operation</span></span>

<span data-ttu-id="6a784-103">Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="6a784-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="6a784-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6a784-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseRA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj), oneArg : 'U)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="6a784-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="6a784-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="6a784-106">measurementResult: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="6a784-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj"></a><span data-ttu-id="6a784-107">onResultZeroOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="6a784-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="6a784-108">zeroArg: 'T</span><span class="sxs-lookup"><span data-stu-id="6a784-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit--is-adj"></a><span data-ttu-id="6a784-109">onResultOneOp: jednotka U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="6a784-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onearg--u"></a><span data-ttu-id="6a784-110">oneArg: ' U</span><span class="sxs-lookup"><span data-stu-id="6a784-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="6a784-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a784-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6a784-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6a784-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6a784-113">'S</span><span class="sxs-lookup"><span data-stu-id="6a784-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="6a784-114">U</span><span class="sxs-lookup"><span data-stu-id="6a784-114">'U</span></span>

