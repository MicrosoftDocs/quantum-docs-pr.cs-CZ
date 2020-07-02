---
title: Specifikace schématu Broombridge (ver 0,2)
description: Podrobně popisuje specifikace pro Broombridgeu pro každé z nich.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
ms.openlocfilehash: df7e651b7d32e672c6e83346ff603132bd55c1a2
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274642"
---
# <a name="broombridge-specification-v02"></a>Broombridge Specification v 0,2 #

Klíčová slova "musí", "nesmí", "požadováno", "musí", "nesmí", "by" neměla "," by "neměla být", "doporučeno", "by" měly být "nepovinné" v tomto dokumentu budou interpretována tak, jak je popsáno v [dokumentu RFC 2119](https://tools.ietf.org/html/rfc2119).

Jakýkoli postranní panel s nadpisy "Poznámka", "informace" nebo "upozornění" jsou informativní.

## <a name="introduction"></a>Úvod ##

Tato část je informativní.

Dokumenty Broombridge jsou určené ke sdělování instancí problémů simulace v chemii doby zpracování za použití simulace využití a programování sady nástrojů.

## <a name="serialization"></a>Serializace ##

Tato část je normativní.

Dokument Broombridge musí být serializován jako [dokument YAML 1,2](http://yaml.org/spec/) REPREZENTUJÍCÍ objekt JSON, jak je popsáno v [dokumentu RFC 4627](https://tools.ietf.org/html/rfc4627) oddíl 2,2.
Objekt serializovaný do YAML musí mít vlastnost `"$schema"` , jejíž hodnota je `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"` , a musí být platný podle konceptu schématu JSON-06 specifikace [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].

Pro zbytek této specifikace "objekt Broombridge" bude odkazovat na objekt JSON deserializaci z dokumentu Broombridge YAML.

Pokud není výslovně uvedeno jinak, objekty nesmí mít další vlastnosti nad rámec těch, které jsou výslovně uvedené v tomto dokumentu.

## <a name="additional-definitions"></a>Další definice ##

Tato část je normativní.

### <a name="quantity-objects"></a>Množství objektů ###

Tato část je normativní.

_Objekt množství_ je objekt JSON a musí mít vlastnost, `units` jejíž hodnota je jedna z povolených hodnot uvedených v tabulce 1.

Objekt množství je _jednoduchý objekt množství_ , pokud má `value` kromě jeho vlastnosti jednu vlastnost `units` .
Hodnota `value` vlastnosti musí být číslo.

Objekt množství je objekt s _ohraničeným množstvím_ , pokud má vlastnosti `lower` a `upper` kromě jeho `units` Vlastnosti.
Hodnoty `lower` `upper` vlastností a musí být čísla.
Objekt vázaného množství může mít vlastnost, `value` jejíž hodnota je číslo.

Objekt množství je objekt množství _zhuštěného pole_ , pokud obsahuje vlastnost `format` a vlastnost `values` kromě jeho `units` Vlastnosti.
Hodnota `format` musí být řetězec `sparse` .
Hodnotou `values` vlastnosti musí být pole.
Každý prvek `values` musí být pole reprezentující indexy a hodnotu množství zhuštěného pole.

Indexy pro každý prvek objektu množství zhuštěného pole musí být jedinečné v celém objektu množství zhuštěného pole.
Pokud je index přítomen s hodnotou `0` , analyzátor musí zacházet s objektem množství zhuštěného pole stejně jako objekt množství zhuštěného pole, ve kterém index není přítomen vůbec.


Objekt množství musí být buď

- jednoduchý objekt množství,
- objekt s ohraničeným množstvím nebo
- objekt množství zhuštěného pole


### <a name="examples"></a>Příklady ###

Tato část je informativní.

Jednoduché množství představující $1.9844146837 \, \mathrm{ha} $:

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

Ohraničené množství představující jednotnou distribuci v intervalu $ [-7,-6] \, \mathrm{ha} $:

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

Následuje množství zhuštěného pole s elementem `[1, 2]` , který se rovná `hello` a element `[3, 4]` se rovná `world` :

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a>Formátovat oddíl ##

Tato část je normativní.

Objekt Broombridge musí mít vlastnost, `format` jejíž hodnota je objekt JSON, který má nazvaná jednu vlastnost `version` .
`version`Vlastnost musí mít hodnotu `"0.2"` .

### <a name="example"></a>Příklad ###

Tato část je informativní.

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a>Oddíl popisu problému ##

Tato část je normativní.

Objekt Broombridge musí mít vlastnost, `problem_description` jejíž hodnota je pole JSON.
Každá položka v hodnotě `problem_description` vlastnosti musí být objekt JSON, který popisuje jednu sadu integrálních objektů, jak je popsáno ve zbývající části této části.
Ve zbývající části této části se termín "objekt popisu problému" odkazuje na položku v hodnotě `problem_description` vlastnosti objektu Broombridge.

Každý objekt popisu problému musí mít vlastnost, `metadata` jejíž hodnota je objekt JSON.
Hodnota `metadata` může být prázdný objekt JSON (tj. `{}` ) nebo může obsahovat další vlastnosti definované implementací.

### <a name="hamiltonian-section"></a>Oddíl Hamiltonian ###

#### <a name="overview"></a>Přehled ####

Tato část je informativní.

`hamiltonian`Vlastnost každého objektu popisu problému popisuje Hamiltonian pro konkrétní chemii problému při práci s procesorem, a to tak, že uvádí jeho jeden a dva tělo jako zhuštěná pole reálných čísel.
Hamiltonian operátory popsané každým popisem problému mají formu

$ $ H = \sum \_ \{ i, j \} \sum \_ {\sigma\in \\ {\uparrow, \downarrow \\ }} h \_ \{ IJ \} a ^ \{ \dagger \} \_ {i, \sigma} a \_ {j, \sigma} + \frac {1} {2} \sum \_ \{ i, j, k, l \} \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} H \_ {IJKL} a ^ \dagger \_ {i, \sigma} a ^ \dagger \_ {k, \rho} a \_ {l, \rho} a \_ {j, \sigma}, $ $

Tady $h _ {IJKL} = (IJ | kl) $ v konvenci Mulliken.

Pro přehlednost je pojem jednorázový

$ $ h_ {IJ} = \int {\mathrm d} x \psi ^ * \_ i (x) \left (\frac {1} {2} \nabla ^ 2 + \sum \_ {A} \frac{Z \_ a} {| x-x \_ A |}  \right) \psi \_ j (x), $ $

a dva elektronické podmínky jsou

$ $ h \_ \{ IJKL \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} (x \_ 2) \psi \_ l (x \_ 2).
$$

Jak je uvedeno v našem popisu [ `basis_set` vlastnosti](#basis-set-object) každého elementu `integral_sets` vlastnosti, dále explicitně předpokládáme, že použité základní funkce jsou reálné.
To umožňuje použít následující symmetries mezi podmínkami pro komprimaci reprezentace Hamiltonian.

$ $ h_ {IJKL} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = H_ {lkij} = h_ {LKJI}.
$$


#### <a name="contents"></a>Obsah ####

Tato část je normativní.

Každý objekt popisu problému musí mít vlastnost, `hamiltonian` jejíž hodnota je objekt JSON.
Hodnota `hamiltonian` vlastnosti je označována jako objekt Hamiltonian a musí mít vlastnosti, `one_electron_integrals` `two_electron_integrals` jak je popsáno ve zbývající části této části.

Každý objekt popisu problému musí mít vlastnost, `coulomb_repulsion` jejíž hodnota je jednoduchý objekt množství.
Každý objekt popisu problému musí mít vlastnost, `energy_offet` jejíž hodnota je jednoduchý objekt množství.
> ZNAČTE Hodnoty `coulomb_repulsion` a `energy_offet` přidané společně zachycují podmínky identity Hamiltonian.

##### <a name="one-electron-integrals-object"></a>Objekt s jedním elektronovým integrálem #####

Tato část je normativní.

`one_electron_integrals`Vlastnost objektu HAMILTONIAN musí být množstvím zhuštěného pole, jehož indexy jsou dvě celá čísla a jejichž hodnoty jsou čísla.
Každý výraz musí mít indexy `[i, j]` , kde `i >= j` .

> ZNAČTE To odráží symetrii, který $h _ {IJ} = h_ {ji} $, což je podsekvence faktu, že Hamiltonian je Hermitian.


###### <a name="example"></a>Příklad ######

Tato část je informativní.

Následující množství zhuštěného pole představuje Hamiltonian $ $ H = \left (-5,0 (a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {1, \downarrow}) + 0,17 (a ^ \{ \dagger \} \_ {2, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {2, \uparrow} + a ^ \{ \dagger \} \_ {2, \downarrow} a \_ {1, \downarrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {2, \downarrow}) \right) \\ , \mathrm{ha}.
$$

```yaml
one_electron_integrals:     # required
    units: hartree          # required
    format: sparse          # required
    values:                 # required
        # i j f(i,j)
        - [1, 1, -5.0]
        - [2, 1,  0.17]
```
> [!NOTE]
> Broombridge používá indexování založené na 1.


##### <a name="two-electron-integrals-object"></a>Objekt dvoumístné integrály #####

Tato část je normativní.

`two_electron_integrals`Vlastnost objektu HAMILTONIAN musí být množstvím zhuštěného pole s jednou další vlastností nazvanou `index_convention` .
Každý prvek hodnoty `two_electron_integrals` musí mít čtyři indexy.

Každá `two_electron_integrals` vlastnost musí mít `index_convention` vlastnost.
Hodnota `index_convention` vlastnosti musí být jedna z povolených hodnot uvedených v tabulce 1.
Pokud hodnota `index_convention` je `mulliken` a potom pro každý prvek `two_electron_integrals` množství zhuštěného pole, analyzátor načítající dokument Broombridge musí vytvořit instanci Hamiltonianho výrazu, který se rovná $h operátoru _ {i, j, k, l} a ^ \ dagger_i ^ \ dagger_j a_k a_l $, kde $i $, $j $, $k $ a $l $ musí být celá čísla v hodnotě nejméně 1 a kde $h _ {i, j, k, l} $ je prvkem `[i, j, k, l, h(i, j, k, l)]` množství zhuštěného pole.

###### <a name="symmetries"></a>Symmetries ######

Tato část je normativní.

Pokud `index_convention` `two_electron_integrals` je vlastnost objektu rovna `mulliken` , pak pokud je přítomen element s indexy `[i, j, k, l]` , následující indexy nesmí být přítomny, pokud nejsou rovny `[i, j, k, l]` :

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> Vzhledem k tomu `index_convention` , že vlastnost je objekt zhuštěného množství, žádné indexy nelze opakovat na různých prvcích.
> Konkrétně, pokud je přítomen element s indexy `[i, j, k, l]` , žádné další prvky nemohou mít tyto indexy.


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>Příklad #######

Tato část je informativní.

Následující objekt určuje Hamiltonian

$ $ H = \frac12 \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} \Biggr (1,6 a ^ {\dagger} \_ {1; \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {1, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {3, \rho} a { \_ 2, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {2, \rho} a \_ {3, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6} \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} a \_ {2, \rho} a \_ {3, \sigma} $ $ $ $-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2. \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {1, \rho} a \_ {6, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3 , \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3, \rho} a \_ {1, \Rho} a \_ {6, \sigma}\Biggr) \\ , \textrm{ha}.
$$

```yaml
two_electron_integrals:
    index_convention: mulliken
    units: hartree
    format: sparse
    values:
        - [1, 1, 1, 1,  1.6]
        - [6, 1, 3, 2, -0.1]
```

### <a name="initial-state-section"></a>Oddíl počáteční stav ###

Tato část je normativní.

`initial_state_suggestion`Objekt, jehož hodnota je pole JSON, určuje počáteční stavy, které mají zájem o zadaný Hamiltonian. Každá položka v hodnotě `initial_state_suggestion` vlastnosti musí být objekt JSON, který popisuje jeden stav, jak je popsáno ve zbývající části této části.
Ve zbývající části této části se pojem "stavový objekt" odkazuje na položku v hodnotě `initial_state_suggestion` vlastnosti objektu Broombridge.

#### <a name="state-object"></a>Stavový objekt ####

Tato část je normativní.

Každý objekt stavu musí mít `label` vlastnost obsahující řetězec. Každý objekt stavu musí mít `method` vlastnost. Hodnota `method` vlastnosti musí být jedna z povolených hodnot uvedených v tabulce 3.
Každý objekt stavu může mít vlastnost, `energy` jejíž hodnota musí být jednoduchý objekt množství.

Pokud `method` je hodnota vlastnosti `sparse_multi_configurational` , objekt stavu musí mít `superposition` vlastnost obsahující pole základních stavů a jejich nenormalizované amplitudy.

Například počáteční stavy $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) + 0,2 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \uparrow}a ^ {\dagger} \_ {2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0,2 | ^ 2}} \ket {0} , kde $ \ket{E} $ má energii $0,987 \textrm{ha} $, jsou reprezentovány
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "|G0>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
  - label: "|G1>"
    method: sparse_multi_configurational
    superposition:
      - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
  - label: "|G2>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
  - label: "|E>"
    energy: {units: hartree, value: 0.987}
    method: sparse_multi_configurational
    superposition:
      - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
      - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

Pokud `method` je hodnota vlastnosti `unitary_coupled_cluster` , objekt stavu musí mít `cluster_operator` vlastnost, jejíž hodnota je objekt JSON.
Objekt JSON musí mít vlastnost, `reference_state` jejíž hodnota je základní stav.
Objekt JSON může mít vlastnost, `one_body_amplitudes` jejíž hodnota je pole operátorů clusteru s jedním tělem a jejich amplitudy.
Objekt JSON může mít vlastnost, `two_body_amplitudes` jejíž hodnota je pole operátorů clusteru se dvěma body a jejich amplitudy.
obsahující pole základních stavů a jejich nenormalizované amplitudy.

Například stav $ $ \ket{\Text{Reference}} = (a ^ {\dagger} \_ {1; \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} , $ $

$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\Text{reference}}, $ $

$ $ T = 0,1 a ^ {\dagger} \_ {3, \uparrow}a \_ {2, \downarrow} + 0,2 a ^ {\dagger} \_ {2, \uparrow}a \_ {2, \downarrow}-0,3 a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \downarrow}a { \_ 3, \uparrow}a \_ {2, \downarrow} $ $ je reprezentován
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "UCCSD"
    method: unitary_coupled_cluster
    cluster_operator: # Initial state that cluster operator is applied to.
        reference_state: 
          [1.0, "(1a)+", "(2a)+", "(2b)+", '|vacuum>']
        one_body_amplitudes: # A one-body cluster term is t^{q}_{p} a^\dag_p a_q   
            - [0.1, "(3a)+", "(2b)"]
            - [-0.2, "(2a)+", "(2b)"]
        two_body_amplitudes: # A two-body unitary cluster term is t^{rs}_{pq} a^\dag_p a^\dag_q a_r a_s
            - [-0.3, "(1a)+", "(3b)+", "(3a)", "(2b)"]
```

#### <a name="basis-set-object"></a>Základní objekt sady ####

Tato část je normativní.

Každý objekt popisu problému může mít `basis_set` vlastnost.
Je-li k dispozici, hodnota `basis_set` vlastnosti musí být objekt se dvěma vlastnostmi `type` a `name` .

Základní funkce identifikované hodnotou `basis_set` vlastnosti musí být reálné.

> [!NOTE]
> Předpokladem, že všechny základní funkce jsou reálné, mohou být v budoucích verzích této specifikace uvolněny.

## <a name="tables-and-lists"></a>Tabulky a seznamy ##

### <a name="table-1-allowed-physical-units"></a>Tabulka 1. Povolené fyzické jednotky ###

Tato část je normativní.

Libovolný řetězec určující jednotku musí být jeden z následujících:

- `hartree`
- `ev`

Analyzátory a producenti musí považovat následující jednoduché objekty množství jako ekvivalentní:

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>Tabulka 2. Povolené konvence indexu ###

Tato část je normativní.

Libovolný řetězec určující konvenci indexu musí být jeden z následujících:

- `mulliken`

Tato část je informativní.

V budoucích verzích této specifikace se můžou zavést další konvence indexu.

#### <a name="interpretation-of-index-conventions"></a>Výklad konvencí indexů ####

Tato část je informativní.

### <a name="table-3-allowed-state-methods"></a>Tabulka 3. Povolené metody stavu ###

Tato část je normativní.

Libovolný řetězec určující metodu stavu musí být jedna z následujících:

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

Tato část je informativní.

V budoucích verzích této specifikace mohou být zavedeny další metody stavu.