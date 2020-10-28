---
uid: Microsoft.Quantum.Simulation.TimeDependentBlockEncoding
title: Uživatelem definovaný typ TimeDependentBlockEncoding
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentBlockEncoding
qsharp.summary: >-
  Represents a `BlockEncoding` that is controlled by a clock register.

  That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k. \end{align} $$.
ms.openlocfilehash: 1cb3a3cf1e16b194eebd1574da6f9934fc34e5f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709405"
---
# <a name="timedependentblockencoding-user-defined-type"></a><span data-ttu-id="63f86-102">Uživatelem definovaný typ TimeDependentBlockEncoding</span><span class="sxs-lookup"><span data-stu-id="63f86-102">TimeDependentBlockEncoding user defined type</span></span>

<span data-ttu-id="63f86-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="63f86-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="63f86-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="63f86-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="63f86-105">Představuje `BlockEncoding` , který je řízen registrem hodin.</span><span class="sxs-lookup"><span data-stu-id="63f86-105">Represents a `BlockEncoding` that is controlled by a clock register.</span></span>

<span data-ttu-id="63f86-106">To znamená, že `TimeDependentBlockEncoding` se jedná o jednotkovou $U $ řízenou stavem $ \ket{k} _D $ v hodinách `d` , takže libovolný operátor $H _k $ z zájmu, který funguje v registru System, `s` je kódovaný v levém horním bloku, který odpovídá pomocnému stavu $ \ket {0} _a $.</span><span class="sxs-lookup"><span data-stu-id="63f86-106">That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="63f86-107">To je</span><span class="sxs-lookup"><span data-stu-id="63f86-107">That is,</span></span>

<span data-ttu-id="63f86-108">$ $ \begin{align} (\bra {0} \_ a\otimes i_ {DS}) U (\ket {0} \_ a\otimes i_ {DS}) = \ sum_ {k} \ket{k}\bra{k} \_ d\otimes H_k.</span><span class="sxs-lookup"><span data-stu-id="63f86-108">$$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k.</span></span>
<span data-ttu-id="63f86-109">\end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="63f86-109">\end{align} $$.</span></span>

```qsharp

newtype TimeDependentBlockEncoding = (((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

