---
title: Modely u elektronických systémů
description: Přečtěte si, jak se v molekulových elektronických systémech simulují pomocí modelování.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantummodels
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4ff3d11bfd4dae5489fc4b7efe4da4ccda00882f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833917"
---
# <a name="quantum-models-for-electronic-systems"></a>Modely u elektronických systémů

Aby bylo možné simulovat elektronické systémy, musíme nejdřív začít zadáním Hamiltonian, který lze najít pomocí kanonické procedury kvantizační popsané výše.
Konkrétně pro $N _e $ Electrons s momentem $p _i $ (ve třech dimenzích) a hromadnou $m _e $ a pozice vektorů $x _i $ spolu s Nuclei s poplatky za $Z e $ na pozicích _k $y $, Hamiltonian operátor čte \begin{Equation} \hat{H} = \sum \_ {i = 1} ^ {N \_ e} \frac{\hat{p} \_ i ^ 2} {2 min \_ e} + \frac {1} {2} \sum \_ {i\ne j} \frac{e ^ 2} {| \hat{x} \_ i-\hat{x} \_ j |}-\sum \_ {i, k} \frac{Z k \_ ^ 2} {| \hat{x} \_ i-{y} \_ k |} + \frac {1} {2} \ sum_ {k\ne k} \frac{Z \_ kZ \_ {k} e ^ 2} {| y \_ k-y \_ k |}. \label{EQ: Ham} \end{Equation} operátory moment. @ \hat{p} \_ i ^ 2 $ se dají zobrazit v reálném prostoru jako Laplacian operátory, tj. $ \hat{p} \_ i ^ 2 =-\partial \_ {x \_ i} ^ 2-\partial \_ {y \_ i} ^ 2-\partial \_ {z \_ i} ^ 2 $.
Tady jsme udělali zjednodušení předpokladu, že Nuclei jsou v klidovém umístění pro molekuly.
Tento postup se označuje jako Přibližná aproximace v Oppenheimer a je v něm platná pro energetickou škálu pro úspory energie $ \hat{H} $, protože elektronická hmotnost je přibližně $1/1836 $, což je hmotnost Proton.
Tento Hamiltonian operátor lze snadno najít tak, že vypíšete energii pro systém $N \_ e $ Electrons a použijete kanonický kvantizační proces [, který](xref:microsoft.quantum.chemistry.concepts.quantumdynamics)je popsán v části.

Aby bylo možné vytvořit jednotnou maticovou matici pro $e ^ {-i\hat {H} t} $, musíme jako matici zastupovat operator $ \hat{H} $.
V takovém případě je nutné zvolit systém souřadnic nebo základ pro reprezentaci problému v.
Pokud má například $ \ psi_j $ sadu kolmých základních funkcí pro $N _e $ Electrons, můžeme definovat matici.

\begin{Equation} H \_ {i, j} = \int \_ {-\infty} ^ \infty\int \_ {-\infty} ^ \infty \psi ^ { \* } \_ i (x \_ 1) \hat{H} \psi \_ j (x \_ 2) \dd ^ 3x \_ 1 \dd ^ 3x \_ 2. \ Label {EQ: discreteHam} \end{Equation}

V podstatě je operátor $ \hat{H} $ neohraničený a nefunguje na konečném multidimenzionálním prostoru, matice s prvky $H \_ \{ i, j \} $ výše.
To znamená, že vzniknou chybu vynásobením příliš malého základního nastavení. Výběr velkého základu ale může simulovat chemický dynamiku nepraktickou.
Z tohoto důvodu je pro řešení potíží s elektronickými strukturami nezbytný způsob, který může stručně představovat problém.

Existuje mnoho odpovídajících základů, které je možné použít, a volba dobrého základu, která je vhodná pro splnění tohoto problému, je velká část z výtvarné chemické třídy.
Možná nejjednodušší takové sady jsou Slater-Type-orbitals (ši), které jsou (kolmá) řešení k rovnici Schrödinger (tj. eigenfunctions of $ \hat{H} $) pro atomy podobné vodíku.
Další základní sady, jako je například rovina, vlny nebo orbitals v reálném čase, se dají použít a podrobnější informace najdete v tématu zajímá Reader na standardní text [' molekulová Elektronická struktura teorie '](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572) od Helgaker.

I když se stavy používané ve výše uvedeném modelu mohou zdát neomezeně, mechanismy na základě počtu chyb mají omezení stavů, které se dají najít v podstatě.
Konkrétně všechny platné elektronické stavové stavy musí být pro výměnu elektronických štítků odolné proti chybám.
To znamená, že $ \psi (x_1, x_2) $ byla funkce Wave pro smíšený stav 2 Electrons a pak musíme mít $ $ \psi (x_1, x_2) =-\psi (x_2, x_1).
$ $ Pauli – princip vyloučení, který zakazuje, že dvě Electrons by mohly být ve stejném stavu, fascinatingly, přímým způsobem tohoto zákona, jak může být z faktu, že pokud jsme provedli záměnu dvou Electrons na stejné pozici $ \psi (x_1, x_1) \mapsto \psi (x_1, x_1) \Ne-\psi (x_1, x_1) $, pokud není $ \psi (x_1 , x_1) = 0 $.
Proto musí být počáteční stavy zvoleny k tomu, aby se řídily touto vlastností anti-symetrie a v současné době nikdy nemají dvě Electrons ve stejném stavu.
To je klíčové pro elektronickou strukturu, protože zakazuje více Electrons ve stejném stavu, a umožňuje počítačům s více podklady použít jeden bit pro uložení počtu Electrons v daném státě.

I když je náročné na počítač, který může být v terénu simulovaný, diskretizace atributu tyto stavy, většina práce v poli má eschewed tento přístup, protože vyžaduje mnoho qubits pro uložení těchto stavů a pro přípravu mikrosymetrického počátečního stavu potřebuje složitý postup přípravy.
Naštěstí je ale možné tyto problémy sidestepped zobrazením problému simulace z jiné perspektivy.
