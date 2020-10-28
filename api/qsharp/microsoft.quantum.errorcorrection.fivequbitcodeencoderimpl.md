---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Operace FiveQubitCodeEncoderImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 29b0f47ddffeae3ed4dfda4084304427418e02fd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697969"
---
# <a name="fivequbitcodeencoderimpl-operation"></a><span data-ttu-id="c665d-102">Operace FiveQubitCodeEncoderImpl</span><span class="sxs-lookup"><span data-stu-id="c665d-102">FiveQubitCodeEncoderImpl operation</span></span>

<span data-ttu-id="c665d-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c665d-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c665d-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c665d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c665d-105">Soukromá operace používaná k implementaci kodéru 5 qubit a dekodéru.</span><span class="sxs-lookup"><span data-stu-id="c665d-105">Private operation used to implement both the 5 qubit encoder and decoder.</span></span>

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c665d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c665d-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="c665d-107">data: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c665d-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c665d-108">pole obsahující 1 qubit, což je vstupní qubit.</span><span class="sxs-lookup"><span data-stu-id="c665d-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="c665d-109">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c665d-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c665d-110">pole obsahující 4 qubitsy, které přidávají redundanci.</span><span class="sxs-lookup"><span data-stu-id="c665d-110">an array holding 4 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c665d-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c665d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c665d-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c665d-112">Remarks</span></span>

<span data-ttu-id="c665d-113">Konkrétní zvolený kodér byl získán ze sady Paper V. Kliuchnikov a D. Maslov, "optimalizace okruhů Clifford", "fyz. rev. fyz. rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Obrázek 4b) a vyžaduje celkem 11 bran.</span><span class="sxs-lookup"><span data-stu-id="c665d-113">The particular encoder chosen was taken from the paper V. Kliuchnikov and D. Maslov, "Optimization of Clifford Circuits," Phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) and requires a total of 11 gates.</span></span>