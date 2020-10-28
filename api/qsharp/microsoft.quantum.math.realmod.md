---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706800"
---
# <a name="realmod-function"></a>RealMod – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček [](https://nuget.org/packages/)


Vypočítá zbytky mezi dvěma reálnými čísly.

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a>Vstup

### <a name="value--double"></a>hodnota: [Double](xref:microsoft.quantum.lang-ref.double)

Reálné číslo $x $, kde se pobírají zbytky.


### <a name="modulo--double"></a>modulo: [Double](xref:microsoft.quantum.lang-ref.double)

Reálné číslo, které má převzít modul $x $ s ohledem na.


### <a name="minvalue--double"></a>minValue: [Double](xref:microsoft.quantum.lang-ref.double)

Nejmenší hodnota, kterou má tato funkce vrátit.



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Poznámky

Tato funkce vypočítá reálné zbytky tím, že zabalí skutečnou čáru o kružnici jednotky a pak vyhledá úhel v kruhu jednotky odpovídající vstupu.
`minValue`Vstup pak efektivně určuje, kde se má vyjmout kruh jednotky.