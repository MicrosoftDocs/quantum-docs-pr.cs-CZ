---
title: Diracova notace
description: Přečtěte si, jak používat zápis Dirac, který představuje stavy a simuluje operace.
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 958910452109fc722999acddd70894c458e38357
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630388"
---
# <a name="dirac-notation"></a><span data-ttu-id="45269-103">Zápis Dirac</span><span class="sxs-lookup"><span data-stu-id="45269-103">Dirac Notation</span></span>

<span data-ttu-id="45269-104">V případě, že je všudypřítomný vektorového zápisu v lineárním algebraický, je často náročný na výpočetní výkon, zejména při práci s více qubits.</span><span class="sxs-lookup"><span data-stu-id="45269-104">While column vector notation is ubiquitous in linear algebra, it is often cumbersome in quantum computing especially when dealing with multiple qubits.</span></span>  <span data-ttu-id="45269-105">Například pokud definujeme $ \psi jako $ vektor, není explicitně jasné, zda je $ \psi $ řádek nebo vektor sloupce.</span><span class="sxs-lookup"><span data-stu-id="45269-105">For example, when we define $\psi$ to be a vector it is not explicitly clear whether $\psi$ is a row or a column vector.</span></span>  <span data-ttu-id="45269-106">Proto pokud jsou $ \phi $ a $ \psi $ vektory, je stejně nejasné, pokud je $ \phi \psi $ dokonce definovaný, protože tvary $ \phi $ a $ \psi $ mohou být v kontextu nejasné.</span><span class="sxs-lookup"><span data-stu-id="45269-106">Thus if $\phi$ and $\psi$ are vectors then it is equally unclear if $\phi \psi$ is even defined because the shapes of $\phi$ and $\psi$ may be unclear in the context.</span></span>  <span data-ttu-id="45269-107">Nad rámec nejednoznačnosti na tvarech vektorů a vyjadřující ještě jednoduché vektory pomocí lineárního algebraických Notation, který jste dříve zavedli, může být velmi obtížné.</span><span class="sxs-lookup"><span data-stu-id="45269-107">Beyond the ambiguity about the shapes of vectors, expressing even simple vectors using the linear algebraic notation introduced earlier can be very cumbersome.</span></span> <span data-ttu-id="45269-108">Pokud si například přejete popsat $n $ qubit, kde každé qubit převezme hodnotu $0, tak $ by byl tento stav formálně vyjadřovat jako</span><span class="sxs-lookup"><span data-stu-id="45269-108">For example, if we wish to describe an $n$-qubit state where each qubit takes the value $0$ then we would formally express the state as</span></span> 

<span data-ttu-id="45269-109">$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cdots \otimes \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="45269-109">$$\begin{bmatrix}1 \\\\  0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\  0 \end{bmatrix}.</span></span> $$  

<span data-ttu-id="45269-110">Kurz vyhodnocování tohoto tensor produktu je nepraktický, protože vektor leží v exponenciálním velkém prostoru, takže tento zápis je ve skutečnosti nejlepším popisem stavu, který může být dán pomocí předchozího zápisu.</span><span class="sxs-lookup"><span data-stu-id="45269-110">Of course evaluating this tensor product is impractical because the vector lies in an exponentially large space and so this notation is in fact the best description of the state that can be given using the previous notation.</span></span>  

<span data-ttu-id="45269-111">[*Dirac Notation*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) řeší tyto problémy tím, že prezentuje nový jazyk, který bude vyhovovat přesným potřebám mechanismu plnění.</span><span class="sxs-lookup"><span data-stu-id="45269-111">[*Dirac notation*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) solves these issues by presenting a new language to fit the precise needs of quantum mechanics.</span></span>  <span data-ttu-id="45269-112">Z tohoto důvodu doporučujeme, aby čtenář nezobrazil příklady v této části jako tuhý předpis o tom, jak tyto stavy popsat, ale místo toho je povzbuzovat, aby si ho mohli zobrazit jako návrhy, které se dají použít k stručné vyjádření nápadů.</span><span class="sxs-lookup"><span data-stu-id="45269-112">For this reason, we recommend the reader not view the examples in this section as a rigid prescription of how to describe quantum states, but rather encourage the reader to view these as suggestions that can be used to concisely express quantum ideas.</span></span>

<span data-ttu-id="45269-113">Existují dva typy vektorů v Dirac Notation: *Bra* Vector a *KET* Vector, takže při jejich sečtení tvoří *brzdový* nebo vnitřní produkt.</span><span class="sxs-lookup"><span data-stu-id="45269-113">There are two types of vectors in Dirac notation: the *bra* vector and the *ket* vector, so named because when put together they form a *braket* or inner product.</span></span>  <span data-ttu-id="45269-114">Pokud $ \psi $ je vektorem sloupce, můžeme ho zapsat do Dirac Notation jako $ \ket { \psi } $, kde $ \ket { \cdot } $ označuje, že se jedná o vektor sloupce jednotek, tj. *KET* Vector.</span><span class="sxs-lookup"><span data-stu-id="45269-114">If $\psi$ is a column vector then we can write it in Dirac notation as $\ket{\psi}$, where the $\ket{\cdot}$ denotes that it is a unit column vector, i.e., a *ket* vector.</span></span>  <span data-ttu-id="45269-115">Podobně je řádek Vector $ \psi ^ \dagger $ vyjádřen jako $ \bra { \psi } $.</span><span class="sxs-lookup"><span data-stu-id="45269-115">Similarly, the row vector $\psi^\dagger$ is expressed as $\bra{\psi}$.</span></span> <span data-ttu-id="45269-116">Jinými slovy, $ \psi ^ \dagger $ se získá tím, že se k prvkům transponovat z $ \psi aplikují komplexní conjugation $ .</span><span class="sxs-lookup"><span data-stu-id="45269-116">In other words, $\psi^\dagger$ is obtained by applying entry-wise complex conjugation to the elements of the transpose of $\psi$.</span></span> <span data-ttu-id="45269-117">Zápis Bra-KET přímo naznačuje, že $ \braket { \psi | \psi } $ je vnitřní produkt vektor $ \psi $ se sebou samým, což je definice $1 $ .</span><span class="sxs-lookup"><span data-stu-id="45269-117">The bra-ket notation directly implies that $\braket{\psi|\psi}$ is the inner product of vector $\psi$ with itself, which is by definition $1$.</span></span>  

<span data-ttu-id="45269-118">Obecně platí, že pokud jsou $ \psi $ a $ \phi, $ jejich vnitřní součin je $ \braket { \phi | \psi } $, což znamená, že pravděpodobnost měření stavu $ \ket \psi { } $ na $ \ket \phi $ { } je $ | \braket { \phi | \psi } | ^ 2 $ .</span><span class="sxs-lookup"><span data-stu-id="45269-118">More generally, if $\psi$ and $\phi$ are quantum state vectors their inner product is $\braket{\phi|\psi}$ which implies that the probability of measuring the state $\ket{\psi}$ to be $\ket{\phi}$ is $|\braket{\phi|\psi}|^2$.</span></span>  

<span data-ttu-id="45269-119">Následující konvence se používá k popsání stavových procesorů, které zakódují hodnoty nula a One (qubit výpočetních základních stavů):</span><span class="sxs-lookup"><span data-stu-id="45269-119">The following convention is used to describe the quantum states that encode the values of zero and one (the single-qubit computational basis states):</span></span>

<span data-ttu-id="45269-120">$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } , \qquad \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } = \ket{1 } .</span><span class="sxs-lookup"><span data-stu-id="45269-120">$$ \begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \ket{0},\qquad \begin{bmatrix} 0 \\\\  1 \end{bmatrix} = \ket{1}.</span></span>
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a><span data-ttu-id="45269-121">Příklad: reprezentace operace Hadamard se zápisem Dirac</span><span class="sxs-lookup"><span data-stu-id="45269-121">Example: representing the Hadamard operation with Dirac notation</span></span>

<span data-ttu-id="45269-122">Následující notace se často používá k popisu stavů, které vznikají v důsledku použití brány Hadamard na $ \ket{0 } $ a $ \ket{1 } $ (které odpovídají vektorům jednotek v $ přísměrech $ + x a $-x $ v koule Bloch):</span><span class="sxs-lookup"><span data-stu-id="45269-122">The following notation is often used to describe the states that result from applying the Hadamard gate to $\ket{0}$ and $\ket{1}$ (which correspond to the unit vectors in the $+x$ and $-x$ directions on the Bloch sphere):</span></span>

<span data-ttu-id="45269-123">$ $ \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ 1 \end{ bmatrix } = H \ket {0 } = \ket { +}, \qquad \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ -1 \end{ bmatrix } = H \ket {1 } = \ket { -}.</span><span class="sxs-lookup"><span data-stu-id="45269-123">$$ \frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=H\ket{0} = \ket{+},\qquad \frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  -1 \end{bmatrix} =H\ket{1} = \ket{-} .</span></span>
$$

<span data-ttu-id="45269-124">Tyto stavy je také možné rozšířit pomocí Dirac Notation jako součty pro $ \ket{0 } $ a $ \ket{1 } $:</span><span class="sxs-lookup"><span data-stu-id="45269-124">These states can also be expanded using Dirac notation as sums of $\ket{0}$ and $\ket{1}$:</span></span>

<span data-ttu-id="45269-125">$ $ \ket { +} = \frac{1 } {\sqrt{2 } } (\ket{0 } + \ket{1 } ), \qquad \ket { -} = \frac{1 } {\sqrt{2 } } (\ket{0 } -\ket{1 } ).</span><span class="sxs-lookup"><span data-stu-id="45269-125">$$ \ket{+} = \frac{1}{\sqrt{2}}(\ket{0} + \ket{1}),\qquad \ket{-} = \frac{1}{\sqrt{2}}(\ket{0} - \ket{1}).</span></span>
$$

### <a name="computational-basis-vectors"></a><span data-ttu-id="45269-126">Vektory výpočetního základu</span><span class="sxs-lookup"><span data-stu-id="45269-126">Computational basis vectors</span></span>
<span data-ttu-id="45269-127">To ukazuje, proč se tyto stavy často označují jako *výpočetní základ*: každý stav bez teček může být vždy vyjádřen jako součet výpočetních vektorů a tyto součty se snadno vyjadřují pomocí Dirac Notation.</span><span class="sxs-lookup"><span data-stu-id="45269-127">This demonstrates why these states are often called a *computational basis*: every quantum state can always be expressed as sums of computational basis vectors and such sums are easily expressed using Dirac notation.</span></span>  <span data-ttu-id="45269-128">Tato konverzace je také pravdivá v tom, že stavy $ \ket { +} $ a $ \ket { -} $ také tvoří základ pro stavové stavy.</span><span class="sxs-lookup"><span data-stu-id="45269-128">The converse is also true in that the states $\ket{+}$ and $\ket{-}$ also form a basis for quantum states.</span></span>  <span data-ttu-id="45269-129">Můžete to vidět z faktu, že</span><span class="sxs-lookup"><span data-stu-id="45269-129">You can see this from the fact that</span></span>

<span data-ttu-id="45269-130">$ $ \ket{0 } = \frac{1 } {\sqrt{2 } } (\ket { +} + \ket { -}), \qquad \ket{1 } = \frac{1 } {\sqrt{2 } } (\ket { +}-\ket { -}).</span><span class="sxs-lookup"><span data-stu-id="45269-130">$$ \ket{0} = \frac{1}{\sqrt{2}}(\ket{+} + \ket{-}),\qquad \ket{1} = \frac{1}{\sqrt{2}}(\ket{+} - \ket{-}).</span></span>
$$

<span data-ttu-id="45269-131">Jako příklad zápisu Diracu Zvažte možnost brzdit $ \braket{0 | 1 } $, což je vnitřní produkt mezi $0 $ a $1 $ .</span><span class="sxs-lookup"><span data-stu-id="45269-131">As an example of Dirac notation, consider the braket $\braket{0 | 1}$, which is the inner product between $0$ and $1$.</span></span>  <span data-ttu-id="45269-132">Dá se zapsat jako</span><span class="sxs-lookup"><span data-stu-id="45269-132">It can be written as</span></span> 

<span data-ttu-id="45269-133">$ $ \braket{0 | 1 } = \begin{ bmatrix } 1 & 0 \end{ bmatrix } \begin{ bmatrix } 0 \\\\ 1 \end { bmatrix } = 0. $ $</span><span class="sxs-lookup"><span data-stu-id="45269-133">$$\braket{0 | 1}=\begin{bmatrix} 1 & 0 \end{bmatrix}\begin{bmatrix}0\\\\ 1\end{bmatrix}=0.$$</span></span>

<span data-ttu-id="45269-134">Říká se tomu, že $ \ket{0 } $ a $ \ket{1 } $ jsou kolmé vektory, což znamená $ \braket{0 | 1 } = \braket{1 | 0 } = 0 $ .</span><span class="sxs-lookup"><span data-stu-id="45269-134">This says that $\ket{0}$ and $\ket{1}$ are orthogonal vectors, meaning that $\braket{0 | 1} = \braket{1 | 0} =0$.</span></span>  <span data-ttu-id="45269-135">Také podle definice $ \braket{0 | 0 } = \braket{1 | 1 } = 1 $ , což znamená, že dva vektory výpočetního základu mohou být také volány *orthonormal*.</span><span class="sxs-lookup"><span data-stu-id="45269-135">Also by definition $\braket{0 | 0} = \braket{1 | 1}=1$, which means that the two computational basis vectors can also be called *orthonormal*.</span></span>
<span data-ttu-id="45269-136">Tyto vlastnosti orthonormal budou užitečné v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="45269-136">These orthonormal properties will be useful in the following example.</span></span> <span data-ttu-id="45269-137">Pokud máme stav $ \ket { \psi } = {\frac{3 } {5 } } \ket{1 } + {\frac{4 } {5 } } \ket{0 } $ then, protože $ \braket{1 | 0 } = 0 $ pravděpodobnost měření $1 $ je</span><span class="sxs-lookup"><span data-stu-id="45269-137">If we have a state $\ket{\psi} = {\frac{3}{5}} \ket{1} + {\frac{4}{5}} \ket{0}$ then because $\braket{1 | 0} =0$ the probability of measuring $1$  is</span></span>  

<span data-ttu-id="45269-138">$ $ \big | \braket{1 | \psi } \big | ^ 2 = \left | \frac{3 } {5 } \braket{1 | 1 } + \frac{4 } {5 } \braket{1 | 0 } \right | ^ 2 = \frac{9 } {25 } . $ $</span><span class="sxs-lookup"><span data-stu-id="45269-138">$$\big|\braket{1 | \psi}\big|^2= \left|\frac{3}{5}\braket{1 | 1} +\frac{4}{5}\braket{1 | 0}\right|^2=\frac{9}{25}.$$</span></span> 

### <a name="tensor-product-notation"></a><span data-ttu-id="45269-139">Zápis produktu tensor</span><span class="sxs-lookup"><span data-stu-id="45269-139">Tensor product notation</span></span>
<span data-ttu-id="45269-140">Zápis Dirac zahrnuje také implicitní strukturu produktů tensor v rámci něj.</span><span class="sxs-lookup"><span data-stu-id="45269-140">Dirac notation also includes an implicit tensor product structure within it.</span></span>  <span data-ttu-id="45269-141">To je důležité z toho důvodu, že v případě, že se jedná o výpočetní výkon, je vektor stavu, který popisuje dva nekorelační Registry, tensor produkty dvou vektorů stavu.</span><span class="sxs-lookup"><span data-stu-id="45269-141">This is important because in quantum computing, the state vector described by two uncorrelated quantum registers is the tensor products of the two state vectors.</span></span>  <span data-ttu-id="45269-142">Stručně popisující strukturu produktu tensor nebo její nedostatečného je důležité, pokud chcete vysvětlit výpočet.</span><span class="sxs-lookup"><span data-stu-id="45269-142">Concisely describing the tensor product structure, or lack thereof, is vital if you want to explain a quantum computation.</span></span>  <span data-ttu-id="45269-143">Struktura produktu tensor předpokládá, že můžeme napsat $ \psi \otimes \phi $ pro jakékoli dvě "vektory stavu" \phi $ a $ \psi $ jako $ \ket { \psi } \ket { \phi } $, někdy explicitně zapsané jako $ \ket { \psi } \otimes \ket { \phi } $, ale konvence psaní $ \otimes $ v mezi vektory není zbytečné.</span><span class="sxs-lookup"><span data-stu-id="45269-143">The tensor product structure implies that we can write $\psi \otimes \phi$ for any two quantum state vectors $\phi$ and $\psi$ as $\ket{\psi} \ket{\phi}$, sometimes explicitly written as $\ket{\psi} \otimes \ket{\phi}$, however by convention writing $\otimes$ in between the vectors is unnecessary.</span></span>  <span data-ttu-id="45269-144">Například stav se dvěma qubits inicializovanými do nulového stavu je dán</span><span class="sxs-lookup"><span data-stu-id="45269-144">For example, the state with two qubits initialized to the zero state is given by</span></span>

<span data-ttu-id="45269-145">$ $ \begin{ bmatrix } 1 \\ \\ 0 0 \\ \\ \\ \\ 0 \end{ bmatrix } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } \otimes \ket{0 } = \ket{0 } \ket{0 } .</span><span class="sxs-lookup"><span data-stu-id="45269-145">$$ \begin{bmatrix} 1 \\\\  0 \\\\  0 \\\\  0 \end{bmatrix}= \begin{bmatrix} 1 \\\\  0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \ket{0} \otimes \ket{0}= \ket{0} \ket{0}.</span></span>
$$

<span data-ttu-id="45269-146">Podobně stav $ \ket{p } $ pro celočíselný $p $ představuje stav bez hodnoty, který se zakóduje v binární reprezentaci na celé číslo $p $ .</span><span class="sxs-lookup"><span data-stu-id="45269-146">Similarly,  the state $\ket{p}$ for integer $p$ represents a quantum state that encodes in binary representation the integer $p$.</span></span>  <span data-ttu-id="45269-147">Například pokud chceme vyjádřit číslo $5 $ pomocí binárního kódování bez znaménka, můžeme ho stejně vyjádřit jako</span><span class="sxs-lookup"><span data-stu-id="45269-147">For example, if we wish to express the number $5$ using an unsigned binary encoding we could equally express it as</span></span>

<span data-ttu-id="45269-148">$ $ \ket{1 } \ket{0 } \ket{1 } = \ket{101 } = \ket{5 } .</span><span class="sxs-lookup"><span data-stu-id="45269-148">$$ \ket{1}\ket{0}\ket{1} = \ket{101} = \ket{5}.</span></span>
$$

<span data-ttu-id="45269-149">V tomto zápisu $ \ket{0 } $ nemusí odkazovat na stav s jedním qubit, ale místo *registrace qubit* uložit binární kódování $0 $ .</span><span class="sxs-lookup"><span data-stu-id="45269-149">Within this notation $\ket{0}$ need not refer to a single-qubit state but rather a *qubit register* storing a binary encoding of $0$.</span></span>  <span data-ttu-id="45269-150">Rozdíly mezi těmito dvěma zápisy jsou obvykle jasně jasné z kontextu.</span><span class="sxs-lookup"><span data-stu-id="45269-150">The differences between these two notations is usually clear from the context.</span></span>  <span data-ttu-id="45269-151">Tato konvence je užitečná pro zjednodušení prvního příkladu, který lze zapsat některým z následujících způsobů:</span><span class="sxs-lookup"><span data-stu-id="45269-151">This convention is useful for simplifying the first example which can be written in any of the following ways:</span></span>

<span data-ttu-id="45269-152">$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cdots \otimes \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } \otimes \cdots \otimes \ket{0 } = | 0 \cdots 0 \rangle = \ket{0 } ^ {\otimes n } = \ket{0 } .</span><span class="sxs-lookup"><span data-stu-id="45269-152">$$ \begin{bmatrix}1 \\\\  0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\  0 \end{bmatrix} = \ket{0} \otimes \cdots \otimes \ket{0}= |0\cdots 0\rangle = \ket{0}^{\otimes n} = \ket{0}.</span></span>
$$

### <a name="example-describing-superposition-with-dirac-notation"></a><span data-ttu-id="45269-153">Příklad: popisující pozici Dirac Notation</span><span class="sxs-lookup"><span data-stu-id="45269-153">Example: Describing superposition with Dirac notation</span></span>
<span data-ttu-id="45269-154">Dalším příkladem, jak můžete použít Dirac Notation k popsání státu, zvažte následující ekvivalenty při psaní stavových stavů, které jsou stejné jako u každého možného bitového řetězce délky $n$</span><span class="sxs-lookup"><span data-stu-id="45269-154">As another example of how you can use Dirac notation to describe a quantum state, consider the following equivalent ways of writing a quantum state that is an equal superposition over every possible bit string of length $n$</span></span>

<span data-ttu-id="45269-155">$ $ H ^ {\otimes n } \ket{0 } = \frac{1 } {2 ^ {n/2 } } \ sum_ {j = 0 } ^ {2 ^ n-1 } \ket{j } = \ket { +} ^ {\otimes n } .</span><span class="sxs-lookup"><span data-stu-id="45269-155">$$ H^{\otimes n} \ket{0} = \frac{1}{2^{n/2}} \sum_{j=0}^{2^n-1} \ket{j} = \ket{+}^{\otimes n}.</span></span>
$$

<span data-ttu-id="45269-156">V této části se můžete zajímat, proč součet z $0 $ do $2 ^ {n } -1 $ pro $n $ bitů.</span><span class="sxs-lookup"><span data-stu-id="45269-156">Here you may wonder why the sum goes from $0$ to $2^{n}-1$ for $n$ bits.</span></span>  <span data-ttu-id="45269-157">Nejdřív si všimněte, že je k dispozici $2 ^ {n } $ různých konfigurací, které $n $ BITS může trvat.</span><span class="sxs-lookup"><span data-stu-id="45269-157">First note that there are $2^{n}$ different configurations that $n$ bits can take.</span></span>  <span data-ttu-id="45269-158">Můžete se podívat, že jeden bit může přijmout $2 hodnot, $ ale dvě bity mohou přijmout $4 $ hodnoty a tak dále.</span><span class="sxs-lookup"><span data-stu-id="45269-158">You can see this by noting that one bit can take $2$ values but two bits can take $4$ values and so forth.</span></span> <span data-ttu-id="45269-159">Obecně to znamená, že existuje $2 ^ n $ různých možných bitových řetězců, ale největší hodnota je kódována v jednom z nich $1 \cdots 1 = 2 ^ n-1 $ , a proto je horním limitem pro součet.</span><span class="sxs-lookup"><span data-stu-id="45269-159">In general, this means that there are $2^n$ different possible bit strings but the largest value encoded in any of them $1\cdots 1=2^n-1$ and hence it is the upper limit for the sum.</span></span>
<span data-ttu-id="45269-160">Jako poznámku na straně, v tomto příkladu jsme nepoužili $ \ket { +} ^ {\otimes n } = \ket { +} $ v analogii na $ \ket{0 } ^ {\otimes n } = \ket{0 } $, protože tato konvence zápisu je obvykle vyhrazená pro výpočetní stav se všemi qubity inicializovanými na nulu.</span><span class="sxs-lookup"><span data-stu-id="45269-160">As a side note, in this example we did not use $\ket{+}^{\otimes n}=\ket{+}$ in analogy to $\ket{0}^{\otimes n} = \ket{0}$ because this notational convention is usually reserved for the computational basis state with every qubit initialized to zero.</span></span>  <span data-ttu-id="45269-161">I když by taková konvence rozumné v tomto případě, nejedná se o výpočetní prostředí.</span><span class="sxs-lookup"><span data-stu-id="45269-161">While such a convention would be sensible in this case, it is not employed in the quantum computing literature.</span></span>

### <a name="expressing-linearity-with-dirac-notation"></a><span data-ttu-id="45269-162">Vyjádření linearity pomocí notace Dirac</span><span class="sxs-lookup"><span data-stu-id="45269-162">Expressing linearity with Dirac notation</span></span>
<span data-ttu-id="45269-163">Další dobrým prvkem Dirac Notation je skutečnost, že je lineární.</span><span class="sxs-lookup"><span data-stu-id="45269-163">Another nice feature of Dirac notation is the fact that it is linear.</span></span>  <span data-ttu-id="45269-164">Pokud chceme napsat pro všechny čtyři stavy stavu,</span><span class="sxs-lookup"><span data-stu-id="45269-164">If we wish to write for any four quantum state vectors,</span></span> 

<span data-ttu-id="45269-165">$ $ (\Alpha \ket { \psi } + \beta \ket { \phi } ) \otimes (\gamma \ket { \chi } + \delta \ket { \omega } ) = \Alpha \gamma \ket { \psi } \ket { \chi } + \Alpha \delta \ket { \psi } \ket { \omega } + \beta \gamma \ket { \phi } \ket { \chi } + \beta \delta \ket { \phi } \ket { \omega } . $ $</span><span class="sxs-lookup"><span data-stu-id="45269-165">$$(\alpha \ket{\psi} +\beta\ket{\phi})\otimes (\gamma \ket{\chi} + \delta \ket{\omega})= \alpha\gamma \ket{\psi}\ket{\chi} + \alpha\delta \ket{\psi}\ket{\omega}+\beta\gamma\ket{\phi}\ket{\chi}+\beta\delta\ket{\phi}\ket{\omega}.$$</span></span>

<span data-ttu-id="45269-166">To znamená, že je možné distribuovat zápis produktu tensor v zápisu Dirac, takže přebírání tensor produktů mezi vektory stavu končí hledáním stejně jako v případě obyčejného násobení.</span><span class="sxs-lookup"><span data-stu-id="45269-166">That is to say, you can distribute the tensor product notation in Dirac notation so that taking tensor products between state vectors ends up looking just like ordinary multiplication.</span></span>

<span data-ttu-id="45269-167">Vektory Bra sledují podobnou konvenci pro KET vektory.</span><span class="sxs-lookup"><span data-stu-id="45269-167">Bra vectors follow a similar convention to ket vectors.</span></span>  <span data-ttu-id="45269-168">Například Vector $ \bra { \psi } \bra { \phi } $ je ekvivalentem State Vector $ \psi ^ \dagger \otimes \phi ^ \dagger = (\psi \otimes \phi) ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="45269-168">For example, the vector $\bra{\psi}\bra{\phi}$ is equivalent to the state vector $\psi^\dagger \otimes \phi^\dagger=(\psi\otimes \phi)^\dagger$.</span></span> <span data-ttu-id="45269-169">Pokud je KET Vector $ \ket { \psi } $ $ \Alpha \ket{0 } + \beta \ket{1 } $, pak je verze vektoru Bra \bra $ \psi { \ket } = \psi { \dagger } ^ \bra{0 = (\Alpha } \bra{1 ^ \* + \beta } ^ \*) $.</span><span class="sxs-lookup"><span data-stu-id="45269-169">If the ket vector $\ket{\psi}$ is $\alpha \ket{0} + \beta \ket{1}$ then the bra vector version of the vector is $\bra{\psi}=\ket{\psi}^\dagger = (\bra{0}\alpha^\* +\bra{1}\beta^\*)$.</span></span>

<span data-ttu-id="45269-170">Představte si například, že chceme vypočítat pravděpodobnost měření stavu $ \ket { \psi } = \frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } $ pomocí programu pro měření stavů na hodnotu $ \ket { +} $ nebo $ \ket { -} $.</span><span class="sxs-lookup"><span data-stu-id="45269-170">As an example, imagine that we wish to calculate the probability of measuring the state $\ket{\psi} = \frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}$ using a quantum program for measuring states to be either $\ket{+}$ or $\ket{-}$.</span></span> <span data-ttu-id="45269-171">Pak pravděpodobnost, že by zařízení mělo výstup do stavu $ \ket { -} $</span><span class="sxs-lookup"><span data-stu-id="45269-171">Then the probability that the device would output that the state is $\ket{-}$ is</span></span> 

<span data-ttu-id="45269-172">$ $ | \braket { -| \psi } | ^ 2 = \left | \frac{1 } {\sqrt{2 } } (\bra{0 } -\bra{1 } ) (\frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } ) \right | ^ 2 = \left | -\frac{3 } {5 \sqrt {2 } } + \frac{4 } {5 \sqrt {2 } } \right | ^ 2 = \frac{1 } {50 } . $ $</span><span class="sxs-lookup"><span data-stu-id="45269-172">$$|\braket{- | \psi}|^2= \left|\frac{1}{\sqrt{2}}(\bra{0} - \bra{1})(\frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}) \right|^2=\left|-\frac{3}{5\sqrt{2}} + \frac{4}{5\sqrt{2}}\right|^2=\frac{1}{50}.$$</span></span>

<span data-ttu-id="45269-173">Skutečnost, že se záporné znaménko objeví při výpočtu pravděpodobnosti, je manifestem rušivého rušení, což je jeden z mechanismů, kterými výpočetní výkon získá výhody oproti klasickému výpočetnímu prostředí.</span><span class="sxs-lookup"><span data-stu-id="45269-173">The fact that the negative sign appears in the calculation of the probability is a manifestation of quantum interference, which is one of the mechanisms by which quantum computing gains advantages over classical computing.</span></span>

## <a name="ketbra-or-outer-product"></a><span data-ttu-id="45269-174">ketbra nebo vnější produkt</span><span class="sxs-lookup"><span data-stu-id="45269-174">ketbra or outer product</span></span>
<span data-ttu-id="45269-175">Konečná položka, která je předmětem diskuze v Dirac Notation, je *ketbra* nebo vnější produkt.</span><span class="sxs-lookup"><span data-stu-id="45269-175">The final item worth discussing in Dirac notation is the *ketbra* or outer product.</span></span>  <span data-ttu-id="45269-176">Vnější produkt je reprezentován v Dirac zápisy jako $ \ket { \psi } \bra { \phi } $ a někdy se označuje jako ketbras, protože Bras a kets se vyskytují v opačném pořadí jako brakets.</span><span class="sxs-lookup"><span data-stu-id="45269-176">The outer product is represented within Dirac notations as $\ket{\psi} \bra{\phi}$, and sometimes called ketbras because the bras and kets occur in the opposite order as brakets.</span></span>  <span data-ttu-id="45269-177">Vnější produkt je definován pomocí násobení matic jako $ \ket { \psi } \bra { \phi } = \psi \phi ^ \dagger pro násobky $ stavových vektorů $ \psi $ a $ \phi $ .</span><span class="sxs-lookup"><span data-stu-id="45269-177">The outer product is defined via matrix multiplication as $\ket{\psi} \bra{\phi} = \psi \phi^\dagger$ for quantum state vectors $\psi$ and $\phi$.</span></span>  <span data-ttu-id="45269-178">Nejjednodušším a pravděpodobně Nejběžnějším příkladem tohoto zápisu je</span><span class="sxs-lookup"><span data-stu-id="45269-178">The simplest, and arguably most common example of this notation, is</span></span>

<span data-ttu-id="45269-179">$ $ \ket{0 } \bra{0 } = \begin{ bmatrix } 1 \\\\ 0 \end{ bmatrix } \begin{ bmatrix } 1&0 \end{ bmatrix } = \begin{ bmatrix } 1 &0 \\\\ 0 &0 \end { bmatrix } \qquad \ket{1 } \bra{1 } = \begin{ bmatrix } 0 \\\\ 1 \end{ bmatrix } \begin{ bmatrix } 0&1 \end{ bmatrix } = \begin{ bmatrix } 0 &0 \\\\ 0 &1 \end { bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="45269-179">$$ \ket{0} \bra{0} = \begin{bmatrix}1\\\\ 0 \end{bmatrix}\begin{bmatrix}1&0 \end{bmatrix}= \begin{bmatrix}1 &0\\\\ 0 &0\end{bmatrix} \qquad \ket{1} \bra{1} = \begin{bmatrix}0\\\\ 1 \end{bmatrix}\begin{bmatrix}0&1 \end{bmatrix}= \begin{bmatrix}0 &0\\\\ 0 &1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="45269-180">Ketbras se často nazývají projektory, protože projektují stav na pevnou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="45269-180">Ketbras are often called projectors because they project a quantum state onto a fixed value.</span></span>  <span data-ttu-id="45269-181">Vzhledem k tomu, že tyto operace nejsou jednotkové (a dokonce i zachovat normu vektoru), mělo by být neuvedeno, že počítač s více operačními počítači nemůže deterministickém způsobem použít projektor.</span><span class="sxs-lookup"><span data-stu-id="45269-181">Since these operations are not unitary (and do not even preserve the norm of a vector), it should come as no surprise that a quantum computer cannot deterministically apply a projector.</span></span>  <span data-ttu-id="45269-182">Projektory se dotýkají působivé úlohy popisující akci, kterou měření má v nestavovém stavu.</span><span class="sxs-lookup"><span data-stu-id="45269-182">However projectors do a beautiful job of describing the action that measurement has on a quantum state.</span></span>  <span data-ttu-id="45269-183">Pokud například měříme stav $ \ket { \psi } $, který bude $0 $ , pak výsledná transformace, která se v důsledku měření funguje jako stav, je</span><span class="sxs-lookup"><span data-stu-id="45269-183">For example, if we measure a state $\ket{\psi}$ to be $0$ then the resulting transformation that the state experiences as a result of the measurement is</span></span>

  <span data-ttu-id="45269-184">$ $ \ket { \psi } \rightarrow \frac { (\ket{0 } \bra{0 } ) \ket { \psi } } {| \braket{0 | \psi } |} = \ket{0 } , $ $</span><span class="sxs-lookup"><span data-stu-id="45269-184">$$\ket{\psi} \rightarrow \frac{(\ket{0} \bra{0})\ket{\psi}}{|\braket{0 | \psi}|}= \ket{0},$$</span></span>

<span data-ttu-id="45269-185">očekává se, že pokud byste chtěli změřit stav a vyhledat ho jako $ \ket{0 } $.</span><span class="sxs-lookup"><span data-stu-id="45269-185">as one expects if you were to measure the state and find it to be $\ket{0}$.</span></span>  <span data-ttu-id="45269-186">Chcete-li provést iteraci, nelze tyto projektory použít ve stavu v počítači s více než jednou.</span><span class="sxs-lookup"><span data-stu-id="45269-186">To reiterate, such projectors cannot be applied on a state in a quantum computer deterministically.</span></span>  <span data-ttu-id="45269-187">Místo toho je lze použít náhodně s výsledným $ \ket{0 } $ zobrazeným s určitou pevnou pravděpodobností.</span><span class="sxs-lookup"><span data-stu-id="45269-187">Instead, they can at best be applied randomly with the result $\ket{0}$ appearing with some fixed probability.</span></span>  <span data-ttu-id="45269-188">Pravděpodobnost takového měření se může zapsat jako hodnota očekávaného projektoru ve stavu.</span><span class="sxs-lookup"><span data-stu-id="45269-188">The probability of such a measurement succeeding can be written as the expectation value of the quantum projector in the state</span></span>

<span data-ttu-id="45269-189">$ $ \bra { \psi } (\ket{0 } \bra{0 } ) \ket { \psi } = | \braket { \psi | 0 } | ^ 2, $ $</span><span class="sxs-lookup"><span data-stu-id="45269-189">$$ \bra{\psi} (\ket{0} \bra{0})\ket{\psi} = |\braket{\psi | 0}|^2, $$</span></span>

<span data-ttu-id="45269-190">To ukazuje, že projektory jednoduše poskytují nový způsob, jak vyjádřit proces měření.</span><span class="sxs-lookup"><span data-stu-id="45269-190">which illustrates that projectors simply give a new way of expressing the measurement process.</span></span>

<span data-ttu-id="45269-191">Pokud místo toho zvažte měření prvního qubit stavu qubit na hodnotu $1, $ můžeme také tento proces snadno popsat pomocí projektorů a notace Dirac:</span><span class="sxs-lookup"><span data-stu-id="45269-191">If instead we consider measuring the first qubit of a multi-qubit state to be $1$ then we can also describe this process conveniently using projectors and Dirac notation:</span></span>

<span data-ttu-id="45269-192">$ $ P (\Text{First qubit = 1 } ) = \bra { \psi } \left (\ket{1 } \bra{1 } \otimes \boldone ^ {\otimes n-1 } \right) \ket { \psi } .</span><span class="sxs-lookup"><span data-stu-id="45269-192">$$ P(\text{first qubit = 1})= \bra{\psi}\left(\ket{1}\bra{1}\otimes \boldone^{\otimes n-1}\right) \ket{\psi}.</span></span>
$$

<span data-ttu-id="45269-193">Tady se může v zápisu Dirac pohodlně napsat matice identity jako</span><span class="sxs-lookup"><span data-stu-id="45269-193">Here the identity matrix can be conveniently written in Dirac notation as</span></span>

<span data-ttu-id="45269-194">$ $ \boldone = \ket{0 } \bra{0 } + \ket{1 } \bra{1 } = \begin{ bmatrix } 1&0 \\\\ 0&1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="45269-194">$$ \boldone = \ket{0} \bra{0}+\ket{1} \bra{1}= \begin{bmatrix}1&0\\\\ 0&1 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="45269-195">V případě, že je možné qubits projektor rozšířit na dva, jako</span><span class="sxs-lookup"><span data-stu-id="45269-195">For the case where there are two-qubits the projector can be expanded as</span></span> 

<span data-ttu-id="45269-196">$ $ \ket{1 } \bra{1 } \otimes \id = \ket{1 } \bra{1 } \otimes (\ket{0 } \bra{0 } + \ket{1 } \bra{1 } ) = \ket{10 } \bra{10 } + \ket{11 } \bra{11 } .</span><span class="sxs-lookup"><span data-stu-id="45269-196">$$ \ket{1} \bra{1} \otimes \id = \ket{1}\bra{1} \otimes (\ket{0} \bra{0}+\ket{1} \bra{1})= \ket{10}\bra{10} + \ket{11}\bra{11}.</span></span>
$$

<span data-ttu-id="45269-197">Uvidíte, že je to v souladu s diskusí o pravděpodobnosti měření pro stavy multiqubit pomocí notace sloupcový-Vector:</span><span class="sxs-lookup"><span data-stu-id="45269-197">We can then see that this is consistent with the discussion about measurement likelihoods for multiqubit states using column-vector notation:</span></span>

<span data-ttu-id="45269-198">$ $ P (\Text{First qubit = 1 } ) = \psi ^ \dagger (e \_ {10} e \_ {10 } ^ \dagger + e \_ {11} e \_ {11 } ^ \dagger) \psi = | e \_ {10 } ^ \dagger \psi | ^ 2 + | e \_ {11 } ^ \dagger \psi | ^ 2, $ $</span><span class="sxs-lookup"><span data-stu-id="45269-198">$$ P(\text{first qubit = 1})= \psi^\dagger (e\_{10}e\_{10}^\dagger + e\_{11}e\_{11}^\dagger)\psi = |e\_{10}^\dagger \psi|^2 + |e\_{11}^\dagger \psi|^2, $$</span></span>

<span data-ttu-id="45269-199">který se shoduje s qubitou diskuzi o měření.</span><span class="sxs-lookup"><span data-stu-id="45269-199">which matches the multi-qubit measurement discussion.</span></span>  <span data-ttu-id="45269-200">Vygeneralizení tohoto výsledku pro qubit případ je však poněkud jednodušší, aby bylo možné vyjádřit pomocí notace Dirac, než je zápis ve sloupcovém vektoru, a je zcela ekvivalentní k předchozímu ošetření.</span><span class="sxs-lookup"><span data-stu-id="45269-200">The generalization of this result to the multi-qubit case, however, is slightly more straightforward to express using Dirac notation than column-vector notation, and is entirely equivalent to the previous treatment.</span></span>

## <a name="density-operators"></a><span data-ttu-id="45269-201">Operátory hustoty</span><span class="sxs-lookup"><span data-stu-id="45269-201">Density operators</span></span>

<span data-ttu-id="45269-202">Dalším užitečným operátorem k vyjádření použití notace Dirac je *operátor hustoty*, někdy také označovaný jako *operátor State*.</span><span class="sxs-lookup"><span data-stu-id="45269-202">Another useful operator to express using Dirac notation is a *density operator*, sometimes also known as a *state operator*.</span></span>
<span data-ttu-id="45269-203">Operátor hustoty pro vektorový stavový vektor má formu $ \rho = \ket { \psi } \bra { \psi } $.</span><span class="sxs-lookup"><span data-stu-id="45269-203">A density operator for a quantum state vector takes the form $\rho = \ket{\psi} \bra{\psi}$.</span></span>
<span data-ttu-id="45269-204">Tento koncept představující stav jako matici, spíše než vektor, je často pohodlný, protože poskytuje pohodlný způsob, jak vyjádřit výpočty pravděpodobnosti a také umožňuje, aby popsal statistickou nejistotu i nejistotu v rámci stejné formality.</span><span class="sxs-lookup"><span data-stu-id="45269-204">This concept of representing the state as a matrix, rather than a vector, is often convenient because it gives a convenient way of representing probability calculations, and also allows one to describe both statistical uncertainty as well as quantum uncertainty within the same formalism.</span></span>
<span data-ttu-id="45269-205">Obecné operátory státních stavů, nikoli vektory, se všudypřítomný v některých oblastech výpočetního prostředí, ale není nutné porozumět základům tohoto pole.</span><span class="sxs-lookup"><span data-stu-id="45269-205">General quantum state operators, rather than vectors, are ubiquitous in some areas of quantum computing but are not necessary to understand the basics of the field.</span></span>
<span data-ttu-id="45269-206">Pro zúčastněný čtenář doporučujeme přečíst si jednu z referenčních knih, které jsou k dispozici v tématu, [kde najdete další informace](xref:microsoft.quantum.more-information).</span><span class="sxs-lookup"><span data-stu-id="45269-206">For the interested reader, we recommend reading one of the reference books provided in [For more information](xref:microsoft.quantum.more-information).</span></span>

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a><span data-ttu-id="45269-207">Sekvence pro bránu Q # rovnající se státům</span><span class="sxs-lookup"><span data-stu-id="45269-207">Q# gate sequences equivalent to quantum states</span></span>
<span data-ttu-id="45269-208">Konečný bod vyvolal informace o zápisu na základě teček a programovací jazyk Q #: na začátku tohoto dokumentu jsme zjistili, že stav je základní objekt informací v výpočetním prostředí.</span><span class="sxs-lookup"><span data-stu-id="45269-208">A final point worth raising about quantum notation and the Q# programming language: at the onset of this document we mentioned that the quantum state is the fundamental object of information in quantum computing.</span></span>  <span data-ttu-id="45269-209">Pak může nastat jako neočekávaně v Q # neexistuje žádný pojem stát.</span><span class="sxs-lookup"><span data-stu-id="45269-209">It may then come as a surprise that in Q# there is no notion of a quantum state.</span></span>  <span data-ttu-id="45269-210">Místo toho jsou všechny stavy popsány pouze pomocí operací, které slouží k jejich přípravě.</span><span class="sxs-lookup"><span data-stu-id="45269-210">Instead, all states are described only by the operations used to prepare them.</span></span>  <span data-ttu-id="45269-211">Předchozí příklad představuje vynikající ilustraci.</span><span class="sxs-lookup"><span data-stu-id="45269-211">The previous example is an excellent illustration of this.</span></span>  <span data-ttu-id="45269-212">Místo toho, abychom v registru vyjádřili jednotnou polohu před každým bitem, můžeme výsledek vyjádřit jako $H ^ {\otimes n } \ket{0 } $.</span><span class="sxs-lookup"><span data-stu-id="45269-212">Rather than expressing a uniform superposition over every quantum bit string in a register, we can represent the result as $H^{\otimes n} \ket{0}$.</span></span>  <span data-ttu-id="45269-213">Tento exponenciálně kratší popis stavu má nejen výhodu, že se na něj dá klasický důvod, ale také stručně definuje operace, které je potřeba rozšířit prostřednictvím softwarového zásobníku, aby se tento algoritmus implementoval.</span><span class="sxs-lookup"><span data-stu-id="45269-213">This exponentially shorter description of the state not only has the advantage that we can classically reason about it, but it also concisely defines the operations needed to be propagated through the software stack to implement the algorithm.</span></span>  <span data-ttu-id="45269-214">Z tohoto důvodu je Q # navržený tak, aby vygeneroval sekvence brány místo nestavových stavů. na teoretické úrovni jsou však dva perspektivy ekvivalentní.</span><span class="sxs-lookup"><span data-stu-id="45269-214">For this reason, Q# is designed to emit gate sequences rather than quantum states; however, at a theoretical level the two perspectives are equivalent.</span></span>
