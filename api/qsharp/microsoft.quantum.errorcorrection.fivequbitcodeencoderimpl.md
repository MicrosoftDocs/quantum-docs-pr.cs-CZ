---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Operace FiveQubitCodeEncoderImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 0a40d9674c011567b2fa9c838f31a0ee115e4268
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826087"
---
# <a name="fivequbitcodeencoderimpl-operation"></a><span data-ttu-id="539d9-102">Operace FiveQubitCodeEncoderImpl</span><span class="sxs-lookup"><span data-stu-id="539d9-102">FiveQubitCodeEncoderImpl operation</span></span>

<span data-ttu-id="539d9-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="539d9-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="539d9-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="539d9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="539d9-105">Soukromá operace používaná k implementaci kodéru 5 qubit a dekodéru.</span><span class="sxs-lookup"><span data-stu-id="539d9-105">Private operation used to implement both the 5 qubit encoder and decoder.</span></span>

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="539d9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="539d9-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="539d9-107">data: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="539d9-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="539d9-108">pole obsahující 1 qubit, což je vstupní qubit.</span><span class="sxs-lookup"><span data-stu-id="539d9-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="539d9-109">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="539d9-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="539d9-110">pole obsahující 4 qubitsy, které přidávají redundanci.</span><span class="sxs-lookup"><span data-stu-id="539d9-110">an array holding 4 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="539d9-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="539d9-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="539d9-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="539d9-112">Remarks</span></span>

<span data-ttu-id="539d9-113">Konkrétní zvolený kodér byl získán ze sady Paper V. Kliuchnikov a D. Maslov, "optimalizace okruhů Clifford", "fyz. rev. fyz. rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Obrázek 4b) a vyžaduje celkem 11 bran.</span><span class="sxs-lookup"><span data-stu-id="539d9-113">The particular encoder chosen was taken from the paper V. Kliuchnikov and D. Maslov, "Optimization of Clifford Circuits," Phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) and requires a total of 11 gates.</span></span>