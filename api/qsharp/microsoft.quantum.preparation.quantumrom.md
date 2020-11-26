---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  > [!WARNING]

  > QuantumROM has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.


  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 1ee805fb2ea02121daaab7fc3eb5dbbcb134b470
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229881"
---
# <a name="quantumrom-function"></a><span data-ttu-id="2ec0f-102">QuantumROM – funkce</span><span class="sxs-lookup"><span data-stu-id="2ec0f-102">QuantumROM function</span></span>

<span data-ttu-id="2ec0f-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="2ec0f-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="2ec0f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2ec0f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="2ec0f-105">QuantumROM se už nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-105">QuantumROM has been deprecated.</span></span> <span data-ttu-id="2ec0f-106"><xref:Microsoft.Quantum.Preparation.PurifiedMixedState>Místo toho ho použijte.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.</span></span>

<span data-ttu-id="2ec0f-107">Vystupuje danou matici hustoty pomocí techniky paměti pro paměťová pole.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-107">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="2ec0f-108">V případě, že se zobrazí seznam $N alpha_j $ \ket{j}\bra{j} $, vrátí se jednotková $U $, která používá techniku pro vystavení paměti, k přípravě aproximace $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j $ z čištění matrice hustoty $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-108">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="2ec0f-109">V této aproximaci je chyba $ \epsilon $ taková, že $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \le \epsilon/N $ a $ \| \tilde\rho-\rho \| \le \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-109">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="2ec0f-110">Jinými slovy $ $ \begin{align} U\ket {0} ^ {\lceil\ Log_2 N\rceil} \ KET {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\Text{garbage} _J}.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-110">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="2ec0f-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="2ec0f-111">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="2ec0f-112">Vstup</span><span class="sxs-lookup"><span data-stu-id="2ec0f-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="2ec0f-113">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2ec0f-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2ec0f-114">Cílová chyba $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="2ec0f-115">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="2ec0f-115">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="2ec0f-116">Pole $N $ koeficientů určujících pravděpodobnost základních stavů.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-116">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="2ec0f-117">Záporná čísla $-\ alpha_j $ se budou považovat za pozitivní $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="2ec0f-118">Výstup: (([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL)</span><span class="sxs-lookup"><span data-stu-id="2ec0f-118">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="2ec0f-119">První parametr</span><span class="sxs-lookup"><span data-stu-id="2ec0f-119">First parameter</span></span>

<span data-ttu-id="2ec0f-120">Řazená kolekce členů `(x,(y,z))` `x = y + z` , kde je celkový počet přidělených qubits, `y` je počet qubits pro `LittleEndian` registr a `z` počet qubitsů paměti.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-120">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="2ec0f-121">Druhý parametr</span><span class="sxs-lookup"><span data-stu-id="2ec0f-121">Second parameter</span></span>

<span data-ttu-id="2ec0f-122">Jedna-norma $ \ sum_j | \ alpha_j | $ z pole koeficient.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-122">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="2ec0f-123">Třetí parametr</span><span class="sxs-lookup"><span data-stu-id="2ec0f-123">Third parameter</span></span>

<span data-ttu-id="2ec0f-124">Jednotková $U $.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-124">The unitary $U$.</span></span>

## <a name="references"></a><span data-ttu-id="2ec0f-125">Reference</span><span class="sxs-lookup"><span data-stu-id="2ec0f-125">References</span></span>

- <span data-ttu-id="2ec0f-126">Kódování elektronického spektra v Okruhech v případě využití lineární T, Babbush, Craig Gidney, Dominic W. bobulovin, Nathan Wiebe, Jarrod McClean, Alexandru bledější, Austin Fowlera, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="2ec0f-126">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>