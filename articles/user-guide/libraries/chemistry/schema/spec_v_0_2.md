---
title: Specifikace schématu Broombridge (ver 0,2)
description: Podrobně popisuje specifikace pro Broombridgeu pro každé z nich.
author: guanghaolow
ms.author: gulow
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
no-loc:
- Q#
- $$v
ms.openlocfilehash: 851d10c0137deecf8e861aad30b5e08a9ae61754
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833761"
---
# <a name="broombridge-specification-v02"></a><span data-ttu-id="82805-103">Broombridge Specification v 0,2</span><span class="sxs-lookup"><span data-stu-id="82805-103">Broombridge Specification v0.2</span></span> #

<span data-ttu-id="82805-104">Klíčová slova "musí", "nesmí", "požadováno", "musí", "nesmí", "by" neměla "," by "neměla být", "doporučeno", "by" měly být "nepovinné" v tomto dokumentu budou interpretována tak, jak je popsáno v [dokumentu RFC 2119](https://tools.ietf.org/html/rfc2119).</span><span class="sxs-lookup"><span data-stu-id="82805-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="82805-105">Jakýkoli postranní panel s nadpisy "Poznámka", "informace" nebo "upozornění" jsou informativní.</span><span class="sxs-lookup"><span data-stu-id="82805-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="82805-106">Úvod</span><span class="sxs-lookup"><span data-stu-id="82805-106">Introduction</span></span> ##

<span data-ttu-id="82805-107">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="82805-107">This section is informative.</span></span>

<span data-ttu-id="82805-108">Dokumenty Broombridge jsou určené ke sdělování instancí problémů simulace v chemii doby zpracování za použití simulace využití a programování sady nástrojů.</span><span class="sxs-lookup"><span data-stu-id="82805-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="82805-109">Serializace</span><span class="sxs-lookup"><span data-stu-id="82805-109">Serialization</span></span> ##

<span data-ttu-id="82805-110">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="82805-110">This section is normative.</span></span>

<span data-ttu-id="82805-111">Dokument Broombridge musí být serializován jako [dokument YAML 1,2](http://yaml.org/spec/) REPREZENTUJÍCÍ objekt JSON, jak je popsáno v [dokumentu RFC 4627](https://tools.ietf.org/html/rfc4627) oddíl 2,2.</span><span class="sxs-lookup"><span data-stu-id="82805-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="82805-112">Objekt serializovaný do YAML musí mít vlastnost `"$schema"` , jejíž hodnota je `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"` , a musí být platný podle konceptu schématu JSON-06 specifikace [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="82805-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="82805-113">Pro zbytek této specifikace "objekt Broombridge" bude odkazovat na objekt JSON deserializaci z dokumentu Broombridge YAML.</span><span class="sxs-lookup"><span data-stu-id="82805-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="82805-114">Pokud není výslovně uvedeno jinak, objekty nesmí mít další vlastnosti nad rámec těch, které jsou výslovně uvedené v tomto dokumentu.</span><span class="sxs-lookup"><span data-stu-id="82805-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="82805-115">Další definice</span><span class="sxs-lookup"><span data-stu-id="82805-115">Additional Definitions</span></span> ##

<span data-ttu-id="82805-116">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="82805-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="82805-117">Množství objektů</span><span class="sxs-lookup"><span data-stu-id="82805-117">Quantity Objects</span></span> ###

<span data-ttu-id="82805-118">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="82805-118">This section is normative.</span></span>

<span data-ttu-id="82805-119">_Objekt množství_ je objekt JSON a musí mít vlastnost, `units` jejíž hodnota je jedna z povolených hodnot uvedených v tabulce 1.</span><span class="sxs-lookup"><span data-stu-id="82805-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="82805-120">Objekt množství je _jednoduchý objekt množství_ , pokud má `value` kromě jeho vlastnosti jednu vlastnost `units` .</span><span class="sxs-lookup"><span data-stu-id="82805-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="82805-121">Hodnota `value` vlastnosti musí být číslo.</span><span class="sxs-lookup"><span data-stu-id="82805-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="82805-122">Objekt množství je objekt s _ohraničeným množstvím_ , pokud má vlastnosti `lower` a `upper` kromě jeho `units` Vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="82805-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="82805-123">Hodnoty `lower` `upper` vlastností a musí být čísla.</span><span class="sxs-lookup"><span data-stu-id="82805-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="82805-124">Objekt vázaného množství může mít vlastnost, `value` jejíž hodnota je číslo.</span><span class="sxs-lookup"><span data-stu-id="82805-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="82805-125">Objekt množství je objekt množství _zhuštěného pole_ , pokud obsahuje vlastnost `format` a vlastnost `values` kromě jeho `units` Vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="82805-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="82805-126">Hodnota `format` musí být řetězec `sparse` .</span><span class="sxs-lookup"><span data-stu-id="82805-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="82805-127">Hodnotou `values` vlastnosti musí být pole.</span><span class="sxs-lookup"><span data-stu-id="82805-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="82805-128">Každý prvek `values` musí být pole reprezentující indexy a hodnotu množství zhuštěného pole.</span><span class="sxs-lookup"><span data-stu-id="82805-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="82805-129">Indexy pro každý prvek objektu množství zhuštěného pole musí být jedinečné v celém objektu množství zhuštěného pole.</span><span class="sxs-lookup"><span data-stu-id="82805-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="82805-130">Pokud je index přítomen s hodnotou `0` , analyzátor musí zacházet s objektem množství zhuštěného pole stejně jako objekt množství zhuštěného pole, ve kterém index není přítomen vůbec.</span><span class="sxs-lookup"><span data-stu-id="82805-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="82805-131">Objekt množství musí být buď</span><span class="sxs-lookup"><span data-stu-id="82805-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="82805-132">jednoduchý objekt množství,</span><span class="sxs-lookup"><span data-stu-id="82805-132">a simple quantity object,</span></span>
- <span data-ttu-id="82805-133">objekt s ohraničeným množstvím nebo</span><span class="sxs-lookup"><span data-stu-id="82805-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="82805-134">objekt množství zhuštěného pole</span><span class="sxs-lookup"><span data-stu-id="82805-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="82805-135">Příklady</span><span class="sxs-lookup"><span data-stu-id="82805-135">Examples</span></span> ###

<span data-ttu-id="82805-136">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="82805-136">This section is informative.</span></span>

<span data-ttu-id="82805-137">Jednoduché množství představující $1.9844146837 \, \mathrm{ha} $:</span><span class="sxs-lookup"><span data-stu-id="82805-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="82805-138">Ohraničené množství představující jednotnou distribuci v intervalu $ [-7,-6] \, \mathrm{ha} $:</span><span class="sxs-lookup"><span data-stu-id="82805-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="82805-139">Následuje množství zhuštěného pole s elementem `[1, 2]` , který se rovná `hello` a element `[3, 4]` se rovná `world` :</span><span class="sxs-lookup"><span data-stu-id="82805-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="82805-140">Formátovat oddíl</span><span class="sxs-lookup"><span data-stu-id="82805-140">Format Section</span></span> ##

<span data-ttu-id="82805-141">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="82805-141">This section is normative.</span></span>

<span data-ttu-id="82805-142">Objekt Broombridge musí mít vlastnost, `format` jejíž hodnota je objekt JSON, který má nazvaná jednu vlastnost `version` .</span><span class="sxs-lookup"><span data-stu-id="82805-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="82805-143">`version`Vlastnost musí mít hodnotu `"0.2"` .</span><span class="sxs-lookup"><span data-stu-id="82805-143">The `version` property MUST have the value `"0.2"`.</span></span>

### <a name="example"></a><span data-ttu-id="82805-144">Příklad</span><span class="sxs-lookup"><span data-stu-id="82805-144">Example</span></span> ###

<span data-ttu-id="82805-145">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="82805-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a><span data-ttu-id="82805-146">Oddíl popisu problému</span><span class="sxs-lookup"><span data-stu-id="82805-146">Problem Description Section</span></span> ##

<span data-ttu-id="82805-147">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="82805-147">This section is normative.</span></span>

<span data-ttu-id="82805-148">Objekt Broombridge musí mít vlastnost, `problem_description` jejíž hodnota je pole JSON.</span><span class="sxs-lookup"><span data-stu-id="82805-148">The Broombridge object MUST have a property `problem_description` whose value is a JSON array.</span></span>
<span data-ttu-id="82805-149">Každá položka v hodnotě `problem_description` vlastnosti musí být objekt JSON, který popisuje jednu sadu integrálních objektů, jak je popsáno ve zbývající části této části.</span><span class="sxs-lookup"><span data-stu-id="82805-149">Each item in the value of the `problem_description` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="82805-150">Ve zbývající části této části se termín "objekt popisu problému" odkazuje na položku v hodnotě `problem_description` vlastnosti objektu Broombridge.</span><span class="sxs-lookup"><span data-stu-id="82805-150">In the remainder of this section, the term "problem description object" will refer to an item in the value of the `problem_description` property of the Broombridge object.</span></span>

<span data-ttu-id="82805-151">Každý objekt popisu problému musí mít vlastnost, `metadata` jejíž hodnota je objekt JSON.</span><span class="sxs-lookup"><span data-stu-id="82805-151">Each problem description object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="82805-152">Hodnota `metadata` může být prázdný objekt JSON (tj. `{}` ) nebo může obsahovat další vlastnosti definované implementací.</span><span class="sxs-lookup"><span data-stu-id="82805-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="82805-153">Oddíl Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="82805-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="82805-154">Přehled</span><span class="sxs-lookup"><span data-stu-id="82805-154">Overview</span></span> ####

<span data-ttu-id="82805-155">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="82805-155">This section is informative.</span></span>

<span data-ttu-id="82805-156">`hamiltonian`Vlastnost každého objektu popisu problému popisuje Hamiltonian pro konkrétní chemii problému při práci s procesorem, a to tak, že uvádí jeho jeden a dva tělo jako zhuštěná pole reálných čísel.</span><span class="sxs-lookup"><span data-stu-id="82805-156">The `hamiltonian` property of each problem description object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="82805-157">Hamiltonian operátory popsané každým popisem problému mají formu</span><span class="sxs-lookup"><span data-stu-id="82805-157">The Hamiltonian operators described by each problem description object take the form</span></span>

<span data-ttu-id="82805-158">$ $ H = \sum \_ \{ i, j \} \sum \_ {\sigma\in \\ {\uparrow, \downarrow \\ }} h \_ \{ IJ \} a ^ \{ \dagger \} \_ {i, \sigma} a \_ {j, \sigma} + \frac {1} {2} \sum \_ \{ i, j, k, l \} \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} H \_ {IJKL} a ^ \dagger \_ {i, \sigma} a ^ \dagger \_ {k, \rho} a \_ {l, \rho} a \_ {j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="82805-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="82805-159">Tady $h _ {IJKL} = (IJ | kl) $ v konvenci Mulliken.</span><span class="sxs-lookup"><span data-stu-id="82805-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="82805-160">Pro přehlednost je pojem jednorázový</span><span class="sxs-lookup"><span data-stu-id="82805-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="82805-161">$ $ h_ {IJ} = \int {\mathrm d} x \psi ^ \* \_ i (x) \left (\frac {1} {2} \nabla ^ 2 + \sum \_ {A} \frac{Z \_ a} {| x-x \_ A |}  \right) \psi \_ j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="82805-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="82805-162">a dva elektronické podmínky jsou</span><span class="sxs-lookup"><span data-stu-id="82805-162">and the two-electron term is</span></span>

<span data-ttu-id="82805-163">$ $ h \_ \{ IJKL \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} (x \_ 2) \psi \_ l (x \_ 2).</span><span class="sxs-lookup"><span data-stu-id="82805-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="82805-164">Jak je uvedeno v našem popisu [ `basis_set` vlastnosti](#basis-set-object) každého elementu `integral_sets` vlastnosti, dále explicitně předpokládáme, že použité základní funkce jsou reálné.</span><span class="sxs-lookup"><span data-stu-id="82805-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="82805-165">To umožňuje použít následující symmetries mezi podmínkami pro komprimaci reprezentace Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="82805-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="82805-166">$ $ h_ {IJKL} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = H_ {lkij} = h_ {LKJI}.</span><span class="sxs-lookup"><span data-stu-id="82805-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="82805-167">Obsah</span><span class="sxs-lookup"><span data-stu-id="82805-167">Contents</span></span> ####

<span data-ttu-id="82805-168">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="82805-168">This section is normative.</span></span>

<span data-ttu-id="82805-169">Každý objekt popisu problému musí mít vlastnost, `hamiltonian` jejíž hodnota je objekt JSON.</span><span class="sxs-lookup"><span data-stu-id="82805-169">Each problem description object MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="82805-170">Hodnota `hamiltonian` vlastnosti je označována jako objekt Hamiltonian a musí mít vlastnosti, `one_electron_integrals` `two_electron_integrals` jak je popsáno ve zbývající části této části.</span><span class="sxs-lookup"><span data-stu-id="82805-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>

<span data-ttu-id="82805-171">Každý objekt popisu problému musí mít vlastnost, `coulomb_repulsion` jejíž hodnota je jednoduchý objekt množství.</span><span class="sxs-lookup"><span data-stu-id="82805-171">Each problem description object MUST have a property `coulomb_repulsion` whose value is a simple quantity object.</span></span>
<span data-ttu-id="82805-172">Každý objekt popisu problému musí mít vlastnost, `energy_offet` jejíž hodnota je jednoduchý objekt množství.</span><span class="sxs-lookup"><span data-stu-id="82805-172">Each problem description object MUST have a property `energy_offet` whose value is a simple quantity object.</span></span>
> <span data-ttu-id="82805-173">ZNAČTE Hodnoty `coulomb_repulsion` a `energy_offet` přidané společně zachycují podmínky identity Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="82805-173">[NOTE] The values of `coulomb_repulsion` and `energy_offet` added together capture the identity term of the Hamiltonian.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="82805-174">Objekt s jedním elektronovým integrálem</span><span class="sxs-lookup"><span data-stu-id="82805-174">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="82805-175">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="82805-175">This section is normative.</span></span>

<span data-ttu-id="82805-176">`one_electron_integrals`Vlastnost objektu HAMILTONIAN musí být množstvím zhuštěného pole, jehož indexy jsou dvě celá čísla a jejichž hodnoty jsou čísla.</span><span class="sxs-lookup"><span data-stu-id="82805-176">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="82805-177">Každý výraz musí mít indexy `[i, j]` , kde `i >= j` .</span><span class="sxs-lookup"><span data-stu-id="82805-177">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="82805-178">ZNAČTE To odráží symetrii, který $h _ {IJ} = h_ {ji} $, což je podsekvence faktu, že Hamiltonian je Hermitian.</span><span class="sxs-lookup"><span data-stu-id="82805-178">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="82805-179">Příklad</span><span class="sxs-lookup"><span data-stu-id="82805-179">Example</span></span> ######

<span data-ttu-id="82805-180">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="82805-180">This section is informative.</span></span>

<span data-ttu-id="82805-181">Následující množství zhuštěného pole představuje Hamiltonian $ $ H = \left (-5,0 (a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {1, \downarrow}) + 0,17 (a ^ \{ \dagger \} \_ {2, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {2, \uparrow} + a ^ \{ \dagger \} \_ {2, \downarrow} a \_ {1, \downarrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {2, \downarrow}) \right) \\ , \mathrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="82805-181">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="82805-182">Broombridge používá indexování založené na 1.</span><span class="sxs-lookup"><span data-stu-id="82805-182">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="82805-183">Objekt dvoumístné integrály</span><span class="sxs-lookup"><span data-stu-id="82805-183">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="82805-184">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="82805-184">This section is normative.</span></span>

<span data-ttu-id="82805-185">`two_electron_integrals`Vlastnost objektu HAMILTONIAN musí být množstvím zhuštěného pole s jednou další vlastností nazvanou `index_convention` .</span><span class="sxs-lookup"><span data-stu-id="82805-185">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="82805-186">Každý prvek hodnoty `two_electron_integrals` musí mít čtyři indexy.</span><span class="sxs-lookup"><span data-stu-id="82805-186">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="82805-187">Každá `two_electron_integrals` vlastnost musí mít `index_convention` vlastnost.</span><span class="sxs-lookup"><span data-stu-id="82805-187">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="82805-188">Hodnota `index_convention` vlastnosti musí být jedna z povolených hodnot uvedených v tabulce 1.</span><span class="sxs-lookup"><span data-stu-id="82805-188">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="82805-189">Pokud hodnota `index_convention` je `mulliken` a potom pro každý prvek `two_electron_integrals` množství zhuštěného pole, analyzátor načítající dokument Broombridge musí vytvořit instanci Hamiltonianho výrazu, který se rovná $h operátoru _ {i, j, k, l} a ^ \ dagger_i ^ \ dagger_j a_k a_l $, kde $i $, $j $, $k $ a $l $ musí být celá čísla v hodnotě nejméně 1 a kde $h _ {i, j, k, l} $ je prvkem `[i, j, k, l, h(i, j, k, l)]` množství zhuštěného pole.</span><span class="sxs-lookup"><span data-stu-id="82805-189">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers of value at least 1, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="82805-190">Symmetries</span><span class="sxs-lookup"><span data-stu-id="82805-190">Symmetries</span></span> ######

<span data-ttu-id="82805-191">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="82805-191">This section is normative.</span></span>

<span data-ttu-id="82805-192">Pokud `index_convention` `two_electron_integrals` je vlastnost objektu rovna `mulliken` , pak pokud je přítomen element s indexy `[i, j, k, l]` , následující indexy nesmí být přítomny, pokud nejsou rovny `[i, j, k, l]` :</span><span class="sxs-lookup"><span data-stu-id="82805-192">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="82805-193">Vzhledem k tomu `index_convention` , že vlastnost je objekt zhuštěného množství, žádné indexy nelze opakovat na různých prvcích.</span><span class="sxs-lookup"><span data-stu-id="82805-193">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="82805-194">Konkrétně, pokud je přítomen element s indexy `[i, j, k, l]` , žádné další prvky nemohou mít tyto indexy.</span><span class="sxs-lookup"><span data-stu-id="82805-194">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="82805-195">Příklad</span><span class="sxs-lookup"><span data-stu-id="82805-195">Example</span></span> #######

<span data-ttu-id="82805-196">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="82805-196">This section is informative.</span></span>

<span data-ttu-id="82805-197">Následující objekt určuje Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="82805-197">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="82805-198">$ $ H = \frac12 \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} \Biggr (1,6 a ^ {\dagger} \_ {1; \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {1, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {3, \rho} a { \_ 2, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {2, \rho} a \_ {3, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6} \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} a \_ {2, \rho} a \_ {3, \sigma} $ $ $ $-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2. \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {1, \rho} a \_ {6, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3 , \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3, \rho} a \_ {1, \Rho} a \_ {6, \sigma}\Biggr) \\ , \textrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="82805-198">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

### <a name="initial-state-section"></a><span data-ttu-id="82805-199">Oddíl počáteční stav</span><span class="sxs-lookup"><span data-stu-id="82805-199">Initial State Section</span></span> ###

<span data-ttu-id="82805-200">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="82805-200">This section is normative.</span></span>

<span data-ttu-id="82805-201">`initial_state_suggestion`Objekt, jehož hodnota je pole JSON, určuje počáteční stavy, které mají zájem o zadaný Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="82805-201">The `initial_state_suggestion` object whose value is a JSON array specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="82805-202">Každá položka v hodnotě `initial_state_suggestion` vlastnosti musí být objekt JSON, který popisuje jeden stav, jak je popsáno ve zbývající části této části.</span><span class="sxs-lookup"><span data-stu-id="82805-202">Each item in the value of the `initial_state_suggestion` property MUST be a JSON object describing one quantum state, as described in the remainder of this section.</span></span>
<span data-ttu-id="82805-203">Ve zbývající části této části se pojem "stavový objekt" odkazuje na položku v hodnotě `initial_state_suggestion` vlastnosti objektu Broombridge.</span><span class="sxs-lookup"><span data-stu-id="82805-203">In the remainder of this section, the term "state object" will refer to an item in the value of the `initial_state_suggestion` property of the Broombridge object.</span></span>

#### <a name="state-object"></a><span data-ttu-id="82805-204">Stavový objekt</span><span class="sxs-lookup"><span data-stu-id="82805-204">State object</span></span> ####

<span data-ttu-id="82805-205">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="82805-205">This section is normative.</span></span>

<span data-ttu-id="82805-206">Každý objekt stavu musí mít `label` vlastnost obsahující řetězec.</span><span class="sxs-lookup"><span data-stu-id="82805-206">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="82805-207">Každý objekt stavu musí mít `method` vlastnost.</span><span class="sxs-lookup"><span data-stu-id="82805-207">Each state object MUST have a `method` property.</span></span> <span data-ttu-id="82805-208">Hodnota `method` vlastnosti musí být jedna z povolených hodnot uvedených v tabulce 3.</span><span class="sxs-lookup"><span data-stu-id="82805-208">The value of the `method` property MUST be one of the allowed values listed in Table 3.</span></span>
<span data-ttu-id="82805-209">Každý objekt stavu může mít vlastnost, `energy` jejíž hodnota musí být jednoduchý objekt množství.</span><span class="sxs-lookup"><span data-stu-id="82805-209">Each state object MAY have a property `energy` whose value MUST be a simple quantity object.</span></span>

<span data-ttu-id="82805-210">Pokud `method` je hodnota vlastnosti `sparse_multi_configurational` , objekt stavu musí mít `superposition` vlastnost obsahující pole základních stavů a jejich nenormalizované amplitudy.</span><span class="sxs-lookup"><span data-stu-id="82805-210">If the value of the `method` property is `sparse_multi_configurational`, the state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="82805-211">Například počáteční stavy $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) + 0,2 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \uparrow}a ^ {\dagger} \_ {2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0,2 | ^ 2}} \ket {0} , kde $ \ket{E} $ má energii $0,987 \textrm{ha} $, jsou reprezentovány</span><span class="sxs-lookup"><span data-stu-id="82805-211">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0}, $$ where $\ket{E}$ has energy $0.987 \textrm{Ha}$, are represented by</span></span>
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

<span data-ttu-id="82805-212">Pokud `method` je hodnota vlastnosti `unitary_coupled_cluster` , objekt stavu musí mít `cluster_operator` vlastnost, jejíž hodnota je objekt JSON.</span><span class="sxs-lookup"><span data-stu-id="82805-212">If the value of the `method` property is `unitary_coupled_cluster`, the state object MUST have a `cluster_operator` property whose value is a JSON object.</span></span>
<span data-ttu-id="82805-213">Objekt JSON musí mít vlastnost, `reference_state` jejíž hodnota je základní stav.</span><span class="sxs-lookup"><span data-stu-id="82805-213">The JSON object MUST have a `reference_state` property whose value is a basis state.</span></span>
<span data-ttu-id="82805-214">Objekt JSON může mít vlastnost, `one_body_amplitudes` jejíž hodnota je pole operátorů clusteru s jedním tělem a jejich amplitudy.</span><span class="sxs-lookup"><span data-stu-id="82805-214">The JSON object MAY have a `one_body_amplitudes` property whose value is an array of one-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="82805-215">Objekt JSON může mít vlastnost, `two_body_amplitudes` jejíž hodnota je pole operátorů clusteru se dvěma body a jejich amplitudy.</span><span class="sxs-lookup"><span data-stu-id="82805-215">The JSON object MAY have a `two_body_amplitudes` property whose value is an array of two-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="82805-216">obsahující pole základních stavů a jejich nenormalizované amplitudy.</span><span class="sxs-lookup"><span data-stu-id="82805-216">containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="82805-217">Například stav $ $ \ket{\Text{Reference}} = (a ^ {\dagger} \_ {1; \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} , $ $</span><span class="sxs-lookup"><span data-stu-id="82805-217">For example, the state $$ \ket{\text{reference}}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0}, $$</span></span>

<span data-ttu-id="82805-218">$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\Text{reference}}, $ $</span><span class="sxs-lookup"><span data-stu-id="82805-218">$$ \ket{\text{UCCSD}}=e^{T-T^\dagger}\ket{\text{reference}}, $$</span></span>

<span data-ttu-id="82805-219">$ $ T = 0,1 a ^ {\dagger} \_ {3, \uparrow}a \_ {2, \downarrow} + 0,2 a ^ {\dagger} \_ {2, \uparrow}a \_ {2, \downarrow}-0,3 a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \downarrow}a { \_ 3, \uparrow}a \_ {2, \downarrow} $ $ je reprezentován</span><span class="sxs-lookup"><span data-stu-id="82805-219">$$ T = 0.1 a^{\dagger}\_{3,\uparrow}a\_{2,\downarrow} + 0.2 a^{\dagger}\_{2,\uparrow}a\_{2,\downarrow} - 0.3 a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\downarrow}a\_{3,\uparrow}a\_{2,\downarrow} $$ is represented by</span></span>
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

#### <a name="basis-set-object"></a><span data-ttu-id="82805-220">Základní objekt sady</span><span class="sxs-lookup"><span data-stu-id="82805-220">Basis Set Object</span></span> ####

<span data-ttu-id="82805-221">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="82805-221">This section is normative.</span></span>

<span data-ttu-id="82805-222">Každý objekt popisu problému může mít `basis_set` vlastnost.</span><span class="sxs-lookup"><span data-stu-id="82805-222">Each problem description object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="82805-223">Je-li k dispozici, hodnota `basis_set` vlastnosti musí být objekt se dvěma vlastnostmi `type` a `name` .</span><span class="sxs-lookup"><span data-stu-id="82805-223">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="82805-224">Základní funkce identifikované hodnotou `basis_set` vlastnosti musí být reálné.</span><span class="sxs-lookup"><span data-stu-id="82805-224">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="82805-225">Předpokladem, že všechny základní funkce jsou reálné, mohou být v budoucích verzích této specifikace uvolněny.</span><span class="sxs-lookup"><span data-stu-id="82805-225">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="82805-226">Tabulky a seznamy</span><span class="sxs-lookup"><span data-stu-id="82805-226">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="82805-227">Tabulka 1.</span><span class="sxs-lookup"><span data-stu-id="82805-227">Table 1.</span></span> <span data-ttu-id="82805-228">Povolené fyzické jednotky</span><span class="sxs-lookup"><span data-stu-id="82805-228">Allowed Physical Units</span></span> ###

<span data-ttu-id="82805-229">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="82805-229">This section is normative.</span></span>

<span data-ttu-id="82805-230">Libovolný řetězec určující jednotku musí být jeden z následujících:</span><span class="sxs-lookup"><span data-stu-id="82805-230">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="82805-231">Analyzátory a producenti musí považovat následující jednoduché objekty množství jako ekvivalentní:</span><span class="sxs-lookup"><span data-stu-id="82805-231">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="82805-232">Tabulka 2.</span><span class="sxs-lookup"><span data-stu-id="82805-232">Table 2.</span></span> <span data-ttu-id="82805-233">Povolené konvence indexu</span><span class="sxs-lookup"><span data-stu-id="82805-233">Allowed Index Conventions</span></span> ###

<span data-ttu-id="82805-234">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="82805-234">This section is normative.</span></span>

<span data-ttu-id="82805-235">Libovolný řetězec určující konvenci indexu musí být jeden z následujících:</span><span class="sxs-lookup"><span data-stu-id="82805-235">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="82805-236">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="82805-236">This section is informative.</span></span>

<span data-ttu-id="82805-237">V budoucích verzích této specifikace se můžou zavést další konvence indexu.</span><span class="sxs-lookup"><span data-stu-id="82805-237">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="82805-238">Výklad konvencí indexů</span><span class="sxs-lookup"><span data-stu-id="82805-238">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="82805-239">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="82805-239">This section is informative.</span></span>

### <a name="table-3-allowed-state-methods"></a><span data-ttu-id="82805-240">Tabulka 3.</span><span class="sxs-lookup"><span data-stu-id="82805-240">Table 3.</span></span> <span data-ttu-id="82805-241">Povolené metody stavu</span><span class="sxs-lookup"><span data-stu-id="82805-241">Allowed State methods</span></span> ###

<span data-ttu-id="82805-242">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="82805-242">This section is normative.</span></span>

<span data-ttu-id="82805-243">Libovolný řetězec určující metodu stavu musí být jedna z následujících:</span><span class="sxs-lookup"><span data-stu-id="82805-243">Any string specifying a state method MUST be one of the following:</span></span>

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

<span data-ttu-id="82805-244">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="82805-244">This section is informative.</span></span>

<span data-ttu-id="82805-245">V budoucích verzích této specifikace mohou být zavedeny další metody stavu.</span><span class="sxs-lookup"><span data-stu-id="82805-245">Additional state methods may be introduced in future versions of this specification.</span></span>
