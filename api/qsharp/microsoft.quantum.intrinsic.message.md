---
uid: Microsoft.Quantum.Intrinsic.Message
title: Funkce zprávy
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 0428a46bc639bc8a0697f5bd392f85b8b9f40ee5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697709"
---
# <a name="message-function"></a><span data-ttu-id="deed3-102">Funkce zprávy</span><span class="sxs-lookup"><span data-stu-id="deed3-102">Message function</span></span>

<span data-ttu-id="deed3-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="deed3-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="deed3-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="deed3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="deed3-105">Zaznamená zprávu.</span><span class="sxs-lookup"><span data-stu-id="deed3-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="deed3-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="deed3-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="deed3-107">Msg: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="deed3-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="deed3-108">Zpráva, která má být hlášena.</span><span class="sxs-lookup"><span data-stu-id="deed3-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="deed3-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="deed3-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="deed3-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="deed3-110">Remarks</span></span>

<span data-ttu-id="deed3-111">Konkrétní chování této funkce je závislé na simulátoru, ale ve většině případů bude daná zpráva zapsána do konzoly.</span><span class="sxs-lookup"><span data-stu-id="deed3-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>