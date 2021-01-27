---
uid: Microsoft.Quantum.Math.PowC
title: PowC – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowC
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: 7dbadbd4c3cc16c3fa0bcd9b5b1acbee990e24ac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846821"
---
# <a name="powc-function"></a><span data-ttu-id="f7390-102">PowC – funkce</span><span class="sxs-lookup"><span data-stu-id="f7390-102">PowC function</span></span>

<span data-ttu-id="f7390-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f7390-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f7390-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f7390-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f7390-105">Vrátí číslo umocněné na daný příkon.</span><span class="sxs-lookup"><span data-stu-id="f7390-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowC (a : Microsoft.Quantum.Math.Complex, power : Microsoft.Quantum.Math.Complex) : Microsoft.Quantum.Math.Complex
```


## <a name="input"></a><span data-ttu-id="f7390-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f7390-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="f7390-107">a: [komplexní](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="f7390-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="f7390-108">Číslo $a $, které má být vyvoláno.</span><span class="sxs-lookup"><span data-stu-id="f7390-108">The number $a$ that is to be raised.</span></span>


### <a name="power--complex"></a><span data-ttu-id="f7390-109">výkon: [komplexní](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="f7390-109">power : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="f7390-110">$B pro napájení, na které $a $ má být vyvoláno.</span><span class="sxs-lookup"><span data-stu-id="f7390-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--complex"></a><span data-ttu-id="f7390-111">Výstup: [komplexní](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="f7390-111">Output : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="f7390-112">$a napájení ^ b $</span><span class="sxs-lookup"><span data-stu-id="f7390-112">The power $a^b$</span></span>