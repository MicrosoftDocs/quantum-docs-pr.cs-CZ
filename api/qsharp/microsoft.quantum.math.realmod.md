---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228249"
---
# <a name="realmod-function"></a>RealMod – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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