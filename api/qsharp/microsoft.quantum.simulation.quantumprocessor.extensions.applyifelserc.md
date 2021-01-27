---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRC
title: Operace ApplyIfElseRC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRC
qsharp.summary: ''
ms.openlocfilehash: 97536f2071918bec7129d8157e8750a5c310767f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855647"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="1a7de-102">Operace ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="1a7de-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="1a7de-103">Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="1a7de-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="1a7de-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1a7de-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseRC<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Ctl), oneArg : 'U)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="1a7de-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="1a7de-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="1a7de-106">measurementResult: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="1a7de-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-ctl"></a><span data-ttu-id="1a7de-107">onResultZeroOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="1a7de-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="1a7de-108">zeroArg: 'T</span><span class="sxs-lookup"><span data-stu-id="1a7de-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit--is-ctl"></a><span data-ttu-id="1a7de-109">onResultOneOp: U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL.</span><span class="sxs-lookup"><span data-stu-id="1a7de-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onearg--u"></a><span data-ttu-id="1a7de-110">oneArg: ' U</span><span class="sxs-lookup"><span data-stu-id="1a7de-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="1a7de-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1a7de-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1a7de-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="1a7de-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1a7de-113">'S</span><span class="sxs-lookup"><span data-stu-id="1a7de-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="1a7de-114">U</span><span class="sxs-lookup"><span data-stu-id="1a7de-114">'U</span></span>

