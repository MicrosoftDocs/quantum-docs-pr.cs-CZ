---
uid: Microsoft.Quantum.Core.Deprecated
title: Zastaralý uživatelem definovaný typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 1a32d98f5d034c2673d42301b45379da1302ca7f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832091"
---
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="d1f23-102">Zastaralý uživatelem definovaný typ</span><span class="sxs-lookup"><span data-stu-id="d1f23-102">Deprecated user defined type</span></span>

<span data-ttu-id="d1f23-103">Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="d1f23-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="d1f23-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d1f23-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d1f23-105">Atribut rozpoznaný kompilátorem, který slouží k označení typu nebo k jeho vyžádání jako zastaralé.</span><span class="sxs-lookup"><span data-stu-id="d1f23-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="d1f23-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="d1f23-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="d1f23-107">Nový_název: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d1f23-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="d1f23-108">Úplný název typu nebo volat, který se má použít.</span><span class="sxs-lookup"><span data-stu-id="d1f23-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="d1f23-109">Je nastaven na prázdný řetězec, pokud je typ nebo možné použití zastaralá bez substituce.</span><span class="sxs-lookup"><span data-stu-id="d1f23-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>