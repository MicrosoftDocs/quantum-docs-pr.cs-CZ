---
uid: microsoft.quantum.standardlibsintro
title: Standardní knihovna jazyka Q# pro Microsoft Quantum
description: Referenční dokumentace ke standardní knihovně jazyka Q# pro Microsoft Quantum
author: natke
ms.author: nakersha
ms.date: 09/04/2019
ms.topic: landing-page
ms.openlocfilehash: 25a53e1cb8577761ef89cdcf2cfcddc509093f86
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2019
ms.locfileid: "73056966"
---
# <a name="q-standard-libraries"></a><span data-ttu-id="459c0-103">Standardní knihovny jazyka Q#</span><span class="sxs-lookup"><span data-stu-id="459c0-103">Q# standard libraries</span></span> #

<span data-ttu-id="459c0-104">Jazyk Q# je podporován mnoha různými užitečnými operacemi, funkcemi a uživatelem definovanými typy, které tvoří *standardní knihovnu* jazyka Q#.</span><span class="sxs-lookup"><span data-stu-id="459c0-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard library*.</span></span>
<span data-ttu-id="459c0-105">Standardní knihovna jazyka Q# je rozdělená na dvě hlavní části:</span><span class="sxs-lookup"><span data-stu-id="459c0-105">The Q# standard library is split into two main parts:</span></span>

- <span data-ttu-id="459c0-106">**Předehra:** Operace a funkce definované jako součást cílového počítače a kompilátoru, typicky v klasickém nativním kódu .NET.</span><span class="sxs-lookup"><span data-stu-id="459c0-106">**The prelude**: operations and functions defined as a part of the target machine and compiler, typically in classical native .NET code.</span></span>
  <span data-ttu-id="459c0-107">Obecně platí, že různé cílové počítače můžou mít různé implementace předehry podle používaného systému.</span><span class="sxs-lookup"><span data-stu-id="459c0-107">In general, different target machines may have different implementations of the prelude appropriate to each system.</span></span>
- <span data-ttu-id="459c0-108">**Zásady:** Operace a funkce definované v jazyku Q# a založené na logice definované v předehře.</span><span class="sxs-lookup"><span data-stu-id="459c0-108">**The canon**: operations and functions defined in Q# building on the logic defined in the prelude.</span></span>
  <span data-ttu-id="459c0-109">Implementace zásad je nezávislá na cílových počítačích.</span><span class="sxs-lookup"><span data-stu-id="459c0-109">The canon implementation is agnostic with respect to target machines.</span></span>
<span data-ttu-id="459c0-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span><span class="sxs-lookup"><span data-stu-id="459c0-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span></span>