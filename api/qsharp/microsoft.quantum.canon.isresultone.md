---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: f259c21e6cc0a4886332e9ffcb546e527ec7def1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840332"
---
# <a name="isresultone-function"></a><span data-ttu-id="2050c-102">IsResultOne – funkce</span><span class="sxs-lookup"><span data-stu-id="2050c-102">IsResultOne function</span></span>

<span data-ttu-id="2050c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2050c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2050c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2050c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2050c-105">Testuje, zda je daná hodnota výsledku rovna `One` .</span><span class="sxs-lookup"><span data-stu-id="2050c-105">Tests if a given Result value is equal to `One`.</span></span>

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="2050c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2050c-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="2050c-107">vstup: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="2050c-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="2050c-108">`Result` hodnota, která má být testována.</span><span class="sxs-lookup"><span data-stu-id="2050c-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2050c-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2050c-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2050c-110">Vrátí, `true` Pokud `input` je rovno `One` .</span><span class="sxs-lookup"><span data-stu-id="2050c-110">Returns `true` if `input` is equal to `One`.</span></span>