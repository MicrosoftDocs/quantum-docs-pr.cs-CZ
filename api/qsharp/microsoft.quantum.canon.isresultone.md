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
# <a name="isresultone-function"></a>IsResultOne – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Testuje, zda je daná hodnota výsledku rovna `One` .

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a>Vstup

### <a name="input--__invalidresult__"></a>vstup: __neplatné <Result>__

`Result` hodnota, která má být testována.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

Vrátí, `true` Pokud `input` je rovno `One` .