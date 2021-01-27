---
uid: Microsoft.Quantum.Canon.IsResultZero
title: IsResultZero – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: b1e7cf6324a2a90f10b6aa93811f2df60fe3afbd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840316"
---
# <a name="isresultzero-function"></a>IsResultZero – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Testuje, zda je daná hodnota výsledku rovna `Zero` .

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a>Vstup

### <a name="input--__invalidresult__"></a>vstup: __neplatné <Result>__

`Result` hodnota, která má být testována.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

Vrátí, `true` Pokud `input` je rovno `Zero` .