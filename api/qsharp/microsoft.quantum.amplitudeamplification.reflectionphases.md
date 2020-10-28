---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Uživatelem definovaný typ ReflectionPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: e0c7db6cd1aad636a34684958be117de1b9888f8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707714"
---
# <a name="reflectionphases-user-defined-type"></a>Uživatelem definovaný typ ReflectionPhases

Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)

Balíček [](https://nuget.org/packages/)


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