---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroA
title: Operace ApplyIfZeroA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroA
qsharp.summary: ''
ms.openlocfilehash: 812b7a830d963b4bb73c32ba1c136e506789e997
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854204"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="b040c-102">Operace ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="b040c-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="b040c-103">Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="b040c-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="b040c-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b040c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="b040c-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="b040c-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="b040c-106">measurementResult: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="b040c-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj"></a><span data-ttu-id="b040c-107">onResultZeroOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="b040c-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="b040c-108">zeroArg: 'T</span><span class="sxs-lookup"><span data-stu-id="b040c-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="b040c-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b040c-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b040c-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b040c-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b040c-111">'S</span><span class="sxs-lookup"><span data-stu-id="b040c-111">'T</span></span>

