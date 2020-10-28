---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706800"
---
# <a name="realmod-function"></a><span data-ttu-id="cd83d-102">RealMod – funkce</span><span class="sxs-lookup"><span data-stu-id="cd83d-102">RealMod function</span></span>

<span data-ttu-id="cd83d-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="cd83d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="cd83d-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cd83d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cd83d-105">Vypočítá zbytky mezi dvěma reálnými čísly.</span><span class="sxs-lookup"><span data-stu-id="cd83d-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="cd83d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="cd83d-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="cd83d-107">hodnota: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cd83d-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cd83d-108">Reálné číslo $x $, kde se pobírají zbytky.</span><span class="sxs-lookup"><span data-stu-id="cd83d-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="cd83d-109">modulo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cd83d-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cd83d-110">Reálné číslo, které má převzít modul $x $ s ohledem na.</span><span class="sxs-lookup"><span data-stu-id="cd83d-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="cd83d-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cd83d-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cd83d-112">Nejmenší hodnota, kterou má tato funkce vrátit.</span><span class="sxs-lookup"><span data-stu-id="cd83d-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="cd83d-113">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cd83d-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="cd83d-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="cd83d-114">Remarks</span></span>

<span data-ttu-id="cd83d-115">Tato funkce vypočítá reálné zbytky tím, že zabalí skutečnou čáru o kružnici jednotky a pak vyhledá úhel v kruhu jednotky odpovídající vstupu.</span><span class="sxs-lookup"><span data-stu-id="cd83d-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="cd83d-116">`minValue`Vstup pak efektivně určuje, kde se má vyjmout kruh jednotky.</span><span class="sxs-lookup"><span data-stu-id="cd83d-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>