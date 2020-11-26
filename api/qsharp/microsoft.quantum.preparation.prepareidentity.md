---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Operace PrepareIdentity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: 6e0a43e61e3c49edef94db63f07ed29132d84c83
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210433"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="62179-102">Operace PrepareIdentity</span><span class="sxs-lookup"><span data-stu-id="62179-102">PrepareIdentity operation</span></span>

<span data-ttu-id="62179-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="62179-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="62179-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="62179-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="62179-105">V případě registru připraví tento registr do smíšeného stavu.</span><span class="sxs-lookup"><span data-stu-id="62179-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="62179-106">Registr se připravuje ve stavu $ \boldone/2 ^ N $ tím, že použije kompletní kanál depolarizing na každou qubit, kde $N $ je délka registru.</span><span class="sxs-lookup"><span data-stu-id="62179-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="62179-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="62179-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="62179-108">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="62179-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="62179-109">Registr, jehož stav má být depolarizace způsobem popsaným výše.</span><span class="sxs-lookup"><span data-stu-id="62179-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="62179-110">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62179-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="62179-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="62179-111">See Also</span></span>

- [<span data-ttu-id="62179-112">Microsoft. Přípravno. Preparation. PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="62179-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)