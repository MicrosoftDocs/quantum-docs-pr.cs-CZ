---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: Operace AssertOperationsEqualReferenced
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: 045f00a720e9f4d2e6993c66ace44a81e192ff30
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853468"
---
# <a name="assertoperationsequalreferenced-operation"></a>Operace AssertOperationsEqualReferenced

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Tyto dvě operace vyhodnotí, že jsou identické pro všechny vstupní stavy.

Tento kontrolní výraz je implementován pomocí Choi – Jamiołkowski isomorphism k omezení kontrolního výrazu na jeden z kontrolního výrazu qubit ve dvou registrech entangled.
Proto tato operace potřebuje pouze jedno volání každé testované operace, ale vyžaduje, aby bylo přiděleno více qubits.
Tento kontrolní výraz lze použít k zajištění toho, aby Optimalizovaná verze operace se shoduje s jeho implementací Naive nebo aby operace, která funguje na řadě nestránkovaného řetězce, souhlasila se známými případy.

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Vstup

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits, které se mají předat každé operaci


### <a name="actual--qubit--unit"></a>skutečnost: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace, která se má testovat


### <a name="expected--qubit--unit--is-adj"></a>očekáváno: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace definující očekávané chování testované operace.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Tato operace vyžaduje, aby byla operace modelování očekávaného chování sousední, aby bylo možné provést invertování pouze v cílovém registru.
Jedna z nich může určit operaci transpozice, která tento požadavek zmírnit, ale operace transpozice není obecně fyzicky určena pro libovolné operace, a proto zde není obsažena jako možnost.