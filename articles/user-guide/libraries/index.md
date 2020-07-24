---
title: Knihovny pro sady Quantum Development Kit
description: Přehled standardních, chemických a numerických knihoven, které jsou součástí sady Microsoft Quantum Development Kit
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
ms.openlocfilehash: 09fc723d27f2e026430b358c62b817c106c135c2
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871497"
---
# <a name="overview-of-q-libraries"></a><span data-ttu-id="25e92-103">Přehled knihoven Q #</span><span class="sxs-lookup"><span data-stu-id="25e92-103">Overview of Q# Libraries</span></span>
<span data-ttu-id="25e92-104">Sada Quantum Development Kit je poskytována s několika knihovnami, které usnadňují vývoj kvantových aplikací v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="25e92-104">The Quantum Development Kit is provided with several libraries to make it easier to develop quantum applications in Q#.</span></span>
<span data-ttu-id="25e92-105">V této části dokumentace popisujeme tyto knihovny a způsob jejich použití ve vašich programech.</span><span class="sxs-lookup"><span data-stu-id="25e92-105">In this section of the documentation, we describe these libraries and how to use them in your programs.</span></span>

- <span data-ttu-id="25e92-106">[**Standardní knihovny**](xref:microsoft.quantum.libraries.standard.intro): Tato část popisuje předehru, která definuje rozhraní mezi programy Q# a cílovými počítači, a kánon, knihovnou Q#, která poskytuje operace a funkce pro obecné účely k použití při psaní programů Q#.</span><span class="sxs-lookup"><span data-stu-id="25e92-106">[**Standard libraries**](xref:microsoft.quantum.libraries.standard.intro): This section describes the prelude, which defines the interface between Q# programs and target machines, and the canon, a Q# library that provides general-purpose operations and functions for use in writing Q# programs.</span></span>
- <span data-ttu-id="25e92-107">[**Kvantová chemická knihovna**](xref:microsoft.quantum.chemistry.concepts.intro): Tato část popisuje kvantovou chemickou knihovnu, která poskytuje datový model pro načítání reprezentace fermionových hamiltoniánů, a operace a funkce kvantové simulace, které fungují na základě těchto reprezentací.</span><span class="sxs-lookup"><span data-stu-id="25e92-107">[**Quantum chemistry library**](xref:microsoft.quantum.chemistry.concepts.intro): This section describes the quantum chemistry library, which provides a data model for loading representations of fermionic Hamiltonians and quantum simulation operations and functions which act on these representations.</span></span>
- <span data-ttu-id="25e92-108">[**Kvantová numerická knihovna**](xref:microsoft.quantum.numerics.intro): Tato část popisuje kvantovou numerickou knihovnu, která poskytuje implementace pro hostitele matematických funkcí.</span><span class="sxs-lookup"><span data-stu-id="25e92-108">[**Quantum numerics library**](xref:microsoft.quantum.numerics.intro): This section describes the quantum numerics library, which provides implementations for a host of mathematical functions.</span></span> <span data-ttu-id="25e92-109">Podporuje reprezentace celých čísel (se znaménkem i bez znaménka) a čísel s pevnou desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="25e92-109">It supports integer (signed & unsigned) and fixed-point representations.</span></span>
- <span data-ttu-id="25e92-110">[**Knihovna pro kvantové strojové učení**](xref:microsoft.quantum.machine-learning.concepts.intro): Tato část popisuje knihovnu pro kvantové strojového učení, která poskytuje implementaci sekvenčních klasifikátorů využívajících výpočetní výkon pro pochopení dat.</span><span class="sxs-lookup"><span data-stu-id="25e92-110">[**Quantum machine learning library**](xref:microsoft.quantum.machine-learning.concepts.intro): This section describes the quantum machine learning library, which provides an implementation of the sequential classifiers that take advantage of quantum computing to understand data.</span></span>

<span data-ttu-id="25e92-111">Zdroje knihoven včetně ukázek kódu lze získat z GitHubu.</span><span class="sxs-lookup"><span data-stu-id="25e92-111">Sources of the libraries as well as code samples can be obtained from GitHub.</span></span>
<span data-ttu-id="25e92-112">Další informace najdete v tématu věnovaném [licencování](xref:microsoft.quantum.libraries.licensing).</span><span class="sxs-lookup"><span data-stu-id="25e92-112">See [Licensing](xref:microsoft.quantum.libraries.licensing) for further information.</span></span> <span data-ttu-id="25e92-113">Je nutné poznamenat, že odkazy na balíčky („binární soubory“) jsou k dispozici také pro knihovny a nabízejí další způsob zahrnutí knihoven do projektů.</span><span class="sxs-lookup"><span data-stu-id="25e92-113">Note that package references ("binaries") are available also for the libraries and offer another way of including the libraries in projects.</span></span>
<span data-ttu-id="25e92-114">Pohodlný způsob, jak je získat, je prostřednictvím [NuGetu](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="25e92-114">A convenient way of obtaining them is via [NuGet](https://nuget.org).</span></span>
