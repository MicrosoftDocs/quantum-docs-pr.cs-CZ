---
title: Modely u elektronických systémů
description: Přečtěte si, jak se v molekulových elektronických systémech simulují pomocí modelování.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantummodels
ms.openlocfilehash: 9f9fc37944dd76026c2641d9cdf126e71053a598
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904413"
---
# <a name="quantum-models-for-electronic-systems"></a>Modely u elektronických systémů

Aby bylo možné simulovat elektronické systémy, musíme nejdřív začít zadáním Hamiltonian, který lze najít pomocí kanonické procedury kvantizační popsané výše.
Konkrétně pro $N _e $ Electrons s momentem $p _i $ (ve třech dimenzích) a hromadnou $m _e $ a pozice vektorů $x _i $ spolu s Nuclei s poplatky za $Z e $ na pozicích _k $y $, Hamiltonian operátor čte \begin{Equation} \hat{H} = \sum\_{i = 1} ^ {N\_e} \frac{\hat{p}\_i ^ 2} {2 min\_e} + \frac{1}{2}\sum\_{i\ne j} \frac{e ^ 2} {| \hat{x}\_i-\hat{x}\_j |}-\sum\_{i , k} \frac{Z\_ke ^ 2} {| \hat{x}\_i-{y}\_k |} + \frac{1}{2} \ sum_ {k\ne k} \frac{Z\_kZ\_{k} e ^ 2} {| y\_k-y\_k |}. \label{EQ: Ham} \end{Equation} Operators $ \hat{p}\_i ^ 2 $ je možné zobrazit v reálném prostoru jako operátory Laplacian, tj. $ \hat{p}\_i ^ 2 =-\partial\_{x\_i} ^ 2-\partial\_{y\_i} ^ 2-\partial\_{z\_i} ^ 2 $.
Tady jsme udělali zjednodušení předpokladu, že Nuclei jsou v klidovém umístění pro molekuly.
Tento postup se označuje jako Přibližná aproximace v Oppenheimer a je v něm platná pro energetickou škálu pro úspory energie $ \hat{H} $, protože elektronická hmotnost je přibližně $1/1836 $, což je hmotnost Proton.
Tento Hamiltonian operátor lze snadno najít tak, že vypíšete energii pro systém $N\_e $ Electrons a použijete kanonický kvantizační [proces, který](xref:microsoft.quantum.chemistry.concepts.quantumdynamics)je popsaný v části s násobením.

Aby bylo možné vytvořit jednotnou maticovou matici pro $e ^ {-i\hat {H} t} $, musíme jako matici zastupovat operator $ \hat{H} $.
V takovém případě je nutné zvolit systém souřadnic nebo základ pro reprezentaci problému v.
Pokud má například $ \ psi_j $ sadu kolmých základních funkcí pro $N _e $ Electrons, můžeme definovat matici.

\begin{Equation} H\_{i, j} = \int\_{-\infty} ^ \infty\int\_{-\infty} ^ \infty \psi ^ {\*}\_i (x\_1) \hat{H} \psi\_j (x\_2) \dd ^ 3x\_1 \dd ^ 3x\_2. \ Label {EQ: discreteHam} \end{Equation}

V zásadě je operátor $ \hat{H} $ neohraničený a nefunguje na konečném rozměrovém prostoru, matice s prvky $H\_\{i, j\}$ výše.
To znamená, že vzniknou chybu vynásobením příliš malého základního nastavení. Výběr velkého základu ale může simulovat chemický dynamiku nepraktickou.
Z tohoto důvodu je pro řešení potíží s elektronickými strukturami nezbytný způsob, který může stručně představovat problém.

Existuje mnoho odpovídajících základů, které je možné použít, a volba dobrého základu, která je vhodná pro splnění tohoto problému, je velká část z výtvarné chemické třídy.
Možná nejjednodušší takové sady jsou Slater-Type-orbitals (ši), které jsou (kolmá) řešení k rovnici Schrödinger (tj. eigenfunctions of $ \hat{H} $) pro atomy podobné vodíku.
Další základní sady, jako je například rovina, vlny nebo orbitals v reálném čase, se dají použít a podrobnější informace najdete v tématu zajímá Reader na standardní text [' molekulová Elektronická struktura teorie '](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572) od Helgaker.

I když se stavy používané ve výše uvedeném modelu mohou zdát neomezeně, mechanismy na základě počtu chyb mají omezení stavů, které se dají najít v podstatě.
Konkrétně všechny platné elektronické stavové stavy musí být pro výměnu elektronických štítků odolné proti chybám.
To znamená, že $ \psi (x_1, x_2) $ byla funkce Wave pro smíšený stav 2 Electrons a pak musíme mít $ $ \psi (x_1, x_2) =-\psi (x_2, x_1).
$ $ Pauli princip vyloučení, který zakazuje, že dvě Electrons by mohly být ve stejném stavu, fascinatingly, což je přímým podílem tohoto zákona, jak se dá v případě, že jsme provedli záměnu dvou Electrons na stejné pozici $ \psi (x_1, x_1) \mapsto \psi ( x_1, x_1) \Ne-\psi (x_1, x_1) $, pokud není $ \psi (x_1, x_1) = 0 $.
Proto musí být počáteční stavy zvoleny k tomu, aby se řídily touto vlastností anti-symetrie a v současné době nikdy nemají dvě Electrons ve stejném stavu.
To je klíčové pro elektronickou strukturu, protože zakazuje více Electrons ve stejném stavu, a umožňuje počítačům s více podklady použít jeden bit pro uložení počtu Electrons v daném státě.

I když je možné pracovat s velkým množstvím dat na počítači, který diskretizace atributu tyto stavy, většina práce v poli má eschewed tento přístup, protože vyžaduje mnoho qubits pro uložení stavů a potřebuje složitý postup přípravy na přípravu Anti-symetrický počáteční stav.
Naštěstí je ale možné tyto problémy sidestepped zobrazením problému simulace z jiné perspektivy.
