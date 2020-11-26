---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ccef1bbf400e01800053777d0010acb7addaef53
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192481"
---
# <a name="quantumwalkbyqubitization-function"></a><span data-ttu-id="e5968-102">QuantumWalkByQubitization – funkce</span><span class="sxs-lookup"><span data-stu-id="e5968-102">QuantumWalkByQubitization function</span></span>

<span data-ttu-id="e5968-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e5968-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e5968-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e5968-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e5968-105">Převede reflexi kódování bloku na Projděte.</span><span class="sxs-lookup"><span data-stu-id="e5968-105">Converts a block-encoding reflection into a quantum walk.</span></span>

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="e5968-106">Popis</span><span class="sxs-lookup"><span data-stu-id="e5968-106">Description</span></span>

<span data-ttu-id="e5968-107">V případě `BlockEncodingReflection` , že se jedná o $U $, který kóduje některý operátor $H $ zájmu, převede ho na přejíždění do doby, $W $ obsahující spektrum $ \Pm e ^ {\Pm i\sin ^ {-1} (H)} $.</span><span class="sxs-lookup"><span data-stu-id="e5968-107">Given a `BlockEncodingReflection` represented by a unitary $U$ that encodes some operator $H$ of interest, converts it into a quantum walk $W$ containing the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="input"></a><span data-ttu-id="e5968-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="e5968-108">Input</span></span>

### <a name="blockencoding--blockencodingreflection"></a><span data-ttu-id="e5968-109">blockEncoding: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="e5968-109">blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="e5968-110">`BlockEncodingReflection`Jednotková $U $, která se má převést na Průvodce příjížděním</span><span class="sxs-lookup"><span data-stu-id="e5968-110">A `BlockEncodingReflection` unitary $U$ to be converted into a Quantum walk.</span></span>



## <a name="output--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="e5968-111">Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="e5968-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e5968-112">$W $ pracuje společně na registrech `a` a `s` zablokuje $H $ a obsahuje spektrum $ \Pm e ^ {\Pm i\sin ^ {-1} (H)} $.</span><span class="sxs-lookup"><span data-stu-id="e5968-112">A quantum walk $W$ acting jointly on registers `a` and `s` that block- encodes $H$, and contains the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="references"></a><span data-ttu-id="e5968-113">Reference</span><span class="sxs-lookup"><span data-stu-id="e5968-113">References</span></span>

- <span data-ttu-id="e5968-114">Simulace Hamiltonian podle Qubitization Guang vystoupí hao nízká, Petr L. Čuangština https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="e5968-114">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="e5968-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="e5968-115">See Also</span></span>

- [<span data-ttu-id="e5968-116">Microsoft. v. simulace. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="e5968-116">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="e5968-117">Microsoft. v. simulace. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="e5968-117">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)