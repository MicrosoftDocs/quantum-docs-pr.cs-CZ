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
# <a name="reflectionphases-user-defined-type"></a>Uživatelem definovaný typ ReflectionPhases

Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fáze pro sekvenci částečných odrazů v zesílení amplitudy.

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a>Pojmenované položky

### <a name="aboutstart--double"></a>AboutStart: [Double](xref:microsoft.quantum.lang-ref.double)[]

Pole fází pro reflexi počátečního stavu.
### <a name="abouttarget--double"></a>AboutTarget: [Double](xref:microsoft.quantum.lang-ref.double)[]

Pole fází pro reflexi cílového stavu.

## <a name="remarks"></a>Poznámky

Obě pole musí mít stejnou délku. Všimněte si, že v mnoha případech první fáze týkající se počátečního stavu a poslední fáze týkající se cílového stavu zavádí globální fázi posunu a může být nastavená na $0 $.