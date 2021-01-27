---
title: Úvod do standardních knihoven Microsoft Q#
description: Seznamte se se standardními knihovnami Microsoft Q#, které definují operace, funkce a datové typy používané v kvantových programech.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 58e271fefba84e45c5558eeee066bc37c22bf63b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858314"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a><span data-ttu-id="e257b-103">Úvod do standardních knihoven Q#</span><span class="sxs-lookup"><span data-stu-id="e257b-103">Introduction to the Q# Standard Libraries</span></span>

<span data-ttu-id="e257b-104">Jazyk Q# je podporován mnoha různými užitečnými operacemi, funkcemi a uživatelem definovanými typy, které tvoří *standardní knihovny* Q#.</span><span class="sxs-lookup"><span data-stu-id="e257b-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="e257b-105">[Balíček NuGet `Microsoft.Quantum.Development.Kit`](https://www.nuget.org/packages/microsoft.quantum.development.kit) nainstalovaný během [instalace a ověření](xref:microsoft.quantum.install) poskytuje kompilátor Q# a části standardní knihovny, které jsou implementovány cílovými počítači.</span><span class="sxs-lookup"><span data-stu-id="e257b-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="e257b-106">[Balíček `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) poskytuje část standardních knihoven Q#, které se dají přenášet napříč cílovými počítači.</span><span class="sxs-lookup"><span data-stu-id="e257b-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="e257b-107">Symboly definované standardními knihovnami Q# jsou mnohem podrobněji definovány v [dokumentaci k rozhraní API](xref:microsoft.quantum.apiref-intro).</span><span class="sxs-lookup"><span data-stu-id="e257b-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.apiref-intro).</span></span>

<span data-ttu-id="e257b-108">V následujících částech se seznámíme s nejdůležitějšími funkcemi každé části standardní knihovny a také s tím, jak lze každou funkci používat v praxi.</span><span class="sxs-lookup"><span data-stu-id="e257b-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>
