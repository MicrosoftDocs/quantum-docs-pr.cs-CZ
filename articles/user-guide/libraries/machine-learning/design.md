---
title: Návrh vlastního třídění pomocí QDK
description: Seznamte se se základními koncepcemi navrhování modelů okruhů pro třídění zaměřené na okruhy.
author: geduardo
ms.author: v-edsanc
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 221479e616ff7a03c4ac20e0062125660314e95b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691151"
---
# <a name="design-your-own-classifier"></a>Návrh vlastního klasifikátoru

V této příručce se dozvíte o základních konceptech za návrh modelů okruhů pro třídění zaměřené na okruhy.

Stejně jako v klasickém podrobném učení neexistuje žádné obecné pravidlo pro výběr konkrétní architektury. V závislosti na problému bude některé architektury poskytovat lepší výkon než jiné. Existují však některé koncepty, které mohou být užitečné při navrhování okruhu:

- Velký počet parametrů implikuje flexibilnější model, který může být vhodný pro vykreslení složitých hranic klasifikace, ale může být také náchylnější k přebudování.

- Entangling brány mezi qubits jsou nezbytné k zachycení korelace mezi funkcemi pro období.

## <a name="how-to-build-a-classifier-with-q"></a>Postup vytvoření klasifikátoru pomocí Q\#

K vytvoření klasifikátoru budeme v modelu okruhu zřetězit zařízená otočení podle typu. K tomu můžeme použít typ [`ControlledRotation`](xref:Microsoft.Quantum.MachineLearning.ControlledRotation) definovaný v Machine Learning knihovně. Tento typ přijímá čtyři argumenty, které určují index cílové qubit, pole indexů ovládacího prvku qubits, osu rotace a index přidruženého parametru v poli parametrů, které definují model.

Pojďme se podívat na příklad klasifikátoru. V [Moons ukázce](https://github.com/microsoft/Quantum/tree/main/samples/machine-learning/half-moons)můžeme najít následující klasifikátor definovaný v souboru `Training.qs` .

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

To, co definujeme tady, je funkce, která vrací pole `ControlledRotation` prvků, které spolu s polem parametrů a posunem definují [`SequentialModel`](xref:Microsoft.Quantum.MachineLearning.SequentialModel) . Tento typ je zásadní v Machine Learning knihovně a definuje třídění. Okruh definovaný v funkci výše je součástí třídění, ve kterém každý vzorek datové sady obsahuje dvě funkce. Proto potřebujeme jenom dvě qubits. Grafické znázornění okruhu je:

 ![Příklad modelu okruhu](~/media/circuit_model_1.PNG)

Všimněte si, že ve výchozím nastavení operace Machine Learning v rámci knihovny měří poslední qubit registru k odhadu pravděpodobností klasifikace. Měli byste si pamatovat na tento fakt při navrhování okruhu.

## <a name="use-the-library-functions-to-write-layers-of-gates"></a>Použití funkcí knihovny k psaní vrstev bran

Předpokládejme, že máme datovou sadu s 784 funkcemi na jednu instanci, například obrázky o 28 × 28 pixelů, jako je MNIST ručně zapsaných datová sada. V takovém případě se šířka okruhu zvětší dostatečně velká, takže se každá z jednotlivých bran může stát možnou, ale nepraktickou úlohou. To je důvod, proč Machine Learning Library poskytuje sadu nástrojů pro automatické generování vrstev přeotočení. Například funkce [`LocalRotationsLayer`](xref:Microsoft.Quantum.MachineLearning.LocalRotationsLayer) vrátí pole neřízených jednoduchých qubit otočení podél dané osy, s jedním otočením pro každý qubit v registru, přičemž každý parametr odkazuje na jiný model. Například `LocalRotationsLayer(4, X)` vrátí následující sadu bran:

 ![Místní vrstva rotací](~/media/local_rotations_layer.PNG)

Doporučujeme, abyste si prozkoumali [referenční materiály k rozhraní API Machine Learning knihovně](xref:Microsoft.Quantum.MachineLearning) za účelem zjištění všech dostupných nástrojů pro zjednodušení návrhu okruhu.

## <a name="next-steps"></a>Další kroky

 Vyzkoušejte různé struktury v příkladech, které jsou k dispozici v ukázkách. Vidíte všechny změny v výkonu modelu? V dalším kurzu se [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) naučíte načíst datové sady a vyzkoušet si nové architektury klasifikátorů.
