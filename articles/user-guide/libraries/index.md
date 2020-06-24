---
title: Knihovny pro sady Quantum Development Kit
description: Přehled standardních, chemických a numerických knihoven, které jsou součástí sady Microsoft Quantum Development Kit
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
ms.openlocfilehash: 89612aaa5c11e1a5e0d418256e96366953fdd3fe
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273363"
---
# <a name="overview-of-q-libraries"></a><span data-ttu-id="0c3ae-103">Přehled knihoven Q #</span><span class="sxs-lookup"><span data-stu-id="0c3ae-103">Overview of Q# Libraries</span></span>
<span data-ttu-id="0c3ae-104">Sada Quantum Development Kit je poskytována s několika knihovnami, které usnadňují vývoj kvantových aplikací v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="0c3ae-104">The Quantum Development Kit is provided with several libraries to make it easier to develop quantum applications in Q#.</span></span>
<span data-ttu-id="0c3ae-105">V této části dokumentace popisujeme tyto knihovny a způsob jejich použití ve vašich programech.</span><span class="sxs-lookup"><span data-stu-id="0c3ae-105">In this section of the documentation, we describe these libraries and how to use them in your programs.</span></span>

- <span data-ttu-id="0c3ae-106">[**Standardní knihovny**](xref:microsoft.quantum.libraries.standard.intro): Tato část popisuje předehru, která definuje rozhraní mezi programy Q# a cílovými počítači, a kánon, knihovnou Q#, která poskytuje operace a funkce pro obecné účely k použití při psaní programů Q#.</span><span class="sxs-lookup"><span data-stu-id="0c3ae-106">[**Standard libraries**](xref:microsoft.quantum.libraries.standard.intro): This section describes the prelude, which defines the interface between Q# programs and target machines, and the canon, a Q# library that provides general-purpose operations and functions for use in writing Q# programs.</span></span>
- <span data-ttu-id="0c3ae-107">[**Kvantová chemická knihovna**](xref:microsoft.quantum.chemistry.concepts.intro): Tato část popisuje kvantovou chemickou knihovnu, která poskytuje datový model pro načítání reprezentace fermionových hamiltoniánů, a operace a funkce kvantové simulace, které fungují na základě těchto reprezentací.</span><span class="sxs-lookup"><span data-stu-id="0c3ae-107">[**Quantum chemistry library**](xref:microsoft.quantum.chemistry.concepts.intro): This section describes the quantum chemistry library, which provides a data model for loading representations of fermionic Hamiltonians and quantum simulation operations and functions which act on these representations.</span></span>
- <span data-ttu-id="0c3ae-108">[**Kvantová numerická knihovna**](xref:microsoft.quantum.numerics.intro): Tato část popisuje kvantovou numerickou knihovnu, která poskytuje implementace pro hostitele matematických funkcí.</span><span class="sxs-lookup"><span data-stu-id="0c3ae-108">[**Quantum numerics library**](xref:microsoft.quantum.numerics.intro): This section describes the quantum numerics library, which provides implementations for a host of mathematical functions.</span></span> <span data-ttu-id="0c3ae-109">Podporuje reprezentace celých čísel (se znaménkem i bez znaménka) a čísel s pevnou desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="0c3ae-109">It supports integer (signed & unsigned) and fixed-point representations.</span></span>

<span data-ttu-id="0c3ae-110">Zdroje knihoven včetně ukázek kódu lze získat z GitHubu.</span><span class="sxs-lookup"><span data-stu-id="0c3ae-110">Sources of the libraries as well as code samples can be obtained from GitHub.</span></span> <span data-ttu-id="0c3ae-111">Další informace najdete také v části s popisem [licencování](xref:microsoft.quantum.libraries.licensing).</span><span class="sxs-lookup"><span data-stu-id="0c3ae-111">See also the [licensing](xref:microsoft.quantum.libraries.licensing) section for further information.</span></span> <span data-ttu-id="0c3ae-112">Je nutné poznamenat, že odkazy na balíčky („binární soubory“) jsou k dispozici také pro knihovny, které nabízí další způsob zahrnutí knihoven do projektů.</span><span class="sxs-lookup"><span data-stu-id="0c3ae-112">It should be noted that package references ("binaries") are available also for the libraries which offers another way of including the libraries in projects.</span></span> <span data-ttu-id="0c3ae-113">Pohodlný způsob, jak je získat, je prostřednictvím [nugetu](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="0c3ae-113">A convenient way of obtaining them is via [nuget](https://nuget.org).</span></span>
