---
title: Specifikace schématu Broombridge
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: a950e04d44e5de8091b034214258d2c2fa663f58
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185354"
---
# <a name="broombridge-specification-v01"></a>Specifikace Broombridge v 0,1 #

Klíčová slova "musí", "nesmí", "požadováno", "musí", "nesmí", "by" neměla "," by "neměla být", "doporučeno", "by" měly být "nepovinné" v tomto dokumentu budou interpretována tak, jak je popsáno v [dokumentu RFC 2119](https://tools.ietf.org/html/rfc2119).

Jakýkoli postranní panel s nadpisy "Poznámka", "informace" nebo "upozornění" jsou informativní.

## <a name="introduction"></a>Představení ##

Tato část je informativní.

Dokumenty Broombridge jsou určené ke sdělování instancí problémů simulace v chemii doby zpracování za použití simulace využití a programování sady nástrojů.

## <a name="serialization"></a>Serializace ##

Tato část je normativní.

Dokument Broombridge musí být serializován jako [dokument YAML 1,2](http://yaml.org/spec/) REPREZENTUJÍCÍ objekt JSON, jak je popsáno v [dokumentu RFC 4627](https://tools.ietf.org/html/rfc4627) oddíl 2,2.
Objekt serializovaný do YAML musí mít vlastnost `"$schema"` jejíž hodnota je `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`a musí být platný podle konceptu schématu JSON-06 specifikace [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].

Pro zbytek této specifikace "objekt Broombridge" bude odkazovat na objekt JSON deserializaci z dokumentu Broombridge YAML.

Pokud není výslovně uvedeno jinak, objekty nesmí mít další vlastnosti nad rámec těch, které jsou výslovně uvedené v tomto dokumentu.

## <a name="additional-definitions"></a>Další definice ##

Tato část je normativní.

### <a name="quantity-objects"></a>Množství objektů ###

Tato část je normativní.

_Objekt množství_ je objekt JSON a musí mít vlastnost, `units` jejíž hodnota je jedna z povolených hodnot uvedených v tabulce 1.

Objekt množství je _jednoduchý objekt množství_ , pokud má jednu vlastnost `value` kromě vlastnosti `units`.
Hodnota vlastnosti `value` musí být číslo.

Objekt množství je objekt s _vazbou množství_ , pokud má vlastnosti `lower` a `upper` kromě jeho vlastnosti `units`.
Hodnoty vlastností `lower` a `upper` musí být čísla.
Objekt vázaného množství může mít vlastnost, `value` jejíž hodnota je číslo.

Objekt množství je objekt množství _zhuštěného pole_ , pokud má vlastnost `format` a vlastnost `values` kromě vlastnosti `units`.
Hodnota `format` musí být `sparse`řetězce.
Hodnota vlastnosti `values` musí být pole.
Každý prvek `values` musí být pole reprezentující indexy a hodnotu množství zhuštěného pole.

Indexy pro každý prvek objektu množství zhuštěného pole musí být jedinečné v celém objektu množství zhuštěného pole.
Pokud je index přítomen s hodnotou `0`, analyzátor musí zacházet s objektem množství zhuštěného pole stejně jako objekt množství zhuštěného pole, ve kterém index není přítomen vůbec.


Objekt množství musí být buď

- jednoduchý objekt množství,
- objekt s ohraničeným množstvím nebo
- objekt množství zhuštěného pole


### <a name="examples"></a>Příklady ###

Tato část je informativní.

Jednoduché množství představující $1.9844146837\,\mathrm{Ha} $:

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

Ohraničené množství představující jednotnou distribuci v intervalu $ [-7,-6]\,\mathrm{Ha} $:

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

Následuje množství zhuštěného pole s elementem `[1, 2]` rovno `hello` a elementu `[3, 4]` rovno `world`:

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

Objekt Broombridge musí mít vlastnost `format` jejíž hodnota je objekt JSON s jednou vlastností nazvanou `version`.
Vlastnost `version` musí mít hodnotu `"0.1"`.

### <a name="example"></a>Příklad: ###

Tato část je informativní.

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a>Oddíl integrálních sad ##

Tato část je normativní.

Objekt Broombridge musí mít vlastnost, `integral_sets` jejíž hodnota je pole JSON.
Každá položka v hodnotě vlastnosti `integral_sets` musí být objekt JSON, který popisuje jednu sadu integrálních objektů, jak je popsáno ve zbývající části této části.
Ve zbývající části této části se pojem "objekt" integrální sady "odkazuje na položku v hodnotě vlastnosti `integral_sets` objektu Broombridge.

Každý objekt integrální sady musí mít vlastnost, `metadata` jejíž hodnota je objekt JSON.
Hodnota `metadata` může být prázdný objekt JSON (tj. `{}`) nebo může obsahovat další vlastnosti definované implementací.

### <a name="hamiltonian-section"></a>Oddíl Hamiltonian ###

#### <a name="overview"></a>Přehled ####

Tato část je informativní.

Vlastnost `hamiltonian` každého objektu integrální sady popisuje Hamiltonian pro konkrétní chemii problému při práci s procesorem, a to tak, že uvádí své první a dvě tělo jako zhuštěná pole reálných čísel.
Hamiltonian operátory popsané každým objektem integrální sady mají formu.

$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} H\_\{IJ\} ^\{\dagger\}\_{i , \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} h\_{IJKL} a ^ \dagger\_{i , \sigma} a ^ \dagger\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $

Tady $h _ {IJKL} = (IJ | kl) $ v konvenci Mulliken.

Pro přehlednost je pojem jednorázový

$ $ H_ {IJ} = \int {\mathrm d} x \psi ^ *\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $

a dva elektronické podmínky jsou

$ $ h\_\{IJKL\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psi\_l (x\_2).
$$

Jak je uvedeno v našem popisu [vlastnosti`basis_set`](#basis-set-object) každého prvku `integral_sets` vlastnosti, explicitně předpokládáme, že použité základní funkce jsou reálné.
To umožňuje použít následující symmetries mezi podmínkami pro komprimaci reprezentace Hamiltonian.

$ $ H_ {IJKL} = H_ {ijlk} = H_ {jikl} = H_ {jilk} = H_ {klij} = H_ {klji} = H_ {lkij} = H_ {LKJI}.
$$


#### <a name="contents"></a>Obsah ####

Tato část je normativní.

Každá celočíselná sada musí mít vlastnost, `hamiltonian` jejíž hodnota je objekt JSON.
Hodnota vlastnosti `hamiltonian` je označována jako objekt Hamiltonian a musí mít `one_electron_integrals` vlastnosti a `two_electron_integrals`, jak je popsáno ve zbývající části této části.
Objekt Hamiltonian může mít také vlastnost `particle_hole_representation`.
Je-li k dispozici, hodnota `particle_hole_representation` musí odpovídat formátu popsanému ve zbývající části této části.

##### <a name="one-electron-integrals-object"></a>Objekt s jedním elektronovým integrálem #####

Tato část je normativní.

Vlastnost `one_electron_integrals` objektu Hamiltonian musí být množstvím zhuštěného pole, jehož indexy jsou dvě celá čísla a jejichž hodnoty jsou čísla.
Každý termín musí mít indexy `[i, j]`, kde `i >= j`.

> ZNAČTE To odráží symetrii, který $h _ {IJ} = H_ {ji} $, což je podsekvence faktu, že Hamiltonian je Hermitian.


###### <a name="example"></a>Příklad: ######

Tato část je informativní.

Následující množství zhuštěného pole představuje Hamiltonian $ $ H = \left (-5,0 (a ^\{\dagger\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1 , \downarrow}) + 0,17 (a ^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 , \downarrow} a\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{2, \downarrow}) \right)\\, \mathrm{Ha}.
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

Vlastnost `two_electron_integrals` objektu Hamiltonian musí být množstvím zhuštěného pole s jednou další vlastností nazvanou `index_convention`.
Každý prvek hodnoty `two_electron_integrals` musí mít čtyři indexy.

Každá vlastnost `two_electron_integrals` musí mít vlastnost `index_convention`.
Hodnota vlastnosti `index_convention` musí být jedna z povolených hodnot uvedených v tabulce 1.
Pokud je hodnota `index_convention` `mulliken`, pak pro každý prvek `two_electron_integrals` množství zhuštěného pole musí být analyzátorem načítání dokumentu Broombridge vytvořen Hamiltonian výraz, který se rovná dvěma elektronům, $h _ {i, j, k, l} a ^ \dagger_i a ^ \dagger_j a_k a_l $ , kde $i $, $j $, $k $, a $l $, musí být celá čísla v rozsahu od 1 do počtu Electrons určených vlastností `n_electrons` objektu integrální sady a kde $h _ {i, j, k, l} $ je prvek `[i, j, k, l, h(i, j, k, l)]` množství zhuštěného pole.

###### <a name="symmetries"></a>Symmetries ######

Tato část je normativní.

Pokud je vlastnost `index_convention` objektu `two_electron_integrals` rovna hodnotě `mulliken`, pak pokud je přítomen element s indexy `[i, j, k, l]`, nesmí být následující indexy přítomny, pokud nejsou rovny `[i, j, k, l]`:

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> Vzhledem k tomu, že vlastnost `index_convention` je objekt zhuštěného množství, nemohou být žádné indexy opakovány na různých prvcích.
> Zejména pokud je k dispozici element s indexy `[i, j, k, l]`, žádné další prvky nemohou mít tyto indexy.


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>Příklad: #######

Tato část je informativní.

Následující objekt určuje Hamiltonian

$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{6} , \sigma} a ^ {\dagger}\_{1, \rho}\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{2, \rho} a\_{3 , \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{2 , \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2 , \rho} a\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2 , \sigma} a ^ {\dagger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.
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

##### <a name="particlehole-representation-object"></a>Částic – objekt reprezentace otvoru #####

Tato část je normativní.

Objekt reprezentace částic určuje, zda jsou uložené integrály definovány s ohledem na vyjádření otvorů částic podle toho, jak Annihilation operátory vytváření a operátorů popisují excitations od používaného referenčního stavu, jako je Hartree – Stav Fock
Objekt je nepovinný.
Pokud objekt není zadán, bude Hamiltonian interpretován tak, jak není zadáno v vyjádření částic.
Je-li k dispozici, hodnota `particle_hole_representation` musí být objekt množství zhuštěného pole, jehož indexy jsou čtyři celá čísla a jejichž hodnoty jsou číslo a řetězec.
Část řetězce hodnoty každého elementu musí obsahovat pouze znaky `'+'` a `'-'`, které určují, zda daný faktor v daném termínu je operátor vytvoření nebo Annihilation v vyjádření částic – díra.  Například `"-+++"` mikroreaguje na díru vytvořenou v lokalitě $i $ a částicích, které jsou vytvářeny v lokalitách $j, k $ a $l $.

> [!NOTE]
> Jako hodnota `particle_hole_representation` je objekt množství zhuštěného pole, musí být zadány vlastnosti `unit` a `format`.
> Přijatelné jednotky jsou uvedeny v tabulce 1.
> Vlastnost `format` je povinná a označuje, zda jsou Hamiltonian koeficienty zadány jako zhuštěné nebo zhuštěné pole.
> V aktuální verzi jsou podporována pouze zhuštěná pole s výkladem, že všechny neurčené prvky jsou $0 $, ale budoucí verze mohou přidat podporu pro další hodnoty vlastnosti `format`.

### <a name="initial-state-section"></a>Oddíl počáteční stav ###

Objekt initial_state_suggestion Určuje počáteční stavy, které mají zájem o zadaný Hamiltonian. Tento objekt musí být pole objektů JSON `state`.

#### <a name="state-object"></a>Stavový objekt ####

Každý stav představuje nadpozici obsazené orbitals. Každý objekt stavu musí mít vlastnost `label` obsahující řetězec. Každý objekt stavu musí mít vlastnost `superposition` obsahující pole základních stavů a jejich nenormalizované amplitudy.

Například počáteční stavy $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1 , \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0,2 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0,2 | ^ 2}} \ket{0} $ $ jsou reprezentované
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
    - state:
        label: "|G0>"
        superposition:
            - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G1>"
        superposition:
            - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G2>"
        superposition:
            - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
    - state:
        label: "|E>"
        superposition:
            - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
            - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

#### <a name="basis-set-object"></a>Základní objekt sady ####

Tato část je normativní.

Každý objekt integrální sady může mít vlastnost `basis_set`.
Je-li k dispozici, hodnota vlastnosti `basis_set` musí být objekt se dvěma vlastnostmi, `type` a `name`.

Základní funkce identifikované hodnotou vlastnosti `basis_set` musí být reálné.

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
