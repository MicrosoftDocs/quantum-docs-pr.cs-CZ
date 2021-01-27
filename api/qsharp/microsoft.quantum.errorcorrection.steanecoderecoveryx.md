---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: c90eac291ebe718d10377399184ad705bb51673e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824703"
---
# <a name="steanecoderecoveryx-function"></a><span data-ttu-id="bd20f-102">SteaneCodeRecoveryX – funkce</span><span class="sxs-lookup"><span data-stu-id="bd20f-102">SteaneCodeRecoveryX function</span></span>

<span data-ttu-id="bd20f-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="bd20f-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="bd20f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd20f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd20f-105">Dekodér pro X-část skupiny stabilizace kódu ⟦ 7, 1, 3 ⟧ Steane.</span><span class="sxs-lookup"><span data-stu-id="bd20f-105">Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="bd20f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="bd20f-106">Input</span></span>

### <a name="syndrome--syndrome"></a><span data-ttu-id="bd20f-107">Syndrome: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="bd20f-107">syndrome : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="bd20f-108">Pole Syndrome získané z měření X-části stabilizovaného modulu.</span><span class="sxs-lookup"><span data-stu-id="bd20f-108">A syndrome array obtained from measuring the X-part of the stabilizer.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="bd20f-109">Výstup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="bd20f-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="bd20f-110">Pole Pauli operací, které při použití s kódovaným systémem v-opravuje chybu odpovídající `syndrome` .</span><span class="sxs-lookup"><span data-stu-id="bd20f-110">An array of Pauli operations which, when applied to the encoded quantum system corrects the error corresponding to `syndrome`.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd20f-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="bd20f-111">Remarks</span></span>

<span data-ttu-id="bd20f-112">Zvolený dekodér používá vlastnost kódu CSS kódu ⟦ 7, 1, 3 ⟧ Steane, to znamená, že opraví chyby X a chyby Z samostatně.</span><span class="sxs-lookup"><span data-stu-id="bd20f-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="bd20f-113">Vlastnost kódu je, že umístění X, v uvedeném pořadí má být použito, je trojrozměrné kódování X, v tomto pořadí Z Syndrome, pokud se považuje za celé číslo.</span><span class="sxs-lookup"><span data-stu-id="bd20f-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="bd20f-114">Reference</span><span class="sxs-lookup"><span data-stu-id="bd20f-114">References</span></span>

- <span data-ttu-id="bd20f-115">D.</span><span class="sxs-lookup"><span data-stu-id="bd20f-115">D.</span></span> <span data-ttu-id="bd20f-116">Gottesman, "kódy stabilizovaných a chybových stavů," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="bd20f-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="bd20f-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="bd20f-117">See Also</span></span>

- [<span data-ttu-id="bd20f-118">Microsoft. ErrorCorrection. SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="bd20f-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="bd20f-119">Microsoft. ErrorCorrection. SteaneCodeRecoveryFns</span><span class="sxs-lookup"><span data-stu-id="bd20f-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)