---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: Operace ApplyBitFlipEncoder
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: e56e84effa001f104bbd5e28e7181dbd39a4cf5e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201287"
---
# <a name="applybitflipencoder-operation"></a><span data-ttu-id="cd4ad-102">Operace ApplyBitFlipEncoder</span><span class="sxs-lookup"><span data-stu-id="cd4ad-102">ApplyBitFlipEncoder operation</span></span>

<span data-ttu-id="cd4ad-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="cd4ad-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="cd4ad-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cd4ad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cd4ad-105">Soukromá operace používaná k implementaci kodéru překlápění i dekodéru.</span><span class="sxs-lookup"><span data-stu-id="cd4ad-105">Private operation used to implement both the bit flip encoder and decoder.</span></span>

<span data-ttu-id="cd4ad-106">Uvědomte si, že tento kodér může využít místní soudržné obnovení. v takovém případě bude "příčinou" Chyba, která je popsána v počátečním stavu `auxQubits` .</span><span class="sxs-lookup"><span data-stu-id="cd4ad-106">Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`.</span></span>
<span data-ttu-id="cd4ad-107">Zejména pokud `auxQubits` jsou ve stavu "$ \ket $" na začátku {10} , $X způsobí to, že se na kódovaném qubit zobrazí chyba _1 $.</span><span class="sxs-lookup"><span data-stu-id="cd4ad-107">In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.</span></span>

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="cd4ad-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="cd4ad-108">Input</span></span>

### <a name="coherentrecovery--bool"></a><span data-ttu-id="cd4ad-109">coherentRecovery: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cd4ad-109">coherentRecovery : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="data--qubit"></a><span data-ttu-id="cd4ad-110">data: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cd4ad-110">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="scratch--qubit"></a><span data-ttu-id="cd4ad-111">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cd4ad-111">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="cd4ad-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cd4ad-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="cd4ad-113">Reference</span><span class="sxs-lookup"><span data-stu-id="cd4ad-113">References</span></span>

- <span data-ttu-id="cd4ad-114">doi:10.1103/PhysRevA.85.044302</span><span class="sxs-lookup"><span data-stu-id="cd4ad-114">doi:10.1103/PhysRevA.85.044302</span></span>