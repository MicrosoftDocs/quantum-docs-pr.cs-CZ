---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848350"
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



## <a name="example"></a>Příklad

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a>Poznámky

Tato funkce vypočítá reálné zbytky tím, že zabalí skutečnou čáru o kružnici jednotky a pak vyhledá úhel v kruhu jednotky odpovídající vstupu.
`minValue`Vstup pak efektivně určuje, kde se má vyjmout kruh jednotky.