---
uid: Microsoft.Quantum.Core.Deprecated
title: Zastaralý uživatelem definovaný typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: b1fcae9647b2a655d25773386ecffa826515516e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698237"
---
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="c2500-102">Zastaralý uživatelem definovaný typ</span><span class="sxs-lookup"><span data-stu-id="c2500-102">Deprecated user defined type</span></span>

<span data-ttu-id="c2500-103">Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="c2500-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="c2500-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c2500-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c2500-105">Atribut rozpoznaný kompilátorem, který slouží k označení typu nebo k jeho vyžádání jako zastaralé.</span><span class="sxs-lookup"><span data-stu-id="c2500-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="c2500-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="c2500-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="c2500-107">Nový_název: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="c2500-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="c2500-108">Úplný název typu nebo volat, který se má použít.</span><span class="sxs-lookup"><span data-stu-id="c2500-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="c2500-109">Je nastaven na prázdný řetězec, pokud je typ nebo možné použití zastaralá bez substituce.</span><span class="sxs-lookup"><span data-stu-id="c2500-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>