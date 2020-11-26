---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: Operace EstimateEnergy
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: fb59071ed05234d4a19cd97598bf479489b9985c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214411"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="3cdfa-102">Operace EstimateEnergy</span><span class="sxs-lookup"><span data-stu-id="3cdfa-102">EstimateEnergy operation</span></span>

<span data-ttu-id="3cdfa-103">Obor názvů: [Microsoft. JordanWigner. chemie.. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="3cdfa-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="3cdfa-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="3cdfa-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="3cdfa-105">Vyhodnotí energii v molekule sečtením energie, kterou přispěly jednotlivé Jordan-Wigner podmínek.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-105">Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.</span></span>

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="3cdfa-106">Popis</span><span class="sxs-lookup"><span data-stu-id="3cdfa-106">Description</span></span>

<span data-ttu-id="3cdfa-107">Tato operace implicitně spoléhá na konvenci indexování s číselníkem.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-107">This operation implicitly relies on the spin up-down indexing convention.</span></span>

## <a name="input"></a><span data-ttu-id="3cdfa-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="3cdfa-108">Input</span></span>

### <a name="jwhamiltonian--jordanwignerencodingdata"></a><span data-ttu-id="3cdfa-109">jwHamiltonian: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="3cdfa-109">jwHamiltonian : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="3cdfa-110">Jordan-Wigner Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-110">The Jordan-Wigner Hamiltonian.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="3cdfa-111">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3cdfa-111">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3cdfa-112">Počet vzorků, které se mají použít pro odhad termínu očekávání.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-112">The number of samples to use for the estimation of the term expectations.</span></span>



## <a name="output--double"></a><span data-ttu-id="3cdfa-113">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3cdfa-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3cdfa-114">Odhadovaná energie molekuly</span><span class="sxs-lookup"><span data-stu-id="3cdfa-114">The estimated energy of the molecule</span></span>