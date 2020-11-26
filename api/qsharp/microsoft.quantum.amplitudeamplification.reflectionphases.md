---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Uživatelem definovaný typ ReflectionPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: 743ece778239c223573a3a8536ae8059cea09d5f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191342"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="9881b-102">Uživatelem definovaný typ ReflectionPhases</span><span class="sxs-lookup"><span data-stu-id="9881b-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="9881b-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="9881b-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="9881b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9881b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9881b-105">Fáze pro sekvenci částečných odrazů v zesílení amplitudy.</span><span class="sxs-lookup"><span data-stu-id="9881b-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="9881b-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="9881b-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="9881b-107">AboutStart: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9881b-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9881b-108">Pole fází pro reflexi počátečního stavu.</span><span class="sxs-lookup"><span data-stu-id="9881b-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="9881b-109">AboutTarget: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9881b-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9881b-110">Pole fází pro reflexi cílového stavu.</span><span class="sxs-lookup"><span data-stu-id="9881b-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="9881b-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="9881b-111">Remarks</span></span>

<span data-ttu-id="9881b-112">Obě pole musí mít stejnou délku.</span><span class="sxs-lookup"><span data-stu-id="9881b-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="9881b-113">Všimněte si, že v mnoha případech první fáze týkající se počátečního stavu a poslední fáze týkající se cílového stavu zavádí globální fázi posunu a může být nastavená na $0 $.</span><span class="sxs-lookup"><span data-stu-id="9881b-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>