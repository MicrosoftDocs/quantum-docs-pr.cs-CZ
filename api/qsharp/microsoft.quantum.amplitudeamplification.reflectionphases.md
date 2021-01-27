---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Uživatelem definovaný typ ReflectionPhases
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: fc3642b76c6e01f0709e78ea42c9ea7237389afa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847185"
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