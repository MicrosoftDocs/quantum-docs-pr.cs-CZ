---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228249"
---
# <a name="realmod-function"></a><span data-ttu-id="fc827-102">RealMod – funkce</span><span class="sxs-lookup"><span data-stu-id="fc827-102">RealMod function</span></span>

<span data-ttu-id="fc827-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="fc827-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="fc827-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc827-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fc827-105">Vypočítá zbytky mezi dvěma reálnými čísly.</span><span class="sxs-lookup"><span data-stu-id="fc827-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="fc827-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="fc827-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="fc827-107">hodnota: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fc827-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fc827-108">Reálné číslo $x $, kde se pobírají zbytky.</span><span class="sxs-lookup"><span data-stu-id="fc827-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="fc827-109">modulo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fc827-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fc827-110">Reálné číslo, které má převzít modul $x $ s ohledem na.</span><span class="sxs-lookup"><span data-stu-id="fc827-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="fc827-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fc827-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fc827-112">Nejmenší hodnota, kterou má tato funkce vrátit.</span><span class="sxs-lookup"><span data-stu-id="fc827-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="fc827-113">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fc827-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="fc827-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="fc827-114">Remarks</span></span>

<span data-ttu-id="fc827-115">Tato funkce vypočítá reálné zbytky tím, že zabalí skutečnou čáru o kružnici jednotky a pak vyhledá úhel v kruhu jednotky odpovídající vstupu.</span><span class="sxs-lookup"><span data-stu-id="fc827-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="fc827-116">`minValue`Vstup pak efektivně určuje, kde se má vyjmout kruh jednotky.</span><span class="sxs-lookup"><span data-stu-id="fc827-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>