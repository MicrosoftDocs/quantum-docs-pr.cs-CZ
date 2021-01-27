---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: Operace AssertOperationsEqualReferenced
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: 045f00a720e9f4d2e6993c66ace44a81e192ff30
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853468"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="271cf-102">Operace AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="271cf-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="271cf-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="271cf-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="271cf-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="271cf-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="271cf-105">Tyto dvě operace vyhodnotí, že jsou identické pro všechny vstupní stavy.</span><span class="sxs-lookup"><span data-stu-id="271cf-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="271cf-106">Tento kontrolní výraz je implementován pomocí Choi – Jamiołkowski isomorphism k omezení kontrolního výrazu na jeden z kontrolního výrazu qubit ve dvou registrech entangled.</span><span class="sxs-lookup"><span data-stu-id="271cf-106">This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers.</span></span>
<span data-ttu-id="271cf-107">Proto tato operace potřebuje pouze jedno volání každé testované operace, ale vyžaduje, aby bylo přiděleno více qubits.</span><span class="sxs-lookup"><span data-stu-id="271cf-107">Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated.</span></span>
<span data-ttu-id="271cf-108">Tento kontrolní výraz lze použít k zajištění toho, aby Optimalizovaná verze operace se shoduje s jeho implementací Naive nebo aby operace, která funguje na řadě nestránkovaného řetězce, souhlasila se známými případy.</span><span class="sxs-lookup"><span data-stu-id="271cf-108">This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.</span></span>

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="271cf-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="271cf-109">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="271cf-110">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="271cf-110">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="271cf-111">Počet qubits, které se mají předat každé operaci</span><span class="sxs-lookup"><span data-stu-id="271cf-111">Number of qubits to pass to each operation.</span></span>


### <a name="actual--qubit--unit"></a><span data-ttu-id="271cf-112">skutečnost: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="271cf-112">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="271cf-113">Operace, která se má testovat</span><span class="sxs-lookup"><span data-stu-id="271cf-113">Operation to be tested.</span></span>


### <a name="expected--qubit--unit--is-adj"></a><span data-ttu-id="271cf-114">očekáváno: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="271cf-114">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="271cf-115">Operace definující očekávané chování testované operace.</span><span class="sxs-lookup"><span data-stu-id="271cf-115">Operation defining the expected behavior for the operation under test.</span></span>



## <a name="output--unit"></a><span data-ttu-id="271cf-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="271cf-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="271cf-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="271cf-117">Remarks</span></span>

<span data-ttu-id="271cf-118">Tato operace vyžaduje, aby byla operace modelování očekávaného chování sousední, aby bylo možné provést invertování pouze v cílovém registru.</span><span class="sxs-lookup"><span data-stu-id="271cf-118">This operation requires that the operation modeling the expected behavior is adjointable, so that the inverse can be performed on the target register alone.</span></span>
<span data-ttu-id="271cf-119">Jedna z nich může určit operaci transpozice, která tento požadavek zmírnit, ale operace transpozice není obecně fyzicky určena pro libovolné operace, a proto zde není obsažena jako možnost.</span><span class="sxs-lookup"><span data-stu-id="271cf-119">Formally, one can specify a transpose operation, which relaxes this requirement, but the transpose operation is not in general physically realizable for arbitrary quantum operations and thus is not included here as an option.</span></span>