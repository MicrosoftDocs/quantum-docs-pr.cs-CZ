---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedQubitizationOracle
title: OptimizedQubitizationOracle – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedQubitizationOracle
qsharp.summary: Returns T-count optimized Qubitization operation and the parameters necessary to run it.
ms.openlocfilehash: d20fe3bfe362a94c23ec266efaebfda73d7baf82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224781"
---
# <a name="optimizedqubitizationoracle-function"></a><span data-ttu-id="dfbda-102">OptimizedQubitizationOracle – funkce</span><span class="sxs-lookup"><span data-stu-id="dfbda-102">OptimizedQubitizationOracle function</span></span>

<span data-ttu-id="dfbda-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="dfbda-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="dfbda-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="dfbda-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="dfbda-105">Vrátí Qubitizationou operaci T-Count optimalizované operace a parametry nezbytné ke spuštění.</span><span class="sxs-lookup"><span data-stu-id="dfbda-105">Returns T-count optimized Qubitization operation and the parameters necessary to run it.</span></span>

```qsharp
function OptimizedQubitizationOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, targetError : Double) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="dfbda-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="dfbda-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="dfbda-107">qSharpData: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="dfbda-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="dfbda-108">Hamiltonian popsané podle `JordanWignerEncodingData` formátu.</span><span class="sxs-lookup"><span data-stu-id="dfbda-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>


### <a name="targeterror--double"></a><span data-ttu-id="dfbda-109">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dfbda-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dfbda-110">Chyba kroku přípravy stavu auxillary</span><span class="sxs-lookup"><span data-stu-id="dfbda-110">Error of auxillary state preparation step.</span></span>



## <a name="output--intdoublequbit--unit--is-adj--ctl"></a><span data-ttu-id="dfbda-111">Výstup: ([int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL))</span><span class="sxs-lookup"><span data-stu-id="dfbda-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl))</span></span>

<span data-ttu-id="dfbda-112">Řazená kolekce členů `Int` , kde: je počet přidělených qubits, `Double` je jednou z Hamiltonian koeficientů a operace je průvodce příchodem na základě doby, kterou vytvořila Qubitization.</span><span class="sxs-lookup"><span data-stu-id="dfbda-112">A tuple where: `Int` is the number of qubits allocated, `Double` is the one-norm of Hamiltonian coefficients, and the operation is the Quantum walk created by Qubitization.</span></span>