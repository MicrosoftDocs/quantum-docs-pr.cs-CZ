---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: Uživatelem definovaný typ BigEndian
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 64590606f7c36e0598a9d29c5c6a7ba6d6451aa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707433"
---
# <a name="bigendian-user-defined-type"></a>Uživatelem definovaný typ BigEndian

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček [](https://nuget.org/packages/)


Zaregistrujte, aby se v pořadí big-endian zakódují unsigned integer. Qubit s indexem `0` kóduje nejvyšší bit unsigned integer.

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a>Poznámky

V dokumentaci se zkrátí `BigEndian` `BE` .