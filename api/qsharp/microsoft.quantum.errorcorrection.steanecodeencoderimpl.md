---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: Operace SteaneCodeEncoderImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697928"
---
# <a name="steanecodeencoderimpl-operation"></a><span data-ttu-id="0fa90-102">Operace SteaneCodeEncoderImpl</span><span class="sxs-lookup"><span data-stu-id="0fa90-102">SteaneCodeEncoderImpl operation</span></span>

<span data-ttu-id="0fa90-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="0fa90-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="0fa90-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0fa90-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0fa90-105">Soukromá operace používaná k implementaci kodéru Steane kódu i dekodéru.</span><span class="sxs-lookup"><span data-stu-id="0fa90-105">Private operation used to implement both the Steane code encoder and decoder.</span></span>

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0fa90-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="0fa90-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="0fa90-107">data: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0fa90-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0fa90-108">pole obsahující 1 qubit, což je vstupní qubit.</span><span class="sxs-lookup"><span data-stu-id="0fa90-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="0fa90-109">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0fa90-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0fa90-110">pole obsahující 6 qubits, které přidávají redundanci.</span><span class="sxs-lookup"><span data-stu-id="0fa90-110">an array holding 6 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0fa90-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0fa90-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

