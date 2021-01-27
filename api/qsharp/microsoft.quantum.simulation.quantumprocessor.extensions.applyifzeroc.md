---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroC
title: Operace ApplyIfZeroC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroC
qsharp.summary: ''
ms.openlocfilehash: c4d1618ff5e2a3d61823eddd6905445effcecfdd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854175"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="7c4dd-102">Operace ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="7c4dd-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="7c4dd-103">Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="7c4dd-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="7c4dd-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7c4dd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroC<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="7c4dd-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="7c4dd-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="7c4dd-106">measurementResult: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="7c4dd-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-ctl"></a><span data-ttu-id="7c4dd-107">onResultZeroOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="7c4dd-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="7c4dd-108">zeroArg: 'T</span><span class="sxs-lookup"><span data-stu-id="7c4dd-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="7c4dd-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c4dd-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7c4dd-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="7c4dd-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7c4dd-111">'S</span><span class="sxs-lookup"><span data-stu-id="7c4dd-111">'T</span></span>

