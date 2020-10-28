---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Operace PrepareIdentity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: a3f96fbdafb19c90fb2b563243600cca60841566
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709033"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="9b25c-102">Operace PrepareIdentity</span><span class="sxs-lookup"><span data-stu-id="9b25c-102">PrepareIdentity operation</span></span>

<span data-ttu-id="9b25c-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="9b25c-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="9b25c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9b25c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9b25c-105">V případě registru připraví tento registr do smíšeného stavu.</span><span class="sxs-lookup"><span data-stu-id="9b25c-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="9b25c-106">Registr se připravuje ve stavu $ \boldone/2 ^ N $ tím, že použije kompletní kanál depolarizing na každou qubit, kde $N $ je délka registru.</span><span class="sxs-lookup"><span data-stu-id="9b25c-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9b25c-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="9b25c-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="9b25c-108">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9b25c-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9b25c-109">Registr, jehož stav má být depolarizace způsobem popsaným výše.</span><span class="sxs-lookup"><span data-stu-id="9b25c-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9b25c-110">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b25c-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="9b25c-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="9b25c-111">See Also</span></span>

- [<span data-ttu-id="9b25c-112">Microsoft. Přípravno. Preparation. PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="9b25c-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)