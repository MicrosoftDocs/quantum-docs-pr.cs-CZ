---
uid: Microsoft.Quantum.Core.Deprecated
title: Zastaralý uživatelem definovaný typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 122cbc113a68cec107558d68a6fb145cf6bbd9db
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224084"
---
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="f4432-102">Zastaralý uživatelem definovaný typ</span><span class="sxs-lookup"><span data-stu-id="f4432-102">Deprecated user defined type</span></span>

<span data-ttu-id="f4432-103">Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="f4432-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="f4432-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f4432-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f4432-105">Atribut rozpoznaný kompilátorem, který slouží k označení typu nebo k jeho vyžádání jako zastaralé.</span><span class="sxs-lookup"><span data-stu-id="f4432-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="f4432-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="f4432-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="f4432-107">Nový_název: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="f4432-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="f4432-108">Úplný název typu nebo volat, který se má použít.</span><span class="sxs-lookup"><span data-stu-id="f4432-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="f4432-109">Je nastaven na prázdný řetězec, pokud je typ nebo možné použití zastaralá bez substituce.</span><span class="sxs-lookup"><span data-stu-id="f4432-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>