---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualReferenced
title: Operace AssertOperationsEqualReferenced
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualReferenced has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: 1f4d98006677dc532d45ffb797fe0a8e05496640
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98820095"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="4c192-102">Operace AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="4c192-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="4c192-103">Obor názvů: [Microsoft.. Extensions. test](xref:Microsoft.Quantum.Extensions.Testing)</span><span class="sxs-lookup"><span data-stu-id="4c192-103">Namespace: [Microsoft.Quantum.Extensions.Testing](xref:Microsoft.Quantum.Extensions.Testing)</span></span>

<span data-ttu-id="4c192-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4c192-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


> [!WARNING]
> <span data-ttu-id="4c192-105">AssertOperationsEqualReferenced se už nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="4c192-105">AssertOperationsEqualReferenced has been deprecated.</span></span> <span data-ttu-id="4c192-106"><xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced>Místo toho ho použijte.</span><span class="sxs-lookup"><span data-stu-id="4c192-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> instead.</span></span>
>
> <span data-ttu-id="4c192-107">Používejte @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".</span><span class="sxs-lookup"><span data-stu-id="4c192-107">Please use @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".</span></span>
> <span data-ttu-id="4c192-108">Všimněte si, že pořadí argumentů této operace se změnilo.</span><span class="sxs-lookup"><span data-stu-id="4c192-108">Note that the order of the arguments to this operation has changed.</span></span>



```qsharp
operation AssertOperationsEqualReferenced (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a><span data-ttu-id="4c192-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="4c192-109">Input</span></span>

### <a name="actual--qubit--unit"></a><span data-ttu-id="4c192-110">skutečnost: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4c192-110">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="expected--qubit--unit--is-adj"></a><span data-ttu-id="4c192-111">očekáváno: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="4c192-111">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nqubits--int"></a><span data-ttu-id="4c192-112">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4c192-112">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--unit"></a><span data-ttu-id="4c192-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4c192-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

