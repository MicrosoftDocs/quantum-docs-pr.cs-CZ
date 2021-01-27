---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848350"
---
# <a name="realmod-function"></a><span data-ttu-id="b8a9b-102">RealMod – funkce</span><span class="sxs-lookup"><span data-stu-id="b8a9b-102">RealMod function</span></span>

<span data-ttu-id="b8a9b-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b8a9b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b8a9b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b8a9b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b8a9b-105">Vypočítá zbytky mezi dvěma reálnými čísly.</span><span class="sxs-lookup"><span data-stu-id="b8a9b-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="b8a9b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="b8a9b-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="b8a9b-107">hodnota: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b8a9b-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b8a9b-108">Reálné číslo $x $, kde se pobírají zbytky.</span><span class="sxs-lookup"><span data-stu-id="b8a9b-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="b8a9b-109">modulo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b8a9b-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b8a9b-110">Reálné číslo, které má převzít modul $x $ s ohledem na.</span><span class="sxs-lookup"><span data-stu-id="b8a9b-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="b8a9b-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b8a9b-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b8a9b-112">Nejmenší hodnota, kterou má tato funkce vrátit.</span><span class="sxs-lookup"><span data-stu-id="b8a9b-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="b8a9b-113">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b8a9b-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="example"></a><span data-ttu-id="b8a9b-114">Příklad</span><span class="sxs-lookup"><span data-stu-id="b8a9b-114">Example</span></span>

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a><span data-ttu-id="b8a9b-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b8a9b-115">Remarks</span></span>

<span data-ttu-id="b8a9b-116">Tato funkce vypočítá reálné zbytky tím, že zabalí skutečnou čáru o kružnici jednotky a pak vyhledá úhel v kruhu jednotky odpovídající vstupu.</span><span class="sxs-lookup"><span data-stu-id="b8a9b-116">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="b8a9b-117">`minValue`Vstup pak efektivně určuje, kde se má vyjmout kruh jednotky.</span><span class="sxs-lookup"><span data-stu-id="b8a9b-117">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>