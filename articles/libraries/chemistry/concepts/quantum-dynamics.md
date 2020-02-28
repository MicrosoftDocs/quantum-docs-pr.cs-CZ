---
title: Dynamika doby
description: Přečtěte si o podobnostech a rozdílech mezi vydanými a klasickými dynamikami.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantumdynamics
ms.openlocfilehash: 9cb74ccd4b7806a90c0701300860d777fa8e5d75
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904481"
---
# <a name="quantum-dynamics"></a>Dynamika doby

Mechanismus plnění do značné míry je z velké části studia dynamiky provozu, který se snaží pochopit, jak počáteční stav za běhu $ \ket{\psi (0)} $ se v průběhu času liší (Další informace o zápisu Dirac najdete v [koncepčních](xref:microsoft.quantum.concepts.dirac) dokumentech s výpočetním prostředím).
Konkrétně za předpokladu, že je v tomto počátečním podmíněném stavu, je čas vývoje a specifikace dynamického systému, který je ve stavu "\ket{\psi (t)} $".
Než začnete s vysvětlem životnosti Dynamics, je vhodné provést krok zpět a zamyslete se na klasických dynamikách, protože poskytuje přehled o tom, jak se ve skutečnosti nejedná o nezávisle na klasických případech.

V klasickém dynamicsovém řešení ví, že se poloha částice v newtonech snaží rozvinout podle $F (x, t) = ma = m\frac {\ DD ^ 2} {\dd t ^ 2} {x} (t) $, kde $F (x, t) $ je silo, $m $ je to zrychlení a $a.
Poté, s ohledem na počáteční pozici $x (0) $, doba vývoje $t $ a popis sil, které působí na částice, můžeme najít $x (t) $ vyřešením rozdílové rovnice uvedené v rovnicích newtonů pro $x (t) $.
Určení síly tímto způsobem je trochu bolesti.
Proto jsme často vyjádřili síly z pohledu potenciální energie systému, který nám poskytuje $-\ partial_x V (x, t) = m \frac{\dd ^ 2} {\dd t ^ 2} {x} (t) $.
Proto pro částice je dynamika systému určena pouze potenciální energetickou funkcí, hmotností částic a časem vývoje.

Pro klasický dynamiku se často zavádí širší jazyk, který překračuje $F = mA $.
Jedna formulace, která je užitečná hlavně v přípravné mechanismy, je Hamiltonian mechanikou.
V Hamiltonian mechanice představuje celková energie systému a (generalizované) pozice a chvilka všechny informace potřebné k popisu pohybu libovolného klasického objektu.
Konkrétně $f (x, p, t) $ být některé funkce generalizované pozice $x $ a moment-$p $ systému a let $H (x, p, t) $ být funkcí Hamiltonian.
Například pokud budeme pořizovat $f (x, p, t) = x (t) $ a $H (x, p, t) = p ^ 2 (t)/2m-V (x, t) $, pak by se vám obnovilo i výše uvedený případ Newtonian Dynamics.
V obecném případě jsme \begin{align} \frac{d}{DT} f & = \ partial_t f-(\ partial_x H \ partial_p f + \ partial_p H \ partial_x f)\\\\ & \defeq \ partial_t f + \\{f, H\\}.
\end{align} tady $\\{f, H\\} $ se nazývá [Poissonova závorka](https://en.wikipedia.org/wiki/Poisson_bracket) a v klasickém dynamikě se zobrazí ubiquitously, protože centrální role, kterou hraje při definování dynamiky.

V aplikaci Dynamics se dá považovat za použití přesně stejného jazyka.
Hamiltonian nebo celková spotřeba energie zcela specifikuje dynamiku všech uzavřených systémů na konci.
Existují však některé zásadní rozdíly mezi dvěma teoriey.
V klasických automechanice $x $ a $p $ jsou jenom čísla, zatímco v něm neexistují.
Ve skutečnosti neexistují ani do dojíždění: $XP \Ne px $.

Správný matematický koncept, který popisuje tyto objekty, které nepatří do nedoručení, je operátor, který v případech, kdy $x $ a $p $, může převzít pouze diskrétní sadu hodnot, která se shoduje s konceptem matice.
Proto předpokládáme, že náš systém pro navýšení je konečný, takže je možné ho popsat pomocí [vektorů a matic](xref:microsoft.quantum.concepts.vectors).
Dále vyžadujeme, aby se tyto matrice Hermitian (to znamená, že sdružená transpozice matice je shodná s původní maticí).
To zaručuje, že eigenvalues matice jsou reálné; podmínka, kterou zavádíme, aby se zajistilo, že při měření množství, jako je třeba pozice, nezískáme imaginární číslo.

Stejně jako analogie pozice a potenciál v Hamiltonian musí být nahrazeni operátory, funkce musí být podobně nahrazena operátorem.
Například pro částice v volném prostoru máme tyto $H (x, p) = p ^ 2/2 min $, zatímco v poli doby pří\hat{H}i Hamiltonian operator $ \hat{H} $ je $ = \hat{p} ^ 2/2 min $, kde $ \hat{p} $ je operátor potenciál.
Z této perspektivy se v případě dynamiky z klasického navýšení na každý z nich vyžaduje nahrazení proměnných používaných v běžném Dynamics with Operators.
Jakmile jsme sestavili Hamiltonian operátor převedením obyčejného klasického Hamiltonianu na jazyk, můžeme vyjádřit dynamiku libovolného množství všech provozních podmínek (tj. "mechanického" operátoru) $ \hat{f} (t) $ Via \begin{ align} \frac{d}{DT} \hat{f} = \ partial_t \hat{f} + [\hat{f}, \hat{H}], \end{align} kde $ [f, H] = fH-HF $ se označuje jako commutator.
Tento výraz je přesně stejný jako klasický výraz uvedený výše s rozdílem, že Poissonova závorka $\\{f, H\\} $ se nahrazuje commutator mezi $f $ a $H $.
Tento proces přebírání klasického Hamiltonianu a jeho použití k vyhledání Hamiltoniany na více procesorů je známou v žargonuech jako kanonické kvantizační.

Jaké operátory $f $ jste nejvíc zajímáme?  Odpověď na tuto otázku závisí na problému, který chceme vyřešit.
Nejužitečnější množství, které je třeba najít, je operátor stavu pro stav, který je popsaný v předchozí Koncepční dokumentaci, lze použít k extrakci všeho, co bychom chtěli vědět o dynamikě.
Až to uděláte (a zjednodušíte výsledek na případ, kde má čistě stav), Schrödinger rovnice pro stav nečinnosti se nachází \begin{align} i \ partial_t \ket{\psi (t)} = \hat{H} (t) \ket{\psi (t)}.
\end{align}

Tato rovnice, i když je to méně intuitivní než výše uvedená, představuje pravděpodobně nejjednodušší výraz pro porozumění tomu, jak simulovat dynamiku nedostatku do více než jednoho nebo klasického počítače.
Důvodem je to, že řešení rozdílové rovnice lze vyjádřit v následujícím formuláři (pro případ, kdy je Hamiltonian konstanta v $t $) \begin{align} \ket{\psi (t)} = e ^ {-iHt} \ket{\psi (0)}.
\end{align} zde $e ^ {iHt} $ je jednotná matice.
To znamená, že existuje okruh, který může být navržený tak, aby se mohl provést, protože počítače můžou přesně blížit jakékoli jednotkové matrice.
Tato operace hledání okruhu termínu pro implementaci operátoru vývoje času na základě počtu procesorů $e ^ {-iHt} $ je to, co se často říká simulace období, nebo zejména Simulace dynamických procesorů.
