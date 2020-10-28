---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 8ba5c6fab4abcfaee7233df9535f22eea5f68c28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708205"
---
# <a name="quantumrom-function"></a><span data-ttu-id="26e5c-102">QuantumROM – funkce</span><span class="sxs-lookup"><span data-stu-id="26e5c-102">QuantumROM function</span></span>

<span data-ttu-id="26e5c-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="26e5c-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="26e5c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="26e5c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="26e5c-105">Vystupuje danou matici hustoty pomocí techniky paměti pro paměťová pole.</span><span class="sxs-lookup"><span data-stu-id="26e5c-105">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="26e5c-106">V případě, že se zobrazí seznam $N alpha_j $ \ket{j}\bra{j} $, vrátí se jednotková $U $, která používá techniku pro vystavení paměti, k přípravě aproximace $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j $ z čištění matrice hustoty $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $.</span><span class="sxs-lookup"><span data-stu-id="26e5c-106">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="26e5c-107">V této aproximaci je chyba $ \epsilon $ taková, že $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \le \epsilon/N $ a $ \| \tilde\rho-\rho \| \le \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="26e5c-107">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="26e5c-108">Jinými slovy $ $ \begin{align} U\ket {0} ^ {\lceil\ Log_2 N\rceil} \ KET {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\Text{garbage} _J}.</span><span class="sxs-lookup"><span data-stu-id="26e5c-108">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="26e5c-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="26e5c-109">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="26e5c-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="26e5c-110">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="26e5c-111">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="26e5c-111">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="26e5c-112">Cílová chyba $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="26e5c-112">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="26e5c-113">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="26e5c-113">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="26e5c-114">Pole $N $ koeficientů určujících pravděpodobnost základních stavů.</span><span class="sxs-lookup"><span data-stu-id="26e5c-114">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="26e5c-115">Záporná čísla $-\ alpha_j $ se budou považovat za pozitivní $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="26e5c-115">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit-adj--ctl"></a><span data-ttu-id="26e5c-116">Výstup: (([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL)</span><span class="sxs-lookup"><span data-stu-id="26e5c-116">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="26e5c-117">První parametr</span><span class="sxs-lookup"><span data-stu-id="26e5c-117">First parameter</span></span>

<span data-ttu-id="26e5c-118">Řazená kolekce členů `(x,(y,z))` `x = y + z` , kde je celkový počet přidělených qubits, `y` je počet qubits pro `LittleEndian` registr a `z` počet qubitsů paměti.</span><span class="sxs-lookup"><span data-stu-id="26e5c-118">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="26e5c-119">Druhý parametr</span><span class="sxs-lookup"><span data-stu-id="26e5c-119">Second parameter</span></span>

<span data-ttu-id="26e5c-120">Jedna-norma $ \ sum_j | \ alpha_j | $ z pole koeficient.</span><span class="sxs-lookup"><span data-stu-id="26e5c-120">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="26e5c-121">Třetí parametr</span><span class="sxs-lookup"><span data-stu-id="26e5c-121">Third parameter</span></span>

<span data-ttu-id="26e5c-122">Jednotková $U $.</span><span class="sxs-lookup"><span data-stu-id="26e5c-122">The unitary $U$.</span></span>

## <a name="references"></a><span data-ttu-id="26e5c-123">Odkazy</span><span class="sxs-lookup"><span data-stu-id="26e5c-123">References</span></span>

- <span data-ttu-id="26e5c-124">Kódování elektronického spektra v Okruhech v případě využití lineární T, Babbush, Craig Gidney, Dominic W. bobulovin, Nathan Wiebe, Jarrod McClean, Alexandru bledější, Austin Fowlera, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="26e5c-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>