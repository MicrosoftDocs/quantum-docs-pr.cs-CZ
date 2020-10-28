---
uid: Microsoft.Quantum.Diagnostics.Test
title: Typ uživatelem definovaného testu
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 8030f6378ac0cb393c7ed2b9e636a7561e8943a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698057"
---
# <a name="test-user-defined-type"></a>Typ uživatelem definovaného testu

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček [](https://nuget.org/packages/)


Atribut rozpoznaný kompilátorem, který slouží k označení testu jednotky.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a>Pojmenované položky

### <a name="executiontarget--string"></a>ExecutionTarget: [řetězec](xref:microsoft.quantum.lang-ref.string)

