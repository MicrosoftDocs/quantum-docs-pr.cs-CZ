---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: Operace ApplyUnitary
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859162"
---
# <a name="applyunitary-operation"></a>Operace ApplyUnitary

Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použije bránu definovanou 2 ^ n × 2 ^ n jednotkovou maticí.

Pokud matice není Jednotková nebo má nesprávnou velikost, dojde k chybě.

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="unitary--complex"></a>jednotná: [komplexní](xref:Microsoft.Quantum.Math.Complex)[] []

2 ^ n × 2 ^ n Jednotková matice popisující operaci.
Pokud matice není Jednotková nebo vhodná velikost, vyvolá výjimku.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubits, na které se má použít Registry Operations-Registry n.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

