---
title: Ukázkové aplikace pro kvantovou chemii
description: Projděte si ukázkové aplikace knihovny Microsoft Quantum pro chemii.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
no-loc:
- Q#
- $$v
ms.openlocfilehash: a0bc79c7fb41069ee7865dbf2f1cfd7851fda32d
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869286"
---
# <a name="quantum-chemistry-examples"></a><span data-ttu-id="88c24-103">Příklady pro kvantovou chemii</span><span class="sxs-lookup"><span data-stu-id="88c24-103">Quantum chemistry examples</span></span>

<span data-ttu-id="88c24-104">Na konceptech kvantové chemie jsme ručně sestavili ukázkové fermionové hamiltoniány.</span><span class="sxs-lookup"><span data-stu-id="88c24-104">In the quantum chemistry concepts, we manually constructed example fermion Hamiltonians.</span></span> <span data-ttu-id="88c24-105">Nyní kombinujeme algoritmy chemické simulace, které jsou uvedené v popisu [simulace hamiltoniánské dynamiky](xref:microsoft.quantum.libraries.standard.algorithms), s [odhadem kvantové fáze](xref:microsoft.quantum.libraries.characterization) v knihovně kánonu.</span><span class="sxs-lookup"><span data-stu-id="88c24-105">We now combine the chemistry simulation algorithms outlined in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) with [quantum phase estimation](xref:microsoft.quantum.libraries.characterization) in the canon library.</span></span> <span data-ttu-id="88c24-106">Tato kombinace nám umožňuje získat odhady energetických úrovní v reprezentované molekule, což je jedna z klíčových aplikací kvantové chemie na kvantových počítačích.</span><span class="sxs-lookup"><span data-stu-id="88c24-106">This combination allows us to obtain  estimates of energy levels in the represented molecule, which is one of the key applications of quantum chemistry on a quantum computer.</span></span> 

<span data-ttu-id="88c24-107">Namísto určování jednotlivých termínů hamiltoniánů také pracujeme s několika příklady, které nám umožňují provádět experimenty kvantové chemie ve velkém.</span><span class="sxs-lookup"><span data-stu-id="88c24-107">Instead of specifying terms of the Hamiltonian one-by-one, we also work through some examples that allow us to perform quantum chemistry experiments at scale.</span></span> <span data-ttu-id="88c24-108">Začneme s příklady, které načítají chemický hamiltonián kódovaný ve [schématu Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span><span class="sxs-lookup"><span data-stu-id="88c24-108">We begin with examples that load a chemistry Hamiltonian encoded in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span></span>

<span data-ttu-id="88c24-109">I pro molekuly, které jsou moc velké pro simulaci na [simulátoru celkového stavu](xref:microsoft.quantum.machines.full-state-simulator), se pořád dá dělat zajímavá věda.</span><span class="sxs-lookup"><span data-stu-id="88c24-109">For molecules that are too large to simulate on the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), interesting science can still be performed.</span></span> <span data-ttu-id="88c24-110">Například stále jde vyhodnotit náklady na prostředky k provádění velkých chemických simulací zaměřením na [simulátor trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="88c24-110">For instance, the resource costs of performing large chemistry simulations may still be evaluated by targeting the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>

<span data-ttu-id="88c24-111">Podívejme se nyní na zajímavé aplikace chemické simulační knihovny prostřednictvím několika z poskytnutých ukázek.</span><span class="sxs-lookup"><span data-stu-id="88c24-111">Let us now illustrate interesting applications of the chemistry simulation library through a few of the provided samples.</span></span>
