---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: Operace SingleQubitProcessTomographyMeasurement
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 883b98ad4f2d0ac4a02e55e444c04e8e7cf37af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839640"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a>Operace SingleQubitProcessTomographyMeasurement

Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Provede qubit proces tomography měření v Pauli, a to s ohledem na konkrétní kanál zájmu.

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a>Vstup

### <a name="preparation--pauli"></a>Příprava: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Základní element Pauli $P $, ve kterém má být připraven qubit.


### <a name="measurement--pauli"></a>měření: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Základní element Pauli $Q $, ve kterém se má měřit qubit.


### <a name="channel--qubit--unit"></a>kanál: [](xref:microsoft.quantum.lang-ref.qubit) => [jednotka](xref:microsoft.quantum.lang-ref.unit) qubit 

Jeden qubit kanál $ \Lambda $, jehož chování se odhaduje pomocí procesu tomography.



## <a name="output--__invalidresult__"></a>Výstup: __neplatný <Result>__

Výsledek `Zero` s pravděpodobností $ $ \Begin{align} \Pr (\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left (\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right).
\end{align} $ $

## <a name="remarks"></a>Poznámky

Distribuce výsledků vrácená touto operací je zvláštní případ qubit tomography stavu. Nechť $ \rho = J (\Lambda)/$2 být stav Choi – Jamiłkowski pro $ \Lambda $. Výše uvedená distribuce je stejná jako u $ $ \begin{align} \Pr (\texttt{Zero} | \rho; M) = \operatorname{Tr} (M \rho); \end{align} $ $ WHERE $M = 2 (\boldone + P) ^ \mathrm{T}/2 \cdot (\boldone + Q)/$2 je efektivní měření odpovídající $P $ a $Q $.