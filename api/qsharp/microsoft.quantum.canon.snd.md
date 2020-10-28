---
uid: Microsoft.Quantum.Canon.Snd
title: SND – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c05053b45d24c3398526d1269b90bb40d1e0ef27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698860"
---
# <a name="snd-function"></a><span data-ttu-id="768f0-102">SND – funkce</span><span class="sxs-lookup"><span data-stu-id="768f0-102">Snd function</span></span>

<span data-ttu-id="768f0-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="768f0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="768f0-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="768f0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="768f0-105">S ohledem na pár vrátí jeho druhý prvek.</span><span class="sxs-lookup"><span data-stu-id="768f0-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="768f0-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="768f0-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="768f0-107">dvojice: (t, ' U)</span><span class="sxs-lookup"><span data-stu-id="768f0-107">pair : ('T,'U)</span></span>

<span data-ttu-id="768f0-108">Řazená kolekce členů se dvěma prvky.</span><span class="sxs-lookup"><span data-stu-id="768f0-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="768f0-109">Výstup: ' U</span><span class="sxs-lookup"><span data-stu-id="768f0-109">Output : 'U</span></span>

<span data-ttu-id="768f0-110">Druhý prvek elementu `pair` .</span><span class="sxs-lookup"><span data-stu-id="768f0-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="768f0-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="768f0-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="768f0-112">'S</span><span class="sxs-lookup"><span data-stu-id="768f0-112">'T</span></span>

<span data-ttu-id="768f0-113">Typ prvního člena dvojice.</span><span class="sxs-lookup"><span data-stu-id="768f0-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="768f0-114">U</span><span class="sxs-lookup"><span data-stu-id="768f0-114">'U</span></span>

<span data-ttu-id="768f0-115">Typ druhého člena dvojice.</span><span class="sxs-lookup"><span data-stu-id="768f0-115">The type of the pair's second member.</span></span>