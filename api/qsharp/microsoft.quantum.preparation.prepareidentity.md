---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Operace PrepareIdentity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: ec7e813110ccd9e6d499fc469fa27249a182b870
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855873"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="69be2-102">Operace PrepareIdentity</span><span class="sxs-lookup"><span data-stu-id="69be2-102">PrepareIdentity operation</span></span>

<span data-ttu-id="69be2-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="69be2-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="69be2-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69be2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69be2-105">V případě registru připraví tento registr do smíšeného stavu.</span><span class="sxs-lookup"><span data-stu-id="69be2-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="69be2-106">Registr se připravuje ve stavu $ \boldone/2 ^ N $ tím, že použije kompletní kanál depolarizing na každou qubit, kde $N $ je délka registru.</span><span class="sxs-lookup"><span data-stu-id="69be2-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="69be2-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="69be2-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="69be2-108">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="69be2-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="69be2-109">Registr, jehož stav má být depolarizace způsobem popsaným výše.</span><span class="sxs-lookup"><span data-stu-id="69be2-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="69be2-110">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69be2-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="69be2-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="69be2-111">See Also</span></span>

- [<span data-ttu-id="69be2-112">Microsoft. Přípravno. Preparation. PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="69be2-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)