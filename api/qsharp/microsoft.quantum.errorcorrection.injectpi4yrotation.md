---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: Operace InjectPi4YRotation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 249c347c9e9729e719eda69e4e9a21847d9a46eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825947"
---
# <a name="injectpi4yrotation-operation"></a>Operace InjectPi4YRotation

Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Otočí jeden qubit o π/4 o ose Y.

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a>Popis

Provede rotaci π/4 o `Y` .

Rotace se provádí spotřebou Magic State; To znamená, že kopie stavu $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} .
\end{align} $ $

## <a name="input"></a>Vstup

### <a name="data--qubit"></a>data: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, který se má otočit o $Y $ by $ \pi/$4.


### <a name="magic--qubit"></a>Magic: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit je zpočátku ve stavu Magic. Po provedení této operace `magic` se vrátí do stavu $ \ket {0} $.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Následují ekvivalenty:

```qsharp
Ry(PI() / 4.0, data);
```

a

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

Tato operace podporuje `Adjoint` funktor. v takovém případě se používá stejný stav Magic, ale vlivem na data qubit je rotace $-\ PI/4 $ $Y $-.