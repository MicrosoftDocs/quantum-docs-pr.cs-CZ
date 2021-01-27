---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: a48f056d138499607d32b38b1fa0970745732c41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851342"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="d950f-102">IsCoprimeL – funkce</span><span class="sxs-lookup"><span data-stu-id="d950f-102">IsCoprimeL function</span></span>

<span data-ttu-id="d950f-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d950f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d950f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d950f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d950f-105">Vrátí hodnotu true, pokud $a $ a $b $ jsou souběžné a false v opačném případě.</span><span class="sxs-lookup"><span data-stu-id="d950f-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="d950f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d950f-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="d950f-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d950f-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d950f-108">první počet primality, které se testují společně</span><span class="sxs-lookup"><span data-stu-id="d950f-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="d950f-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d950f-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d950f-110">druhý počet, který provádí testování primality</span><span class="sxs-lookup"><span data-stu-id="d950f-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="d950f-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d950f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d950f-112">True, pokud $a $ a $b $ jsou souběžné (například jejich největší společný dělitel je 1) a jinak false</span><span class="sxs-lookup"><span data-stu-id="d950f-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>