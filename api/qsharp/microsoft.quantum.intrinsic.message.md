---
uid: Microsoft.Quantum.Intrinsic.Message
title: Funkce zprávy
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 652e33de69ffb725f117db3beeffa66558776f49
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849365"
---
# <a name="message-function"></a><span data-ttu-id="1f56f-102">Funkce zprávy</span><span class="sxs-lookup"><span data-stu-id="1f56f-102">Message function</span></span>

<span data-ttu-id="1f56f-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="1f56f-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="1f56f-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1f56f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1f56f-105">Zaznamená zprávu.</span><span class="sxs-lookup"><span data-stu-id="1f56f-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="1f56f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="1f56f-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="1f56f-107">Msg: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1f56f-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1f56f-108">Zpráva, která má být hlášena.</span><span class="sxs-lookup"><span data-stu-id="1f56f-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f56f-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f56f-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1f56f-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="1f56f-110">Remarks</span></span>

<span data-ttu-id="1f56f-111">Konkrétní chování této funkce je závislé na simulátoru, ale ve většině případů bude daná zpráva zapsána do konzoly.</span><span class="sxs-lookup"><span data-stu-id="1f56f-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>