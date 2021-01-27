---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848213"
---
# <a name="squarednorm-function"></a><span data-ttu-id="fc793-102">SquaredNorm – funkce</span><span class="sxs-lookup"><span data-stu-id="fc793-102">SquaredNorm function</span></span>

<span data-ttu-id="fc793-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="fc793-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="fc793-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc793-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fc793-105">Vrátí čtvercovou 2-normu vektoru.</span><span class="sxs-lookup"><span data-stu-id="fc793-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="fc793-106">Popis</span><span class="sxs-lookup"><span data-stu-id="fc793-106">Description</span></span>

<span data-ttu-id="fc793-107">Vrátí čtvercovou 2-normu vektoru; To znamená, že zadané zadáním $ \vec{x} $ vrátí $ \ sum_i x_i ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="fc793-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="fc793-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="fc793-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="fc793-109">Array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="fc793-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="fc793-110">Vektor, jehož čtvercová 2-norma se má vrátit.</span><span class="sxs-lookup"><span data-stu-id="fc793-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="fc793-111">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fc793-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fc793-112">Druhá 2 – norma `array` .</span><span class="sxs-lookup"><span data-stu-id="fc793-112">The squared 2-norm of `array`.</span></span>