---
title: Návrh vlastního třídění pomocí QDK
description: Seznamte se se základními koncepcemi navrhování modelů okruhů pro třídění zaměřené na okruhy.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
ms.openlocfilehash: 4899336f437c1b7712a7831b97fd6ec1431b59a2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909717"
---
# <a name="design-your-own-classifier"></a><span data-ttu-id="e554f-103">Návrh vlastního třídění</span><span class="sxs-lookup"><span data-stu-id="e554f-103">Design your own classifier</span></span>

<span data-ttu-id="e554f-104">V této příručce se dozvíte o základních konceptech za návrh modelů okruhů pro třídění zaměřené na okruhy.</span><span class="sxs-lookup"><span data-stu-id="e554f-104">In this guide you will learn the basic concepts behind the design of circuit models for the quantum circuit centric classifier.</span></span>

<span data-ttu-id="e554f-105">Stejně jako v klasickém podrobném učení neexistuje žádné obecné pravidlo pro výběr konkrétní architektury.</span><span class="sxs-lookup"><span data-stu-id="e554f-105">As in classical deep learning, there is no general rule for choosing a specific architecture.</span></span> <span data-ttu-id="e554f-106">V závislosti na problému bude některé architektury poskytovat lepší výkon než jiné.</span><span class="sxs-lookup"><span data-stu-id="e554f-106">Depending on the problem some architectures will perform better than others.</span></span> <span data-ttu-id="e554f-107">Existují však některé koncepty, které mohou být užitečné při navrhování okruhu:</span><span class="sxs-lookup"><span data-stu-id="e554f-107">But, there are some concepts that might be useful when designing the circuit:</span></span>

- <span data-ttu-id="e554f-108">Velký počet parametrů implikuje flexibilnější model, který může být vhodný pro vykreslení složitých hranic klasifikace, ale může být také náchylnější k přebudování.</span><span class="sxs-lookup"><span data-stu-id="e554f-108">A large number of parameters implies a more flexible model, which may be suitable to draw complicated classification boundaries but which may also be more susceptible to overfitting.</span></span>

- <span data-ttu-id="e554f-109">Entangling brány mezi qubits jsou nezbytné k zachycení korelace mezi funkcemi pro období.</span><span class="sxs-lookup"><span data-stu-id="e554f-109">Entangling gates between qubits are essential to capture the correlations between the quantum features.</span></span>

## <a name="how-to-build-a-classifier-with-q"></a><span data-ttu-id="e554f-110">Postup vytvoření klasifikátoru pomocí Q\#</span><span class="sxs-lookup"><span data-stu-id="e554f-110">How to build a classifier with Q\#</span></span>

<span data-ttu-id="e554f-111">K vytvoření klasifikátoru budeme v modelu okruhu zřetězit zařízená otočení podle typu.</span><span class="sxs-lookup"><span data-stu-id="e554f-111">To build a classifier we are going to concatenate parametrized controlled rotations in our circuit model.</span></span> <span data-ttu-id="e554f-112">K tomu můžeme použít typ [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) definovaný v knihovně Machine Learning pro.</span><span class="sxs-lookup"><span data-stu-id="e554f-112">To do it we can use the type [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) defined in the Quantum Machine Learning library.</span></span> <span data-ttu-id="e554f-113">Tento typ přijímá čtyři argumenty, které určují index cílové qubit, pole indexů ovládacího prvku qubits, osu rotace a index přidruženého parametru v poli parametrů, které definují model.</span><span class="sxs-lookup"><span data-stu-id="e554f-113">This type accepts four arguments that determine: the index of the target qubit, the array of indices of the control qubits, the axis of rotation, and index of the associated parameter in the array of parameters defining the model.</span></span>

<span data-ttu-id="e554f-114">Pojďme se podívat na příklad klasifikátoru.</span><span class="sxs-lookup"><span data-stu-id="e554f-114">Let's see an example of a classifier.</span></span> <span data-ttu-id="e554f-115">V [Moons ukázce](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons)můžeme najít následující klasifikátor definovaný v souboru `Training.qs`.</span><span class="sxs-lookup"><span data-stu-id="e554f-115">In the [half-moons sample](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons), we can find the following classifier defined in the file `Training.qs`.</span></span>

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

<span data-ttu-id="e554f-116">To, co definujeme tady, je funkce, která vrací pole `ControlledRotation` prvků, které spolu s polem parametrů a posunem definují naši [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel).</span><span class="sxs-lookup"><span data-stu-id="e554f-116">What we are defining here is a function that returns an array of `ControlledRotation` elements, that together with an array of parameters and a bias will define our [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel).</span></span> <span data-ttu-id="e554f-117">Tento typ je zásadní v Machine Learning knihovně a definuje třídění.</span><span class="sxs-lookup"><span data-stu-id="e554f-117">This type is fundamental in the Quantum Machine Learning library and defines the classifier.</span></span> <span data-ttu-id="e554f-118">Okruh definovaný v funkci výše je součástí třídění, ve kterém každý vzorek datové sady obsahuje dvě funkce.</span><span class="sxs-lookup"><span data-stu-id="e554f-118">The circuit defined in the function above is part of a classifier in which each sample of the dataset contains two features.</span></span> <span data-ttu-id="e554f-119">Proto potřebujeme jenom dvě qubits.</span><span class="sxs-lookup"><span data-stu-id="e554f-119">Therefore we only need two qubits.</span></span> <span data-ttu-id="e554f-120">Grafické znázornění okruhu je:</span><span class="sxs-lookup"><span data-stu-id="e554f-120">The graphical representation of the circuit is:</span></span>

 ![Příklad modelu okruhu](~/media/circuit_model_1.PNG)

## <a name="use-the-library-functions-to-write-layers-of-gates"></a><span data-ttu-id="e554f-122">Použití funkcí knihovny k psaní vrstev bran</span><span class="sxs-lookup"><span data-stu-id="e554f-122">Use the library functions to write layers of gates</span></span>

<span data-ttu-id="e554f-123">Předpokládejme, že máme datovou sadu s 784 funkcemi na jednu instanci, například obrázky o 28 × 28 pixelů, jako je MNIST ručně zapsaných datová sada.</span><span class="sxs-lookup"><span data-stu-id="e554f-123">Suppose we have a dataset with 784 features per instance, e.g. images of 28×28 pixels like the MNIST dataset.</span></span> <span data-ttu-id="e554f-124">V takovém případě se šířka okruhu zvětší dostatečně velká, takže se každá z jednotlivých bran může stát možnou, ale nepraktickou úlohou.</span><span class="sxs-lookup"><span data-stu-id="e554f-124">In this case, the width of the circuit becomes large enough so that writing by hand each individual gate becomes a possible but impractical task.</span></span> <span data-ttu-id="e554f-125">To je důvod, proč Machine Learning Library poskytuje sadu nástrojů pro automatické generování vrstev přeotočení.</span><span class="sxs-lookup"><span data-stu-id="e554f-125">This is why the Quantum Machine Learning library provides a set of tools to automatically generate layers of parametrized rotations.</span></span> <span data-ttu-id="e554f-126">Například funkce [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) vrátí pole neřízených qubit otočení podél dané osy, s jedním otočením pro každý qubit v registru, přičemž každý parametr odkazuje na jiný model.</span><span class="sxs-lookup"><span data-stu-id="e554f-126">For instance, the function [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) returns an array of uncontrolled single-qubit rotations along a given axis, with one rotation for each qubit in the register, each parametrized by a different model parameter.</span></span> <span data-ttu-id="e554f-127">`LocalRotationsLayer(4, X)` například vrátí následující sadu bran:</span><span class="sxs-lookup"><span data-stu-id="e554f-127">For example, `LocalRotationsLayer(4, X)` returns the following set of gates:</span></span>

 ![Místní vrstva rotací](~/media/local_rotations_layer.PNG)

<span data-ttu-id="e554f-129">Doporučujeme, abyste si prozkoumali [Referenece rozhraní API Machine Learning knihovně](xref:microsoft.quantum.machinelearning) pro zjišťování všech nástrojů, které jsou k dispozici pro zjednodušení návrhu okruhu.</span><span class="sxs-lookup"><span data-stu-id="e554f-129">We recommend you to explore the [API referenece of the Quantum Machine Learning library](xref:microsoft.quantum.machinelearning) to discover all the tools available to streamline the circuit design.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e554f-130">Další kroky</span><span class="sxs-lookup"><span data-stu-id="e554f-130">Next steps</span></span>

 <span data-ttu-id="e554f-131">Vyzkoušejte různé struktury v příkladech, které jsou k dispozici v ukázkách.</span><span class="sxs-lookup"><span data-stu-id="e554f-131">Try different structures in the examples provided by the samples.</span></span> <span data-ttu-id="e554f-132">Vidíte všechny změny v výkonu modelu?</span><span class="sxs-lookup"><span data-stu-id="e554f-132">Do you see any changes in the performance of the model?</span></span> <span data-ttu-id="e554f-133">V dalším [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load)kurzu se naučíte, jak načíst datové sady, abyste mohli vyzkoušet a prozkoumat nové architektury klasifikátorů.</span><span class="sxs-lookup"><span data-stu-id="e554f-133">In the next tutorial, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load), you will learn how to load datasets to try and explore new architectures of classifiers.</span></span>
