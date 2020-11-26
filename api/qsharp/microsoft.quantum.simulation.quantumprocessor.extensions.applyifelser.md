---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseR
title: Operace ApplyIfElseR
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseR
qsharp.summary: ''
ms.openlocfilehash: 9e391b61aa4d22ad02bf657a866f959d35b6628f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192668"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="a91d9-102">Operace ApplyIfElseR</span><span class="sxs-lookup"><span data-stu-id="a91d9-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="a91d9-103">Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="a91d9-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="a91d9-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a91d9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseR<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T), (onResultOneOp : ('U => Unit), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="a91d9-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="a91d9-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="a91d9-106">measurementResult: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="a91d9-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="a91d9-107">onResultZeroOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a91d9-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="a91d9-108">zeroArg: 'T</span><span class="sxs-lookup"><span data-stu-id="a91d9-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit"></a><span data-ttu-id="a91d9-109">onResultOneOp: [jednotka](xref:microsoft.quantum.lang-ref.unit) U =></span><span class="sxs-lookup"><span data-stu-id="a91d9-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--u"></a><span data-ttu-id="a91d9-110">oneArg: ' U</span><span class="sxs-lookup"><span data-stu-id="a91d9-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="a91d9-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a91d9-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a91d9-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a91d9-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a91d9-113">'S</span><span class="sxs-lookup"><span data-stu-id="a91d9-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="a91d9-114">U</span><span class="sxs-lookup"><span data-stu-id="a91d9-114">'U</span></span>

