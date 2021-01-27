---
uid: Microsoft.Quantum.Synthesis.Extended
title: Rozšířená funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855475"
---
# <a name="extended-function"></a><span data-ttu-id="c6a78-102">Rozšířená funkce</span><span class="sxs-lookup"><span data-stu-id="c6a78-102">Extended function</span></span>

<span data-ttu-id="c6a78-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="c6a78-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="c6a78-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c6a78-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c6a78-105">Rozšiřuje spektrum o opačné koeficienty.</span><span class="sxs-lookup"><span data-stu-id="c6a78-105">Extends a spectrum by inverted coefficients</span></span>

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="c6a78-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c6a78-106">Input</span></span>

### <a name="spectrum--int"></a><span data-ttu-id="c6a78-107">spektrum: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c6a78-107">spectrum : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c6a78-108">Spektrální koeficienty</span><span class="sxs-lookup"><span data-stu-id="c6a78-108">Spectral coefficients</span></span>



## <a name="output--int"></a><span data-ttu-id="c6a78-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c6a78-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c6a78-110">Koeficienty následované opačným kopírováním</span><span class="sxs-lookup"><span data-stu-id="c6a78-110">Coefficients followed by inverted copy</span></span>

## <a name="example"></a><span data-ttu-id="c6a78-111">Příklad</span><span class="sxs-lookup"><span data-stu-id="c6a78-111">Example</span></span>

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```