---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: Operace DecodeFromSteaneCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: e6831a8630c0a80c2abe7c4a720263f0de03edc4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697993"
---
# <a name="decodefromsteanecode-operation"></a><span data-ttu-id="99152-102">Operace DecodeFromSteaneCode</span><span class="sxs-lookup"><span data-stu-id="99152-102">DecodeFromSteaneCode operation</span></span>

<span data-ttu-id="99152-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="99152-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="99152-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="99152-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="99152-105">Operace inverzního kódování, která mapuje nekódovaný registr do kódovaného kódu, se zakódovaným registrem na základě ⟦ 7, 1, 3 ⟧ Steane kód.</span><span class="sxs-lookup"><span data-stu-id="99152-105">An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="99152-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="99152-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="99152-107">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="99152-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="99152-108">Pole qubits představující kódovaný kód 5-qubit kódu.</span><span class="sxs-lookup"><span data-stu-id="99152-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="99152-109">Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="99152-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="99152-110">Qubit pole o délce 1 představující nekódovaný stav v prvním parametru spolu s pomocnou qubits ve druhém parametru.</span><span class="sxs-lookup"><span data-stu-id="99152-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="99152-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="99152-111">Remarks</span></span>

<span data-ttu-id="99152-112">Zvolený dekodér používá vlastnost kódu CSS kódu ⟦ 7, 1, 3 ⟧ Steane, to znamená, že opraví chyby X a chyby Z samostatně.</span><span class="sxs-lookup"><span data-stu-id="99152-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="99152-113">Vlastnost kódu je, že umístění X, v uvedeném pořadí má být použito, je trojrozměrné kódování X, v tomto pořadí Z Syndrome, pokud se považuje za celé číslo.</span><span class="sxs-lookup"><span data-stu-id="99152-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="99152-114">Odkazy</span><span class="sxs-lookup"><span data-stu-id="99152-114">References</span></span>

- <span data-ttu-id="99152-115">D.</span><span class="sxs-lookup"><span data-stu-id="99152-115">D.</span></span> <span data-ttu-id="99152-116">Gottesman, "kódy stabilizovaných a chybových stavů," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="99152-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="99152-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="99152-117">See Also</span></span>

- [<span data-ttu-id="99152-118">Microsoft. ErrorCorrection. SteaneCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="99152-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [<span data-ttu-id="99152-119">Microsoft. ErrorCorrection. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="99152-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [<span data-ttu-id="99152-120">Microsoft. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="99152-120">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)