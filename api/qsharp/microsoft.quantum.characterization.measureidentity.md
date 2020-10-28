---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Operace MeasureIdentity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 71a103fddb3a27703318975bea94bc7a22a9ce81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698721"
---
# <a name="measureidentity-operation"></a>Operace MeasureIdentity

Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)

Balíček [](https://nuget.org/packages/)


Měří operátor identity v registru qubits.

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a>Vstup

### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr, který se má měřit



## <a name="output--__invalidresult__"></a>Výstup: __neplatný <Result>__

Výsledná hodnota `Zero` .

## <a name="remarks"></a>Poznámky

Vzhledem k tomu, že $ \boldone $ má pouze eigenvalue $1 $, a nemá negativní eigenvalue, tato operace vždy vrátí hodnotu `Zero` odpovídající eigenvalue $ + 1 = (-1) ^ 0 $ a nezpůsobí sbalení stavu `register` .

Sám o sobě tato operace není užitečná, ale je užitečná v kontextu procesu tomography, protože poskytuje informace o uchovávání sledování v rámci procesu.
Konkrétně cílový počítač se ztrátovou měřením by měl tuto operaci nahradit skutečným měřením $ \boldone $.