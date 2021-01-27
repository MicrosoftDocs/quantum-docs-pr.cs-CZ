---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855531"
---
# <a name="decomposedon-function"></a><span data-ttu-id="6813a-102">DecomposedOn – funkce</span><span class="sxs-lookup"><span data-stu-id="6813a-102">DecomposedOn function</span></span>

<span data-ttu-id="6813a-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="6813a-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="6813a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6813a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6813a-105">Vytvoří permutaci pro proměnnou.</span><span class="sxs-lookup"><span data-stu-id="6813a-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="6813a-106">Popis</span><span class="sxs-lookup"><span data-stu-id="6813a-106">Description</span></span>

<span data-ttu-id="6813a-107">Pokud je zadána permutace $ \pi $ ( `perm` ) a index $i $ ( `index` ), tato metoda vrátí tři permutace $ ((\ pi_l, \ pi_r), \pi ') $ tak, že obrázky $ \ pi_l $ a $ \ pi_r $ nemění bity v jejich prvcích v jiných rejstřících než $i $ a image $ \pi $ nemění bitovou $i $ ve svých prvcích.</span><span class="sxs-lookup"><span data-stu-id="6813a-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="6813a-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="6813a-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="6813a-109">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6813a-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="6813a-110">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6813a-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="6813a-111">Výstup: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="6813a-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>



## <a name="example"></a><span data-ttu-id="6813a-112">Příklad</span><span class="sxs-lookup"><span data-stu-id="6813a-112">Example</span></span>

<span data-ttu-id="6813a-113">Předpokládejme, že vstup je Perm = [0, 2, 3, 5, 7, 1, 4, 6] a index = 0. Tato funkce vypočítá tři permutace založené na následující tabulce, která obsahuje hodnotu permutace `perm` v binárním zápisu s elementy ve skupině a a obrázky ve skupině D.  Sloupce uvádějí bitové indexy.</span><span class="sxs-lookup"><span data-stu-id="6813a-113">Assume that the input is perm = [0, 2, 3, 5, 7, 1, 4, 6] and index = 0, then this function computes three permutations based on the following table, which lists the permutation `perm` in binary notation with elements in group A and images in group D.  The columns list the bit indices.</span></span>

<span data-ttu-id="6813a-114">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="6813a-114">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="6813a-115">2 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-115">2 1 0</span></span> | <span data-ttu-id="6813a-116">2 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-116">2 1 0</span></span> | <span data-ttu-id="6813a-117">2 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-117">2 1 0</span></span> | <span data-ttu-id="6813a-118">2 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-118">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="6813a-119">0 0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-119">0 0 0</span></span> |       |       | <span data-ttu-id="6813a-120">0 0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-120">0 0 0</span></span> | <span data-ttu-id="6813a-121">0</span><span class="sxs-lookup"><span data-stu-id="6813a-121">0</span></span>
| <span data-ttu-id="6813a-122">0 0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-122">0 0 1</span></span> |       |       | <span data-ttu-id="6813a-123">0 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-123">0 1 0</span></span> | <span data-ttu-id="6813a-124">2</span><span class="sxs-lookup"><span data-stu-id="6813a-124">2</span></span>
| <span data-ttu-id="6813a-125">0 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-125">0 1 0</span></span> |       |       | <span data-ttu-id="6813a-126">0 1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-126">0 1 1</span></span> | <span data-ttu-id="6813a-127">3</span><span class="sxs-lookup"><span data-stu-id="6813a-127">3</span></span>
| <span data-ttu-id="6813a-128">0 1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-128">0 1 1</span></span> |       |       | <span data-ttu-id="6813a-129">1 0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-129">1 0 1</span></span> | <span data-ttu-id="6813a-130">5</span><span class="sxs-lookup"><span data-stu-id="6813a-130">5</span></span>
| <span data-ttu-id="6813a-131">1 0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-131">1 0 0</span></span> |       |       | <span data-ttu-id="6813a-132">1 1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-132">1 1 1</span></span> | <span data-ttu-id="6813a-133">7</span><span class="sxs-lookup"><span data-stu-id="6813a-133">7</span></span>
| <span data-ttu-id="6813a-134">1 0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-134">1 0 1</span></span> |       |       | <span data-ttu-id="6813a-135">0 0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-135">0 0 1</span></span> | <span data-ttu-id="6813a-136">1</span><span class="sxs-lookup"><span data-stu-id="6813a-136">1</span></span>
| <span data-ttu-id="6813a-137">1 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-137">1 1 0</span></span> |       |       | <span data-ttu-id="6813a-138">1 0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-138">1 0 0</span></span> | <span data-ttu-id="6813a-139">4</span><span class="sxs-lookup"><span data-stu-id="6813a-139">4</span></span>
| <span data-ttu-id="6813a-140">1 1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-140">1 1 1</span></span> |       |       | <span data-ttu-id="6813a-141">1 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-141">1 1 0</span></span> | <span data-ttu-id="6813a-142">6</span><span class="sxs-lookup"><span data-stu-id="6813a-142">6</span></span>

<span data-ttu-id="6813a-143">Všechny hodnoty indexů, které nejsou rovny 0 (= index), jsou zkopírovány z A do B a od D do C.</span><span class="sxs-lookup"><span data-stu-id="6813a-143">All values for indices not equal to 0 (= index) are copied from A to B and from D to C.</span></span>

<span data-ttu-id="6813a-144">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="6813a-144">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="6813a-145">2 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-145">2 1 0</span></span> | <span data-ttu-id="6813a-146">2 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-146">2 1 0</span></span> | <span data-ttu-id="6813a-147">2 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-147">2 1 0</span></span> | <span data-ttu-id="6813a-148">2 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-148">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="6813a-149">0 0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-149">0 0 0</span></span> | <span data-ttu-id="6813a-150">0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-150">0 0</span></span>   | <span data-ttu-id="6813a-151">0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-151">0 0</span></span>   | <span data-ttu-id="6813a-152">0 0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-152">0 0 0</span></span> |
| <span data-ttu-id="6813a-153">0 0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-153">0 0 1</span></span> | <span data-ttu-id="6813a-154">0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-154">0 0</span></span>   | <span data-ttu-id="6813a-155">0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-155">0 1</span></span>   | <span data-ttu-id="6813a-156">0 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-156">0 1 0</span></span> |
| <span data-ttu-id="6813a-157">0 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-157">0 1 0</span></span> | <span data-ttu-id="6813a-158">0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-158">0 1</span></span>   | <span data-ttu-id="6813a-159">0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-159">0 1</span></span>   | <span data-ttu-id="6813a-160">0 1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-160">0 1 1</span></span> |
| <span data-ttu-id="6813a-161">0 1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-161">0 1 1</span></span> | <span data-ttu-id="6813a-162">0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-162">0 1</span></span>   | <span data-ttu-id="6813a-163">1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-163">1 0</span></span>   | <span data-ttu-id="6813a-164">1 0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-164">1 0 1</span></span> |
| <span data-ttu-id="6813a-165">1 0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-165">1 0 0</span></span> | <span data-ttu-id="6813a-166">1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-166">1 0</span></span>   | <span data-ttu-id="6813a-167">1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-167">1 1</span></span>   | <span data-ttu-id="6813a-168">1 1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-168">1 1 1</span></span> |
| <span data-ttu-id="6813a-169">1 0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-169">1 0 1</span></span> | <span data-ttu-id="6813a-170">1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-170">1 0</span></span>   | <span data-ttu-id="6813a-171">0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-171">0 0</span></span>   | <span data-ttu-id="6813a-172">0 0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-172">0 0 1</span></span> |
| <span data-ttu-id="6813a-173">1 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-173">1 1 0</span></span> | <span data-ttu-id="6813a-174">1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-174">1 1</span></span>   | <span data-ttu-id="6813a-175">1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-175">1 0</span></span>   | <span data-ttu-id="6813a-176">1 0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-176">1 0 0</span></span> |
| <span data-ttu-id="6813a-177">1 1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-177">1 1 1</span></span> | <span data-ttu-id="6813a-178">1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-178">1 1</span></span>   | <span data-ttu-id="6813a-179">1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-179">1 1</span></span>   | <span data-ttu-id="6813a-180">1 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-180">1 1 0</span></span> |

<span data-ttu-id="6813a-181">Vedle hodnoty 0 je umístěn pro první prvek s prázdným indexem ve sloupci 0 v bloku B a potom je hodnota 1 umístěna v hodnotě B, kde odpovídá předpona (v prvním případě druhý řádek s indexy 0 0).</span><span class="sxs-lookup"><span data-stu-id="6813a-181">Next a 0 is placed for the first element with an empty index at column 0 in block B and then a 1 is placed in B where the prefix matches (in the first case the other row with indices 0 0).</span></span>
<span data-ttu-id="6813a-182">Následně je do stejného řádku v bloku C přidáno číslo 1 a potom pro odpovídající předponu v bloku C bude 0.  Tento proces se opakuje, dokud se všechny indexy neumístily do sloupce 0 v blocích B a C.</span><span class="sxs-lookup"><span data-stu-id="6813a-182">Afterwards, a 1 is added in the same row in block C, and then a 0 for the corresponding prefix in block C.  This process is repeated, until all indices have been placed in column 0 in blocks B and C.</span></span>

<span data-ttu-id="6813a-183">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="6813a-183">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="6813a-184">2 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-184">2 1 0</span></span> | <span data-ttu-id="6813a-185">2 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-185">2 1 0</span></span> | <span data-ttu-id="6813a-186">2 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-186">2 1 0</span></span> | <span data-ttu-id="6813a-187">2 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-187">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="6813a-188">0 0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-188">0 0 0</span></span> | <span data-ttu-id="6813a-189">0 0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-189">0 0 0</span></span> | <span data-ttu-id="6813a-190">0 0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-190">0 0 0</span></span> | <span data-ttu-id="6813a-191">0 0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-191">0 0 0</span></span> |
| <span data-ttu-id="6813a-192">0 0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-192">0 0 1</span></span> | <span data-ttu-id="6813a-193">0 0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-193">0 0 1</span></span> | <span data-ttu-id="6813a-194">0 1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-194">0 1 1</span></span> | <span data-ttu-id="6813a-195">0 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-195">0 1 0</span></span> |
| <span data-ttu-id="6813a-196">0 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-196">0 1 0</span></span> | <span data-ttu-id="6813a-197">0 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-197">0 1 0</span></span> | <span data-ttu-id="6813a-198">0 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-198">0 1 0</span></span> | <span data-ttu-id="6813a-199">0 1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-199">0 1 1</span></span> |
| <span data-ttu-id="6813a-200">0 1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-200">0 1 1</span></span> | <span data-ttu-id="6813a-201">0 1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-201">0 1 1</span></span> | <span data-ttu-id="6813a-202">1 0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-202">1 0 1</span></span> | <span data-ttu-id="6813a-203">1 0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-203">1 0 1</span></span> |
| <span data-ttu-id="6813a-204">1 0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-204">1 0 0</span></span> | <span data-ttu-id="6813a-205">1 0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-205">1 0 0</span></span> | <span data-ttu-id="6813a-206">1 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-206">1 1 0</span></span> | <span data-ttu-id="6813a-207">1 1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-207">1 1 1</span></span> |
| <span data-ttu-id="6813a-208">1 0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-208">1 0 1</span></span> | <span data-ttu-id="6813a-209">1 0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-209">1 0 1</span></span> | <span data-ttu-id="6813a-210">0 0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-210">0 0 1</span></span> | <span data-ttu-id="6813a-211">0 0 1</span><span class="sxs-lookup"><span data-stu-id="6813a-211">0 0 1</span></span> |
| <span data-ttu-id="6813a-212">1 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-212">1 1 0</span></span> | <span data-ttu-id="6813a-213">1 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-213">1 1 0</span></span> | <span data-ttu-id="6813a-214">1 0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-214">1 0 0</span></span> | <span data-ttu-id="6813a-215">1 0 0</span><span class="sxs-lookup"><span data-stu-id="6813a-215">1 0 0</span></span> |
| <span data-ttu-id="6813a-216">1 1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-216">1 1 1</span></span> | <span data-ttu-id="6813a-217">1 1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-217">1 1 1</span></span> | <span data-ttu-id="6813a-218">1 1 1</span><span class="sxs-lookup"><span data-stu-id="6813a-218">1 1 1</span></span> | <span data-ttu-id="6813a-219">1 1 0</span><span class="sxs-lookup"><span data-stu-id="6813a-219">1 1 0</span></span> |

<span data-ttu-id="6813a-220">V tabulce můžeme číst tři nové permutace:</span><span class="sxs-lookup"><span data-stu-id="6813a-220">We can read three new permutations from the table:</span></span>

- <span data-ttu-id="6813a-221">$ \ pi_l $ s prvky v, obrázky v B (vlevo)</span><span class="sxs-lookup"><span data-stu-id="6813a-221">$\pi_l$ with elements in A, images in B (left)</span></span>
- <span data-ttu-id="6813a-222">$ \ pi_r $ s elementy v D, obrázky v C (vpravo)</span><span class="sxs-lookup"><span data-stu-id="6813a-222">$\pi_r$ with elements in D, images in C (right)</span></span>
- <span data-ttu-id="6813a-223">$ \pi $ s prvky v B, obrázky v C (zbytek)</span><span class="sxs-lookup"><span data-stu-id="6813a-223">$\pi'$  with elements in B, images in C (remainder)</span></span>

<span data-ttu-id="6813a-224">Všimněte si, že bitové hodnoty návrhu se nemění v $ \ pi_l $ a $ \ pi_r $ pro indexy 1 a 2 a bitové hodnoty se nemění pro v $ \ pi_ $ pro index 0.</span><span class="sxs-lookup"><span data-stu-id="6813a-224">Note that by design bit values do not change in $\pi_l$ and $\pi_r$ for indices 1 and 2, and bit values do not change for in $\pi_'$ for index 0.</span></span>  <span data-ttu-id="6813a-225">Všimněte si také, že funkce $ \ pi_l $ a $ \ pi_r $ musí být samostatná.</span><span class="sxs-lookup"><span data-stu-id="6813a-225">Also note that $\pi_l$ and $\pi_r$ must be self-inverse.</span></span>

<span data-ttu-id="6813a-226">Odvozená a vrácená permutace jsou: Left = [0, 1, 2, 3, 4, 5, 6, 7] Right = [0, 1, 3, 2, 4, 5, 7, 6] zbytek = [0, 3, 2, 5, 6, 1, 4, 7]</span><span class="sxs-lookup"><span data-stu-id="6813a-226">The derived and returned permutations are: left      = [0, 1, 2, 3, 4, 5, 6, 7] right     = [0, 1, 3, 2, 4, 5, 7, 6] remainder = [0, 3, 2, 5, 6, 1, 4, 7]</span></span>