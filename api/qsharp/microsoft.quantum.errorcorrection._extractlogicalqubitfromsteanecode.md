---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: Operace _ExtractLogicalQubitFromSteaneCode
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: 273692efa629cb8cc20069ef500c4e0902fbc3ff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201338"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a>Operace _ExtractLogicalQubitFromSteaneCode

Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Syndrome měření a inverzní funkce pro vkládání.

$X $-a $Z $-stabilizátory se nepovažují za stejné, což je kvůli konkrétní volbě okruhu kódování.
Tato asymetrie vede k jiné rutině extrakce Syndrome.
Jedním z nich může změřit Syndrome pomocí měření qubit Pauli operátora přímo ve stavu kódu, ale pro účely destilace se logické qubit vrátí do jednoho qubit, v případě, že se Syndrome měření dá provést bez dalšího ancillas.

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a>Vstup

### <a name="code--logicalregister"></a>kód: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)





## <a name="output--qubitintint"></a>Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))

Logický qubit a dvojice celých čísel pro $X $-Syndrome a $Z $-Syndrome.
Představují index qubit kódu, na kterém by jedna $X $-nebo $Z $-Error způsobila měřený Syndrome.

## <a name="remarks"></a>Poznámky

Všimněte si, že tato operace není označena jako `internal` , protože testy jednotek přímo závisejí na této operaci. V rámci budoucího zlepšení by testy jednotek měly být refaktorované, aby závislé jenom na veřejných volatcích.

> [!WARNING]
> Tato rutina je přizpůsobená konkrétnímu okruhu kódování pro qubit kód Steane. Pokud se změní okruh kódování, může být výsledek Syndrome vyhodnocen jinak.