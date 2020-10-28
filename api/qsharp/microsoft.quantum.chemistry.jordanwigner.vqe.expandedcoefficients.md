---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 8f5a2319b5839d0d9e47972389330dc16dffcaf0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698364"
---
# <a name="expandedcoefficients-function"></a><span data-ttu-id="8b3ec-102">ExpandedCoefficients – funkce</span><span class="sxs-lookup"><span data-stu-id="8b3ec-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="8b3ec-103">Obor názvů: [Microsoft. JordanWigner. chemie.. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="8b3ec-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="8b3ec-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8b3ec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8b3ec-105">Rozbalí kompaktní reprezentace Jordan-Wignerných koeficientů, aby bylo možné získat mapování 1:1 mezi těmito a Pauli podmínkami.</span><span class="sxs-lookup"><span data-stu-id="8b3ec-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="8b3ec-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8b3ec-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="8b3ec-107">coeff: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="8b3ec-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="8b3ec-108">Pole koeficientů, které je čteno z Jordan-Wigner struktury dat Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="8b3ec-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="8b3ec-109">termType: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8b3ec-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8b3ec-110">Typ Jordan-Wigner podmínky.</span><span class="sxs-lookup"><span data-stu-id="8b3ec-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="8b3ec-111">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="8b3ec-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="8b3ec-112">Rozšířená pole koeficientů, jedna na Pauli termín.</span><span class="sxs-lookup"><span data-stu-id="8b3ec-112">Expanded arrays of coefficients, one per Pauli term.</span></span>