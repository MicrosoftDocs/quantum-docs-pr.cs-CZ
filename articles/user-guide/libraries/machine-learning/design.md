---
title: Návrh vlastního třídění pomocí QDK
description: Seznamte se se základními koncepcemi navrhování modelů okruhů pro třídění zaměřené na okruhy.
author: geduardo
ms.author: v-edsanc
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 221479e616ff7a03c4ac20e0062125660314e95b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691151"
---
# <a name="design-your-own-classifier"></a><span data-ttu-id="d372a-103">Návrh vlastního klasifikátoru</span><span class="sxs-lookup"><span data-stu-id="d372a-103">Design your own classifier</span></span>

<span data-ttu-id="d372a-104">V této příručce se dozvíte o základních konceptech za návrh modelů okruhů pro třídění zaměřené na okruhy.</span><span class="sxs-lookup"><span data-stu-id="d372a-104">In this guide you will learn the basic concepts behind the design of circuit models for the quantum circuit centric classifier.</span></span>

<span data-ttu-id="d372a-105">Stejně jako v klasickém podrobném učení neexistuje žádné obecné pravidlo pro výběr konkrétní architektury.</span><span class="sxs-lookup"><span data-stu-id="d372a-105">As in classical deep learning, there is no general rule for choosing a specific architecture.</span></span> <span data-ttu-id="d372a-106">V závislosti na problému bude některé architektury poskytovat lepší výkon než jiné.</span><span class="sxs-lookup"><span data-stu-id="d372a-106">Depending on the problem some architectures will perform better than others.</span></span> <span data-ttu-id="d372a-107">Existují však některé koncepty, které mohou být užitečné při navrhování okruhu:</span><span class="sxs-lookup"><span data-stu-id="d372a-107">But, there are some concepts that might be useful when designing the circuit:</span></span>

- <span data-ttu-id="d372a-108">Velký počet parametrů implikuje flexibilnější model, který může být vhodný pro vykreslení složitých hranic klasifikace, ale může být také náchylnější k přebudování.</span><span class="sxs-lookup"><span data-stu-id="d372a-108">A large number of parameters implies a more flexible model, which may be suitable to draw complicated classification boundaries but which may also be more susceptible to overfitting.</span></span>

- <span data-ttu-id="d372a-109">Entangling brány mezi qubits jsou nezbytné k zachycení korelace mezi funkcemi pro období.</span><span class="sxs-lookup"><span data-stu-id="d372a-109">Entangling gates between qubits are essential to capture the correlations between the quantum features.</span></span>

## <a name="how-to-build-a-classifier-with-q"></a><span data-ttu-id="d372a-110">Postup vytvoření klasifikátoru pomocí Q\#</span><span class="sxs-lookup"><span data-stu-id="d372a-110">How to build a classifier with Q\#</span></span>

<span data-ttu-id="d372a-111">K vytvoření klasifikátoru budeme v modelu okruhu zřetězit zařízená otočení podle typu.</span><span class="sxs-lookup"><span data-stu-id="d372a-111">To build a classifier we are going to concatenate parametrized controlled rotations in our circuit model.</span></span> <span data-ttu-id="d372a-112">K tomu můžeme použít typ [`ControlledRotation`](xref:Microsoft.Quantum.MachineLearning.ControlledRotation) definovaný v Machine Learning knihovně.</span><span class="sxs-lookup"><span data-stu-id="d372a-112">To do it we can use the type [`ControlledRotation`](xref:Microsoft.Quantum.MachineLearning.ControlledRotation) defined in the Quantum Machine Learning library.</span></span> <span data-ttu-id="d372a-113">Tento typ přijímá čtyři argumenty, které určují index cílové qubit, pole indexů ovládacího prvku qubits, osu rotace a index přidruženého parametru v poli parametrů, které definují model.</span><span class="sxs-lookup"><span data-stu-id="d372a-113">This type accepts four arguments that determine: the index of the target qubit, the array of indices of the control qubits, the axis of rotation, and index of the associated parameter in the array of parameters defining the model.</span></span>

<span data-ttu-id="d372a-114">Pojďme se podívat na příklad klasifikátoru.</span><span class="sxs-lookup"><span data-stu-id="d372a-114">Let's see an example of a classifier.</span></span> <span data-ttu-id="d372a-115">V [Moons ukázce](https://github.com/microsoft/Quantum/tree/main/samples/machine-learning/half-moons)můžeme najít následující klasifikátor definovaný v souboru `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="d372a-115">In the [half-moons sample](https://github.com/microsoft/Quantum/tree/main/samples/machine-learning/half-moons), we can find the following classifier defined in the file `Training.qs`.</span></span>

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

<span data-ttu-id="d372a-116">To, co definujeme tady, je funkce, která vrací pole `ControlledRotation` prvků, které spolu s polem parametrů a posunem definují [`SequentialModel`](xref:Microsoft.Quantum.MachineLearning.SequentialModel) .</span><span class="sxs-lookup"><span data-stu-id="d372a-116">What we are defining here is a function that returns an array of `ControlledRotation` elements, that together with an array of parameters and a bias will define our [`SequentialModel`](xref:Microsoft.Quantum.MachineLearning.SequentialModel).</span></span> <span data-ttu-id="d372a-117">Tento typ je zásadní v Machine Learning knihovně a definuje třídění.</span><span class="sxs-lookup"><span data-stu-id="d372a-117">This type is fundamental in the Quantum Machine Learning library and defines the classifier.</span></span> <span data-ttu-id="d372a-118">Okruh definovaný v funkci výše je součástí třídění, ve kterém každý vzorek datové sady obsahuje dvě funkce.</span><span class="sxs-lookup"><span data-stu-id="d372a-118">The circuit defined in the function above is part of a classifier in which each sample of the dataset contains two features.</span></span> <span data-ttu-id="d372a-119">Proto potřebujeme jenom dvě qubits.</span><span class="sxs-lookup"><span data-stu-id="d372a-119">Therefore we only need two qubits.</span></span> <span data-ttu-id="d372a-120">Grafické znázornění okruhu je:</span><span class="sxs-lookup"><span data-stu-id="d372a-120">The graphical representation of the circuit is:</span></span>

 ![Příklad modelu okruhu](~/media/circuit_model_1.PNG)

<span data-ttu-id="d372a-122">Všimněte si, že ve výchozím nastavení operace Machine Learning v rámci knihovny měří poslední qubit registru k odhadu pravděpodobností klasifikace.</span><span class="sxs-lookup"><span data-stu-id="d372a-122">Note that by default the operations of the Quantum Machine Learning library measure the last qubit of the register to estimate the classification probabilities.</span></span> <span data-ttu-id="d372a-123">Měli byste si pamatovat na tento fakt při navrhování okruhu.</span><span class="sxs-lookup"><span data-stu-id="d372a-123">You should keep in mind this fact when designing your circuit.</span></span>

## <a name="use-the-library-functions-to-write-layers-of-gates"></a><span data-ttu-id="d372a-124">Použití funkcí knihovny k psaní vrstev bran</span><span class="sxs-lookup"><span data-stu-id="d372a-124">Use the library functions to write layers of gates</span></span>

<span data-ttu-id="d372a-125">Předpokládejme, že máme datovou sadu s 784 funkcemi na jednu instanci, například obrázky o 28 × 28 pixelů, jako je MNIST ručně zapsaných datová sada.</span><span class="sxs-lookup"><span data-stu-id="d372a-125">Suppose we have a dataset with 784 features per instance, e.g. images of 28×28 pixels like the MNIST dataset.</span></span> <span data-ttu-id="d372a-126">V takovém případě se šířka okruhu zvětší dostatečně velká, takže se každá z jednotlivých bran může stát možnou, ale nepraktickou úlohou.</span><span class="sxs-lookup"><span data-stu-id="d372a-126">In this case, the width of the circuit becomes large enough so that writing by hand each individual gate becomes a possible but impractical task.</span></span> <span data-ttu-id="d372a-127">To je důvod, proč Machine Learning Library poskytuje sadu nástrojů pro automatické generování vrstev přeotočení.</span><span class="sxs-lookup"><span data-stu-id="d372a-127">This is why the Quantum Machine Learning library provides a set of tools to automatically generate layers of parametrized rotations.</span></span> <span data-ttu-id="d372a-128">Například funkce [`LocalRotationsLayer`](xref:Microsoft.Quantum.MachineLearning.LocalRotationsLayer) vrátí pole neřízených jednoduchých qubit otočení podél dané osy, s jedním otočením pro každý qubit v registru, přičemž každý parametr odkazuje na jiný model.</span><span class="sxs-lookup"><span data-stu-id="d372a-128">For instance, the function [`LocalRotationsLayer`](xref:Microsoft.Quantum.MachineLearning.LocalRotationsLayer) returns an array of uncontrolled single-qubit rotations along a given axis, with one rotation for each qubit in the register, each parametrized by a different model parameter.</span></span> <span data-ttu-id="d372a-129">Například `LocalRotationsLayer(4, X)` vrátí následující sadu bran:</span><span class="sxs-lookup"><span data-stu-id="d372a-129">For example, `LocalRotationsLayer(4, X)` returns the following set of gates:</span></span>

 ![Místní vrstva rotací](~/media/local_rotations_layer.PNG)

<span data-ttu-id="d372a-131">Doporučujeme, abyste si prozkoumali [referenční materiály k rozhraní API Machine Learning knihovně](xref:Microsoft.Quantum.MachineLearning) za účelem zjištění všech dostupných nástrojů pro zjednodušení návrhu okruhu.</span><span class="sxs-lookup"><span data-stu-id="d372a-131">We recommend you explore the [API reference of the Quantum Machine Learning library](xref:Microsoft.Quantum.MachineLearning) to discover all the tools available to streamline the circuit design.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d372a-132">Další kroky</span><span class="sxs-lookup"><span data-stu-id="d372a-132">Next steps</span></span>

 <span data-ttu-id="d372a-133">Vyzkoušejte různé struktury v příkladech, které jsou k dispozici v ukázkách.</span><span class="sxs-lookup"><span data-stu-id="d372a-133">Try different structures in the examples provided by the samples.</span></span> <span data-ttu-id="d372a-134">Vidíte všechny změny v výkonu modelu?</span><span class="sxs-lookup"><span data-stu-id="d372a-134">Do you see any changes in the performance of the model?</span></span> <span data-ttu-id="d372a-135">V dalším kurzu se [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) naučíte načíst datové sady a vyzkoušet si nové architektury klasifikátorů.</span><span class="sxs-lookup"><span data-stu-id="d372a-135">In the next tutorial, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load), you will learn how to load datasets to try and explore new architectures of classifiers.</span></span>
