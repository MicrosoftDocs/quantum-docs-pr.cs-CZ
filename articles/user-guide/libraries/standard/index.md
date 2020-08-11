---
title: Úvod do standardních knihoven Microsoft Q#
description: Seznamte se se standardními knihovnami Microsoft Q#, které definují operace, funkce a datové typy používané v kvantových programech.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4db227fcf159331f9f8456c474ce6d64111c21df
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868470"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a><span data-ttu-id="b31d9-103">Úvod do standardních knihoven Q#</span><span class="sxs-lookup"><span data-stu-id="b31d9-103">Introduction to the Q# Standard Libraries</span></span>

<span data-ttu-id="b31d9-104">Jazyk Q# je podporován mnoha různými užitečnými operacemi, funkcemi a uživatelem definovanými typy, které tvoří *standardní knihovny* Q#.</span><span class="sxs-lookup"><span data-stu-id="b31d9-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="b31d9-105">[Balíček NuGet `Microsoft.Quantum.Development.Kit`](https://www.nuget.org/packages/microsoft.quantum.development.kit) nainstalovaný během [instalace a ověření](xref:microsoft.quantum.install) poskytuje kompilátor Q# a části standardní knihovny, které jsou implementovány cílovými počítači.</span><span class="sxs-lookup"><span data-stu-id="b31d9-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="b31d9-106">[Balíček `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) poskytuje část standardních knihoven Q#, které se dají přenášet napříč cílovými počítači.</span><span class="sxs-lookup"><span data-stu-id="b31d9-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="b31d9-107">Symboly definované standardními knihovnami Q# jsou mnohem podrobněji definovány v [dokumentaci k rozhraní API](xref:microsoft.quantum.standardlibsintro).</span><span class="sxs-lookup"><span data-stu-id="b31d9-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.standardlibsintro).</span></span>

<span data-ttu-id="b31d9-108">V následujících částech se seznámíme s nejdůležitějšími funkcemi každé části standardní knihovny a také s tím, jak lze každou funkci používat v praxi.</span><span class="sxs-lookup"><span data-stu-id="b31d9-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>
