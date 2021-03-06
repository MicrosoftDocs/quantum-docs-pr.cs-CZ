---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Operace MeasureIdentity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: f8cf5975ac9407e8c532ace08455a41d3c08d6f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851815"
---
# <a name="measureidentity-operation"></a>Operace MeasureIdentity

Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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