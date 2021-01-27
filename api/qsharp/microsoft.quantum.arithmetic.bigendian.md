---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: Uživatelem definovaný typ BigEndian
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 2f6ec9f83ac124ce9b06c278f8fda820c35c23aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843383"
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