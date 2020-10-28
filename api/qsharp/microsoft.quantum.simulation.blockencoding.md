---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: Uživatelem definovaný typ BlockEncoding
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 1b769c58fd23b4ebc9d779cec3c47d8275822e5a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708091"
---
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="2cc1e-102">Uživatelem definovaný typ BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="2cc1e-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="2cc1e-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2cc1e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2cc1e-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2cc1e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2cc1e-105">Představuje jednotnou, kde je libovolný operátor zájmu kódovaný v horním levém bloku.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="2cc1e-106">To znamená, že `BlockEncoding` se jedná o jednotnou $U $, kde libovolný operátor $H $ Interest, který funguje v registru systému, `s` je kódovaný v horním levém bloku, který odpovídá pomocnému stavu $ \ket {0} _a $.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="2cc1e-107">To je</span><span class="sxs-lookup"><span data-stu-id="2cc1e-107">That is,</span></span>

<span data-ttu-id="2cc1e-108">$ $ \begin{align} (\bra {0} _a \otimes I_s) U (\ket {0} _a \otimes I_s) = H \end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

