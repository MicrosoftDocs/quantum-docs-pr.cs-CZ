---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: Operace EstimateEnergy
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: 52e527a68818c80f93bc177d3563064fd0f2aea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698373"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="411de-102">Operace EstimateEnergy</span><span class="sxs-lookup"><span data-stu-id="411de-102">EstimateEnergy operation</span></span>

<span data-ttu-id="411de-103">Obor názvů: [Microsoft. JordanWigner. chemie.. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="411de-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="411de-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="411de-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="411de-105">Vyhodnotí energii v molekule sečtením energie, kterou přispěly jednotlivé Jordan-Wigner podmínek.</span><span class="sxs-lookup"><span data-stu-id="411de-105">Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.</span></span>

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="411de-106">Popis</span><span class="sxs-lookup"><span data-stu-id="411de-106">Description</span></span>

<span data-ttu-id="411de-107">Tato operace implicitně spoléhá na konvenci indexování s číselníkem.</span><span class="sxs-lookup"><span data-stu-id="411de-107">This operation implicitly relies on the spin up-down indexing convention.</span></span>

## <a name="input"></a><span data-ttu-id="411de-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="411de-108">Input</span></span>

### <a name="jwhamiltonian--jordanwignerencodingdata"></a><span data-ttu-id="411de-109">jwHamiltonian: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="411de-109">jwHamiltonian : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="411de-110">Jordan-Wigner Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="411de-110">The Jordan-Wigner Hamiltonian.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="411de-111">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="411de-111">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="411de-112">Počet vzorků, které se mají použít pro odhad termínu očekávání.</span><span class="sxs-lookup"><span data-stu-id="411de-112">The number of samples to use for the estimation of the term expectations.</span></span>



## <a name="output--double"></a><span data-ttu-id="411de-113">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="411de-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="411de-114">Odhadovaná energie molekuly</span><span class="sxs-lookup"><span data-stu-id="411de-114">The estimated energy of the molecule</span></span>