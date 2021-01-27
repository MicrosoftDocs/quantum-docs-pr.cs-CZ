---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: Operace EncodeIntoSteaneCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 2f65423a17dafadd1f9f10a07335150dfc8bf886
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826195"
---
# <a name="encodeintosteanecode-operation"></a><span data-ttu-id="52b44-102">Operace EncodeIntoSteaneCode</span><span class="sxs-lookup"><span data-stu-id="52b44-102">EncodeIntoSteaneCode operation</span></span>

<span data-ttu-id="52b44-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="52b44-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="52b44-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="52b44-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="52b44-105">Operace kódování, která mapuje nekódovaný registr v registru do kódovaného registru, se zakódovaným registrem na základě kódu ⟦ 7, 1, 3 ⟧ Steane.</span><span class="sxs-lookup"><span data-stu-id="52b44-105">An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="52b44-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="52b44-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="52b44-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="52b44-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="52b44-108">Qubit registr, který obsahuje nekódovaný stav bez kódování</span><span class="sxs-lookup"><span data-stu-id="52b44-108">A qubit register which holds the an unencoded quantum state</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="52b44-109">auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="52b44-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="52b44-110">Qubit registr, který je zpočátku nula a který se přidá do systému pro práci s poli, aby bylo možné provést operaci kódování</span><span class="sxs-lookup"><span data-stu-id="52b44-110">A qubit register which is initially zero and which gets added to the quantum system so that an encoding operation can be performed</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="52b44-111">Výstup: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="52b44-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="52b44-112">Registr u po použití kodéru Steane</span><span class="sxs-lookup"><span data-stu-id="52b44-112">A quantum register holding the state after the Steane encoder has been applied</span></span>

## <a name="see-also"></a><span data-ttu-id="52b44-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="52b44-113">See Also</span></span>

- [<span data-ttu-id="52b44-114">Microsoft. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="52b44-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="52b44-115">Microsoft. ErrorCorrection. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="52b44-115">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)