---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: Operace ApplyPermutationUsingDecomposition
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 765b6d301363021f5b57a22f90e2ada38c9c09ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857394"
---
# <a name="applypermutationusingdecomposition-operation"></a>Operace ApplyPermutationUsingDecomposition

Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Permutes amplitudy ve stavu, který má za následek permutaci s využitím syntézy založené na dekompozici.

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Tento postup implementuje postup syntézy založený na dekompozici.  Vstup je permutace $ \pi $ over $2 ^ n $ elementy $ \{ 0, \dots, 2 ^ n-1 \} $, které představují funkci $n $-Variable vratné logické hodnoty.
Algoritmus iterativní provede následující kroky pro každý index proměnné $i $:

1. COMPUTE $ ((\ pi_l, \ pi_r), \pi ') $ tím, že obrázky $ \ pi_l $ a $ \ pi_r $ nemění bity ve svých prvcích v jiných rejstřících než $i $ a image $ \pi $ nemění bitovou $i $ ve svých prvcích.
2. Nastavte $ \pi \leftarrow \pi ' $ a odvodit pravdy tabulky z $ \ pi_l $ a $ \ pi_r $ na základě prvků, které nejsou pevnými body.

Po použití těchto kroků u všech indexů proměnných bude zbývající permutace $ \pi $ identita a na základě shromážděných tabulek a indexů pravdy může jedna použít operace kontrolované v tabulce s @"microsoft.quantum.intrinsic.x" použitím této @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operace.

Proměnná pořadí je $0, \dots, n-$1.  V operaci lze zadat vlastní proměnnou pořadí @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .

## <a name="input"></a>Vstup

### <a name="perm--int"></a>Perm: [int](xref:microsoft.quantum.lang-ref.int)[]

Permutace prvků $2 ^ n $ počínaje 0.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Seznam $n $ qubits, na který se aplikuje permutace



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Příklad

Pro syntetizaci `SWAP` operace:

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecomposition([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a>Reference

- [*Alexis de Vos*, *Yvan van Rentergem*, ADV. v Math. of comm. 2 (2), 2008, PP. 183--200](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [*Mathias Soeken*, *Laura Tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, deník symbolického výpočtu 73 (2016), PP. 1--26](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a>Viz také

- [Microsoft. proshrnutí. ApplyPermutationUsingDecompositionWithVariableOrder](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [Microsoft. proshrnutí. ApplyPermutationUsingTransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)