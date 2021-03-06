---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: 8ffb6eb77a3f910d3064c4a3c90215d5d9a694aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851058"
---
# <a name="quantumwalkbyqubitization-function"></a>QuantumWalkByQubitization – funkce

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Převede reflexi kódování bloku na Projděte.

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a>Popis

V případě `BlockEncodingReflection` , že se jedná o $U $, který kóduje některý operátor $H $ zájmu, převede ho na přejíždění do doby, $W $ obsahující spektrum $ \Pm e ^ {\Pm i\sin ^ {-1} (H)} $.

## <a name="input"></a>Vstup

### <a name="blockencoding--blockencodingreflection"></a>blockEncoding: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

`BlockEncodingReflection`Jednotková $U $, která se má převést na Průvodce příjížděním



## <a name="output--qubitqubit--unit--is-adj--ctl"></a>Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

$W $ pracuje společně na registrech `a` a `s` zablokuje $H $ a obsahuje spektrum $ \Pm e ^ {\Pm i\sin ^ {-1} (H)} $.

## <a name="references"></a>Reference

- Simulace Hamiltonian podle Qubitization Guang vystoupí hao nízká, Petr L. Čuangština https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Viz také

- [Microsoft. v. simulace. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. v. simulace. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)