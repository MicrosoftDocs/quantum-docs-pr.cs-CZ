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
# <a name="decomposedon-function"></a>DecomposedOn – funkce

Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vytvoří permutaci pro proměnnou.

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>Popis

Pokud je zadána permutace $ \pi $ ( `perm` ) a index $i $ ( `index` ), tato metoda vrátí tři permutace $ ((\ pi_l, \ pi_r), \pi ') $ tak, že obrázky $ \ pi_l $ a $ \ pi_r $ nemění bity v jejich prvcích v jiných rejstřících než $i $ a image $ \pi $ nemění bitovou $i $ ve svých prvcích.

## <a name="input"></a>Vstup

### <a name="perm--int"></a>Perm: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Výstup: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])



## <a name="example"></a>Příklad

Předpokládejme, že vstup je Perm = [0, 2, 3, 5, 7, 1, 4, 6] a index = 0. Tato funkce vypočítá tři permutace založené na následující tabulce, která obsahuje hodnotu permutace `perm` v binárním zápisu s elementy ve skupině a a obrázky ve skupině D.  Sloupce uvádějí bitové indexy.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 |       |       | 0 0 0 | 0
| 0 0 1 |       |       | 0 1 0 | 2
| 0 1 0 |       |       | 0 1 1 | 3
| 0 1 1 |       |       | 1 0 1 | 5
| 1 0 0 |       |       | 1 1 1 | 7
| 1 0 1 |       |       | 0 0 1 | 1
| 1 1 0 |       |       | 1 0 0 | 4
| 1 1 1 |       |       | 1 1 0 | 6

Všechny hodnoty indexů, které nejsou rovny 0 (= index), jsou zkopírovány z A do B a od D do C.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0   | 0 0   | 0 0 0 |
| 0 0 1 | 0 0   | 0 1   | 0 1 0 |
| 0 1 0 | 0 1   | 0 1   | 0 1 1 |
| 0 1 1 | 0 1   | 1 0   | 1 0 1 |
| 1 0 0 | 1 0   | 1 1   | 1 1 1 |
| 1 0 1 | 1 0   | 0 0   | 0 0 1 |
| 1 1 0 | 1 1   | 1 0   | 1 0 0 |
| 1 1 1 | 1 1   | 1 1   | 1 1 0 |

Vedle hodnoty 0 je umístěn pro první prvek s prázdným indexem ve sloupci 0 v bloku B a potom je hodnota 1 umístěna v hodnotě B, kde odpovídá předpona (v prvním případě druhý řádek s indexy 0 0).
Následně je do stejného řádku v bloku C přidáno číslo 1 a potom pro odpovídající předponu v bloku C bude 0.  Tento proces se opakuje, dokud se všechny indexy neumístily do sloupce 0 v blocích B a C.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0 0 | 0 0 0 | 0 0 0 |
| 0 0 1 | 0 0 1 | 0 1 1 | 0 1 0 |
| 0 1 0 | 0 1 0 | 0 1 0 | 0 1 1 |
| 0 1 1 | 0 1 1 | 1 0 1 | 1 0 1 |
| 1 0 0 | 1 0 0 | 1 1 0 | 1 1 1 |
| 1 0 1 | 1 0 1 | 0 0 1 | 0 0 1 |
| 1 1 0 | 1 1 0 | 1 0 0 | 1 0 0 |
| 1 1 1 | 1 1 1 | 1 1 1 | 1 1 0 |

V tabulce můžeme číst tři nové permutace:

- $ \ pi_l $ s prvky v, obrázky v B (vlevo)
- $ \ pi_r $ s elementy v D, obrázky v C (vpravo)
- $ \pi $ s prvky v B, obrázky v C (zbytek)

Všimněte si, že bitové hodnoty návrhu se nemění v $ \ pi_l $ a $ \ pi_r $ pro indexy 1 a 2 a bitové hodnoty se nemění pro v $ \ pi_ $ pro index 0.  Všimněte si také, že funkce $ \ pi_l $ a $ \ pi_r $ musí být samostatná.

Odvozená a vrácená permutace jsou: Left = [0, 1, 2, 3, 4, 5, 6, 7] Right = [0, 1, 3, 2, 4, 5, 7, 6] zbytek = [0, 3, 2, 5, 6, 1, 4, 7]