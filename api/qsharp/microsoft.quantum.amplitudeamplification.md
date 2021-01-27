---
uid: Microsoft.Quantum.AmplitudeAmplification
title: Obor názvů Microsoft. AmplitudeAmplification.
ms.date: 1/23/2021 12:00:00 AM
ms.topic: managed-reference
qsharp.kind: namespace
qsharp.name: Microsoft.Quantum.AmplitudeAmplification
qsharp.summary: This namespace contains functions and operations for performing amplitude amplification.
ms.openlocfilehash: a014f923de62c5e660c1c0fc839fbe60e80f8ba9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845836"
---
# <a name="microsoftquantumamplitudeamplification-namespace"></a>Obor názvů Microsoft. AmplitudeAmplification.

Tento obor názvů obsahuje funkce a operace pro provádění zesílení amplitud.



## <a name="description"></a>Popis

Zesílení zesílení oblivious s částečnou odrazací je nejobecnější forma zesílení amplitud, které jsou zde implementovány.

Tato funkce se volá prostřednictvím operace AmpAmpObliviousByReflectionPhases.

Má dva Registry: `ancillaRegister` a `systemRegister` .

To přijímá dva Oracle pro tyto odrazy typu `ReflectionOracle` , které se chovají pouze v `ancillaRegister` registru.

To přijímá speciální rozhraní Oracle pro oblivious amplitudy amplitud typu `ObliviousOracle` , které společně působí v obou registrech.

Hodnota vstupního stavu na `ancillaRegister` je považována za jedinečnou $-$1 eigenstate prvního operátoru reflexe $I-2 \ KET {s} \ Bra {s} $.

Odrazy týkající se cílového stavu se často implementují tím, že předpokládají přístup k Oracle, který tento stav připravuje z výpočetního základu $ \ket{0\cdots 0} $.

Naše konvence pro tyto Oracle vyžaduje dva Registry: registr s jedním qubit `flagQubit` a registr pro všechno ostatní v registraci ancillaRegister.

Oracle typu `StateOracle` funguje společně na obou registrech k vytvoření cílového stavu označeného $ \ket {1} $ v `flagQubit` registru s určitou skutečnou amplitudou.

Reflexe `ReflectionOracle` stavu tohoto příznaku je vygenerována operací `TargetStateReflectionOracle` .

Odraz `ReflectionOracle` o stavu vstupu `ancillaRegister` se generuje obráceným StateOracle a pak se odráží přibližně $ \ket{0\cdots 0} $ s ReflectionStart ().

Oracle typu `DeterministicStateOracle` funguje na `qubitState` registrech, aby bylo možné vytvořit cílový stav přesně bez příznaku.

`AmpAmpObliviousByOraclePhases` je verze oblivious zesílení amplitud, která přijímá Oracle `StateOracle` a `ObliviousOracle` místo odrazů.

Mějte na paměti, že zesílení amplitud je zvláštní případ oblivious zesílení amplitud `ObliviousOracle` , kde je operátorem identity, a neexistuje žádný systémový qubits, tj. `systemRegister` je prázdný.

Tato funkce se volá prostřednictvím operace `AmpAmByReflectionPhases` a `AmpAmpByOraclePhases` .

Fáze pro částečné odrazy ve standardním případu hledání Grover jsou poskytovány funkcí AmpAmpPhasesStandard.

Například máme následující závislosti: AmpAmpByOracle-> AmpAmpByOraclePhases-> AmpAmpObliviousByOraclePhases-> AmpAmpObliviousByReflectionPhases.