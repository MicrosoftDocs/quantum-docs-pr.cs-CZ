---
uid: Microsoft.Quantum.Canon.IsResultZero
title: IsResultZero – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: 790551690cfba42df4cf7aa77e53e303050bdf39
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704089"
---
# <a name="isresultzero-function"></a>IsResultZero – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Testuje, zda je daná hodnota výsledku rovna `Zero` .

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a>Vstup

### <a name="input--__invalidresult__"></a>vstup: __neplatné <Result>__

`Result` hodnota, která má být testována.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

Vrátí, `true` Pokud `input` je rovno `Zero` .