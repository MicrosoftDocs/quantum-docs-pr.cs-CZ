---
uid: Microsoft.Quantum.Core.Deprecated
title: Zastaralý uživatelem definovaný typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 122cbc113a68cec107558d68a6fb145cf6bbd9db
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224084"
---
# <a name="deprecated-user-defined-type"></a>Zastaralý uživatelem definovaný typ

Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Atribut rozpoznaný kompilátorem, který slouží k označení typu nebo k jeho vyžádání jako zastaralé.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>Pojmenované položky

### <a name="newname--string"></a>Nový_název: [řetězec](xref:microsoft.quantum.lang-ref.string)

Úplný název typu nebo volat, který se má použít.
Je nastaven na prázdný řetězec, pokud je typ nebo možné použití zastaralá bez substituce.