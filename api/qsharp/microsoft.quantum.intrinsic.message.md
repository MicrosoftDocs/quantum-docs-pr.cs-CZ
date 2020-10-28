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
# <a name="message-function"></a>Funkce zprávy

Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)

Balíček [](https://nuget.org/packages/)


Zaznamená zprávu.

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a>Vstup

### <a name="msg--string"></a>Msg: [řetězec](xref:microsoft.quantum.lang-ref.string)

Zpráva, která má být hlášena.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Konkrétní chování této funkce je závislé na simulátoru, ale ve většině případů bude daná zpráva zapsána do konzoly.