---
title: Knihovny pro sady Quantum Development Kit
description: Přehled standardních, chemických a numerických knihoven, které jsou součástí sady Microsoft Quantum Development Kit
author: cgranade
ms.author: chgranad
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 90672b6ec78bf8305bdb3ab8326002cf8ce34bfe
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835719"
---
# <a name="overview-of-no-locq-libraries"></a><span data-ttu-id="c7c6b-103">Přehled knihoven Q#</span><span class="sxs-lookup"><span data-stu-id="c7c6b-103">Overview of Q# Libraries</span></span>
<span data-ttu-id="c7c6b-104">Sada Quantum Development Kit se poskytuje s několika knihovnami, které usnadňují vývoj kvantových aplikací v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-104">The Quantum Development Kit is provided with several libraries to make it easier to develop quantum applications in Q#.</span></span>
<span data-ttu-id="c7c6b-105">V této části dokumentace popisujeme tyto knihovny a způsob jejich použití ve vašich programech.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-105">In this section of the documentation, we describe these libraries and how to use them in your programs.</span></span>

- <span data-ttu-id="c7c6b-106">[**Standardní knihovny**](xref:microsoft.quantum.libraries.standard.intro): Tato část popisuje předehru, která definuje rozhraní mezi programy v Q# a cílovými počítači, a kánon, knihovnou Q#, která poskytuje operace a funkce pro obecné účely k použití při psaní programů v Q#.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-106">[**Standard libraries**](xref:microsoft.quantum.libraries.standard.intro): This section describes the prelude, which defines the interface between Q# programs and target machines, and the canon, a Q# library that provides general-purpose operations and functions for use in writing Q# programs.</span></span>
- <span data-ttu-id="c7c6b-107">[**Kvantová chemická knihovna**](xref:microsoft.quantum.chemistry.concepts.intro): Tato část popisuje kvantovou chemickou knihovnu, která poskytuje datový model pro načítání reprezentace fermionových hamiltoniánů, a operace a funkce kvantové simulace, které fungují na základě těchto reprezentací.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-107">[**Quantum chemistry library**](xref:microsoft.quantum.chemistry.concepts.intro): This section describes the quantum chemistry library, which provides a data model for loading representations of fermionic Hamiltonians and quantum simulation operations and functions which act on these representations.</span></span>
- <span data-ttu-id="c7c6b-108">[**Kvantová numerická knihovna**](xref:microsoft.quantum.numerics.intro): Tato část popisuje kvantovou numerickou knihovnu, která poskytuje implementace pro hostitele matematických funkcí.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-108">[**Quantum numerics library**](xref:microsoft.quantum.numerics.intro): This section describes the quantum numerics library, which provides implementations for a host of mathematical functions.</span></span> <span data-ttu-id="c7c6b-109">Podporuje reprezentace celých čísel (se znaménkem i bez znaménka) a čísel s pevnou desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-109">It supports integer (signed & unsigned) and fixed-point representations.</span></span>
- <span data-ttu-id="c7c6b-110">[**Knihovna pro kvantové strojové učení**](xref:microsoft.quantum.machine-learning.concepts.intro): Tato část popisuje knihovnu pro kvantové strojového učení, která poskytuje implementaci sekvenčních klasifikátorů využívajících výpočetní výkon pro pochopení dat.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-110">[**Quantum machine learning library**](xref:microsoft.quantum.machine-learning.concepts.intro): This section describes the quantum machine learning library, which provides an implementation of the sequential classifiers that take advantage of quantum computing to understand data.</span></span>

<span data-ttu-id="c7c6b-111">Zdroje knihoven včetně ukázek kódu lze získat z GitHubu.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-111">Sources of the libraries as well as code samples can be obtained from GitHub.</span></span>
<span data-ttu-id="c7c6b-112">Další informace najdete v tématu věnovaném [licencování](xref:microsoft.quantum.libraries.licensing).</span><span class="sxs-lookup"><span data-stu-id="c7c6b-112">See [Licensing](xref:microsoft.quantum.libraries.licensing) for further information.</span></span> <span data-ttu-id="c7c6b-113">Je nutné poznamenat, že odkazy na balíčky („binární soubory“) jsou k dispozici také pro knihovny a nabízejí další způsob zahrnutí knihoven do projektů.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-113">Note that package references ("binaries") are available also for the libraries and offer another way of including the libraries in projects.</span></span>
<span data-ttu-id="c7c6b-114">Pohodlný způsob, jak je získat, je prostřednictvím [NuGetu](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="c7c6b-114">A convenient way of obtaining them is via [NuGet](https://nuget.org).</span></span>
