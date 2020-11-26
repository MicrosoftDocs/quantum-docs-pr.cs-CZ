---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: Uživatelem definovaný typ BigEndian
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 8ea1aefa46a7224ef199baf68f2d6ab2d563e3a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223659"
---
# <a name="bigendian-user-defined-type"></a>Uživatelem definovaný typ BigEndian

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zaregistrujte, aby se v pořadí big-endian zakódují unsigned integer. Qubit s indexem `0` kóduje nejvyšší bit unsigned integer.

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a>Poznámky

V dokumentaci se zkrátí `BigEndian` `BE` .