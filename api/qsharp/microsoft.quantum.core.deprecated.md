---
uid: Microsoft.Quantum.Core.Deprecated
title: Zastaralý uživatelem definovaný typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: b1fcae9647b2a655d25773386ecffa826515516e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698237"
---
# <a name="deprecated-user-defined-type"></a>Zastaralý uživatelem definovaný typ

Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)

Balíček [](https://nuget.org/packages/)


Atribut rozpoznaný kompilátorem, který slouží k označení typu nebo k jeho vyžádání jako zastaralé.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>Pojmenované položky

### <a name="newname--string"></a>Nový_název: [řetězec](xref:microsoft.quantum.lang-ref.string)

Úplný název typu nebo volat, který se má použít.
Je nastaven na prázdný řetězec, pokud je typ nebo možné použití zastaralá bez substituce.