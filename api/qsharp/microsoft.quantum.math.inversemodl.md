---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e7cb9e98cb0635c50162611f6a52c56027d4a5eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708493"
---
# <a name="inversemodl-function"></a><span data-ttu-id="0e3b4-102">InverseModL – funkce</span><span class="sxs-lookup"><span data-stu-id="0e3b4-102">InverseModL function</span></span>

<span data-ttu-id="0e3b4-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0e3b4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0e3b4-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0e3b4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0e3b4-105">Vrátí $b $ tak, že $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="0e3b4-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="0e3b4-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="0e3b4-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="0e3b4-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0e3b4-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0e3b4-108">Počet, který se obrátí</span><span class="sxs-lookup"><span data-stu-id="0e3b4-108">The number being inverted</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="0e3b4-109">Modulus: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0e3b4-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0e3b4-110">Zbytek v závislosti na tom, které hodnoty jsou obráceny</span><span class="sxs-lookup"><span data-stu-id="0e3b4-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--bigint"></a><span data-ttu-id="0e3b4-111">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0e3b4-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0e3b4-112">Integer $b $, což $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="0e3b4-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>