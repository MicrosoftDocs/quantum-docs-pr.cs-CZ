---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Operace čtverečních
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: d7334d50f245ba358624e6e2eee94b63d9ed7569
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706224"
---
# <a name="squarei-operation"></a>Operace čtverečních

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček [](https://nuget.org/packages/)


Vypočítá čtverci celého čísla `xs` do `result` , které musí být zpočátku nula.

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Vstup

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bitové číslo do čtverce (LittleEndian)


### <a name="result--littleendian"></a>výsledek: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$2N $-bit výsledek (LittleEndian), musí být ve stavu $ \ket {0} $ zpočátku.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

K výpočtu čtverce používá standardní přístup Shift-and-Add. Uloží $n-$1 qubits ve srovnání s řešením přímého přeposílání, které před použitím regulárního násobitele nejdřív zkopíruje XS a potom operaci kopírování vrátí zpět.