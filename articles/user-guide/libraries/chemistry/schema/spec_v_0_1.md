---
title: Specifikace schématu Broombridge (ver 0,1)
description: Podrobnosti o specifikacích pro schéma Broombridgech nech nákladů pro schéma v 0,1 pro knihovnu Microsoft pro složení nákladů
author: cgranade
ms.author: chgranad
ms.date: 10/17/2018
ms.topic: conceptual
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0a306f59a823e76ba0518d023a41f1f9d5670e7a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858199"
---
# <a name="broombridge-specification-v01"></a><span data-ttu-id="b86c8-103">Specifikace Broombridge v 0,1</span><span class="sxs-lookup"><span data-stu-id="b86c8-103">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="b86c8-104">Klíčová slova "musí", "nesmí", "požadováno", "musí", "nesmí", "by" neměla "," by "neměla být", "doporučeno", "by" měly být "nepovinné" v tomto dokumentu budou interpretována tak, jak je popsáno v [dokumentu RFC 2119](https://tools.ietf.org/html/rfc2119).</span><span class="sxs-lookup"><span data-stu-id="b86c8-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="b86c8-105">Jakýkoli postranní panel s nadpisy "Poznámka", "informace" nebo "upozornění" jsou informativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="b86c8-106">Úvod</span><span class="sxs-lookup"><span data-stu-id="b86c8-106">Introduction</span></span> ##

<span data-ttu-id="b86c8-107">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-107">This section is informative.</span></span>

<span data-ttu-id="b86c8-108">Dokumenty Broombridge jsou určené ke sdělování instancí problémů simulace v chemii doby zpracování za použití simulace využití a programování sady nástrojů.</span><span class="sxs-lookup"><span data-stu-id="b86c8-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="b86c8-109">Serializace</span><span class="sxs-lookup"><span data-stu-id="b86c8-109">Serialization</span></span> ##

<span data-ttu-id="b86c8-110">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-110">This section is normative.</span></span>

<span data-ttu-id="b86c8-111">Dokument Broombridge musí být serializován jako [dokument YAML 1,2](http://yaml.org/spec/) REPREZENTUJÍCÍ objekt JSON, jak je popsáno v [dokumentu RFC 4627](https://tools.ietf.org/html/rfc4627) oddíl 2,2.</span><span class="sxs-lookup"><span data-stu-id="b86c8-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="b86c8-112">Objekt serializovaný do YAML musí mít vlastnost `"$schema"` , jejíž hodnota je `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"` , a musí být platný podle konceptu schématu JSON-06 specifikace [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="b86c8-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="b86c8-113">Pro zbytek této specifikace "objekt Broombridge" bude odkazovat na objekt JSON deserializaci z dokumentu Broombridge YAML.</span><span class="sxs-lookup"><span data-stu-id="b86c8-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="b86c8-114">Pokud není výslovně uvedeno jinak, objekty nesmí mít další vlastnosti nad rámec těch, které jsou výslovně uvedené v tomto dokumentu.</span><span class="sxs-lookup"><span data-stu-id="b86c8-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="b86c8-115">Další definice</span><span class="sxs-lookup"><span data-stu-id="b86c8-115">Additional Definitions</span></span> ##

<span data-ttu-id="b86c8-116">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="b86c8-117">Množství objektů</span><span class="sxs-lookup"><span data-stu-id="b86c8-117">Quantity Objects</span></span> ###

<span data-ttu-id="b86c8-118">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-118">This section is normative.</span></span>

<span data-ttu-id="b86c8-119">_Objekt množství_ je objekt JSON a musí mít vlastnost, `units` jejíž hodnota je jedna z povolených hodnot uvedených v tabulce 1.</span><span class="sxs-lookup"><span data-stu-id="b86c8-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="b86c8-120">Objekt množství je _jednoduchý objekt množství_ , pokud má `value` kromě jeho vlastnosti jednu vlastnost `units` .</span><span class="sxs-lookup"><span data-stu-id="b86c8-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="b86c8-121">Hodnota `value` vlastnosti musí být číslo.</span><span class="sxs-lookup"><span data-stu-id="b86c8-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="b86c8-122">Objekt množství je objekt s _ohraničeným množstvím_ , pokud má vlastnosti `lower` a `upper` kromě jeho `units` Vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="b86c8-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="b86c8-123">Hodnoty `lower` `upper` vlastností a musí být čísla.</span><span class="sxs-lookup"><span data-stu-id="b86c8-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="b86c8-124">Objekt vázaného množství může mít vlastnost, `value` jejíž hodnota je číslo.</span><span class="sxs-lookup"><span data-stu-id="b86c8-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="b86c8-125">Objekt množství je objekt množství _zhuštěného pole_ , pokud obsahuje vlastnost `format` a vlastnost `values` kromě jeho `units` Vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="b86c8-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="b86c8-126">Hodnota `format` musí být řetězec `sparse` .</span><span class="sxs-lookup"><span data-stu-id="b86c8-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="b86c8-127">Hodnotou `values` vlastnosti musí být pole.</span><span class="sxs-lookup"><span data-stu-id="b86c8-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="b86c8-128">Každý prvek `values` musí být pole reprezentující indexy a hodnotu množství zhuštěného pole.</span><span class="sxs-lookup"><span data-stu-id="b86c8-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="b86c8-129">Indexy pro každý prvek objektu množství zhuštěného pole musí být jedinečné v celém objektu množství zhuštěného pole.</span><span class="sxs-lookup"><span data-stu-id="b86c8-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="b86c8-130">Pokud je index přítomen s hodnotou `0` , analyzátor musí zacházet s objektem množství zhuštěného pole stejně jako objekt množství zhuštěného pole, ve kterém index není přítomen vůbec.</span><span class="sxs-lookup"><span data-stu-id="b86c8-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="b86c8-131">Objekt množství musí být buď</span><span class="sxs-lookup"><span data-stu-id="b86c8-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="b86c8-132">jednoduchý objekt množství,</span><span class="sxs-lookup"><span data-stu-id="b86c8-132">a simple quantity object,</span></span>
- <span data-ttu-id="b86c8-133">objekt s ohraničeným množstvím nebo</span><span class="sxs-lookup"><span data-stu-id="b86c8-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="b86c8-134">objekt množství zhuštěného pole</span><span class="sxs-lookup"><span data-stu-id="b86c8-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="b86c8-135">Příklady</span><span class="sxs-lookup"><span data-stu-id="b86c8-135">Examples</span></span> ###

<span data-ttu-id="b86c8-136">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-136">This section is informative.</span></span>

<span data-ttu-id="b86c8-137">Jednoduché množství představující $1.9844146837 \, \mathrm{ha} $:</span><span class="sxs-lookup"><span data-stu-id="b86c8-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="b86c8-138">Ohraničené množství představující jednotnou distribuci v intervalu $ [-7,-6] \, \mathrm{ha} $:</span><span class="sxs-lookup"><span data-stu-id="b86c8-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="b86c8-139">Následuje množství zhuštěného pole s elementem `[1, 2]` , který se rovná `hello` a element `[3, 4]` se rovná `world` :</span><span class="sxs-lookup"><span data-stu-id="b86c8-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="b86c8-140">Formátovat oddíl</span><span class="sxs-lookup"><span data-stu-id="b86c8-140">Format Section</span></span> ##

<span data-ttu-id="b86c8-141">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-141">This section is normative.</span></span>

<span data-ttu-id="b86c8-142">Objekt Broombridge musí mít vlastnost, `format` jejíž hodnota je objekt JSON, který má nazvaná jednu vlastnost `version` .</span><span class="sxs-lookup"><span data-stu-id="b86c8-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="b86c8-143">`version`Vlastnost musí mít hodnotu `"0.1"` .</span><span class="sxs-lookup"><span data-stu-id="b86c8-143">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="b86c8-144">Příklad</span><span class="sxs-lookup"><span data-stu-id="b86c8-144">Example</span></span> ###

<span data-ttu-id="b86c8-145">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="b86c8-146">Oddíl integrálních sad</span><span class="sxs-lookup"><span data-stu-id="b86c8-146">Integral Sets Section</span></span> ##

<span data-ttu-id="b86c8-147">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-147">This section is normative.</span></span>

<span data-ttu-id="b86c8-148">Objekt Broombridge musí mít vlastnost, `integral_sets` jejíž hodnota je pole JSON.</span><span class="sxs-lookup"><span data-stu-id="b86c8-148">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="b86c8-149">Každá položka v hodnotě `integral_sets` vlastnosti musí být objekt JSON, který popisuje jednu sadu integrálních objektů, jak je popsáno ve zbývající části této části.</span><span class="sxs-lookup"><span data-stu-id="b86c8-149">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="b86c8-150">Ve zbývající části této části se pojem "objekt" integrální sady "odkazuje na položku v hodnotě `integral_sets` vlastnosti objektu Broombridge.</span><span class="sxs-lookup"><span data-stu-id="b86c8-150">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="b86c8-151">Každý objekt integrální sady musí mít vlastnost, `metadata` jejíž hodnota je objekt JSON.</span><span class="sxs-lookup"><span data-stu-id="b86c8-151">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="b86c8-152">Hodnota `metadata` může být prázdný objekt JSON (tj. `{}` ) nebo může obsahovat další vlastnosti definované implementací.</span><span class="sxs-lookup"><span data-stu-id="b86c8-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="b86c8-153">Oddíl Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="b86c8-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="b86c8-154">Přehled</span><span class="sxs-lookup"><span data-stu-id="b86c8-154">Overview</span></span> ####

<span data-ttu-id="b86c8-155">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-155">This section is informative.</span></span>

<span data-ttu-id="b86c8-156">`hamiltonian`Vlastnost každého objektu integrální sady popisuje Hamiltonian pro konkrétní chemii. 2. část je uvedena jako zhuštěná pole reálných čísel.</span><span class="sxs-lookup"><span data-stu-id="b86c8-156">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="b86c8-157">Hamiltonian operátory popsané každým objektem integrální sady mají formu.</span><span class="sxs-lookup"><span data-stu-id="b86c8-157">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="b86c8-158">$ $ H = \sum \_ \{ i, j \} \sum \_ {\sigma\in \\ {\uparrow, \downarrow \\ }} h \_ \{ IJ \} a ^ \{ \dagger \} \_ {i, \sigma} a \_ {j, \sigma} + \frac {1} {2} \sum \_ \{ i, j, k, l \} \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} H \_ {IJKL} a ^ \dagger \_ {i, \sigma} a ^ \dagger \_ {k, \rho} a \_ {l, \rho} a \_ {j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="b86c8-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="b86c8-159">Tady $h _ {IJKL} = (IJ | kl) $ v konvenci Mulliken.</span><span class="sxs-lookup"><span data-stu-id="b86c8-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="b86c8-160">Pro přehlednost je pojem jednorázový</span><span class="sxs-lookup"><span data-stu-id="b86c8-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="b86c8-161">$ $ h_ {IJ} = \int {\mathrm d} x \psi ^ \* \_ i (x) \left (\frac {1} {2} \nabla ^ 2 + \sum \_ {A} \frac{Z \_ a} {| x-x \_ A |}  \right) \psi \_ j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="b86c8-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="b86c8-162">a dva elektronické podmínky jsou</span><span class="sxs-lookup"><span data-stu-id="b86c8-162">and the two-electron term is</span></span>

<span data-ttu-id="b86c8-163">$ $ h \_ \{ IJKL \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} (x \_ 2) \psi \_ l (x \_ 2).</span><span class="sxs-lookup"><span data-stu-id="b86c8-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="b86c8-164">Jak je uvedeno v našem popisu [ `basis_set` vlastnosti](#basis-set-object) každého elementu `integral_sets` vlastnosti, dále explicitně předpokládáme, že použité základní funkce jsou reálné.</span><span class="sxs-lookup"><span data-stu-id="b86c8-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="b86c8-165">To umožňuje použít následující symmetries mezi podmínkami pro komprimaci reprezentace Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="b86c8-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="b86c8-166">$ $ h_ {IJKL} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = H_ {lkij} = h_ {LKJI}.</span><span class="sxs-lookup"><span data-stu-id="b86c8-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="b86c8-167">Obsah</span><span class="sxs-lookup"><span data-stu-id="b86c8-167">Contents</span></span> ####

<span data-ttu-id="b86c8-168">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-168">This section is normative.</span></span>

<span data-ttu-id="b86c8-169">Každá celočíselná sada musí mít vlastnost, `hamiltonian` jejíž hodnota je objekt JSON.</span><span class="sxs-lookup"><span data-stu-id="b86c8-169">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="b86c8-170">Hodnota `hamiltonian` vlastnosti je označována jako objekt Hamiltonian a musí mít vlastnosti, `one_electron_integrals` `two_electron_integrals` jak je popsáno ve zbývající části této části.</span><span class="sxs-lookup"><span data-stu-id="b86c8-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="b86c8-171">Objekt Hamiltonian může mít také vlastnost `particle_hole_representation` .</span><span class="sxs-lookup"><span data-stu-id="b86c8-171">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="b86c8-172">Je-li k dispozici, hodnota `particle_hole_representation` musí následovat po formátu popsaném ve zbývající části této části.</span><span class="sxs-lookup"><span data-stu-id="b86c8-172">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="b86c8-173">Objekt One-Electron integrály</span><span class="sxs-lookup"><span data-stu-id="b86c8-173">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="b86c8-174">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-174">This section is normative.</span></span>

<span data-ttu-id="b86c8-175">`one_electron_integrals`Vlastnost objektu HAMILTONIAN musí být množstvím zhuštěného pole, jehož indexy jsou dvě celá čísla a jejichž hodnoty jsou čísla.</span><span class="sxs-lookup"><span data-stu-id="b86c8-175">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="b86c8-176">Každý výraz musí mít indexy `[i, j]` , kde `i >= j` .</span><span class="sxs-lookup"><span data-stu-id="b86c8-176">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="b86c8-177">ZNAČTE To odráží symetrii, který $h _ {IJ} = h_ {ji} $, což je podsekvence faktu, že Hamiltonian je Hermitian.</span><span class="sxs-lookup"><span data-stu-id="b86c8-177">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="b86c8-178">Příklad</span><span class="sxs-lookup"><span data-stu-id="b86c8-178">Example</span></span> ######

<span data-ttu-id="b86c8-179">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-179">This section is informative.</span></span>

<span data-ttu-id="b86c8-180">Následující množství zhuštěného pole představuje Hamiltonian $ $ H = \left (-5,0 (a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {1, \downarrow}) + 0,17 (a ^ \{ \dagger \} \_ {2, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {2, \uparrow} + a ^ \{ \dagger \} \_ {2, \downarrow} a \_ {1, \downarrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {2, \downarrow}) \right) \\ , \mathrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="b86c8-180">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="b86c8-181">Broombridge používá indexování založené na 1.</span><span class="sxs-lookup"><span data-stu-id="b86c8-181">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="b86c8-182">Objekt Two-Electron integrály</span><span class="sxs-lookup"><span data-stu-id="b86c8-182">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="b86c8-183">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-183">This section is normative.</span></span>

<span data-ttu-id="b86c8-184">`two_electron_integrals`Vlastnost objektu HAMILTONIAN musí být množstvím zhuštěného pole s jednou další vlastností nazvanou `index_convention` .</span><span class="sxs-lookup"><span data-stu-id="b86c8-184">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="b86c8-185">Každý prvek hodnoty `two_electron_integrals` musí mít čtyři indexy.</span><span class="sxs-lookup"><span data-stu-id="b86c8-185">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="b86c8-186">Každá `two_electron_integrals` vlastnost musí mít `index_convention` vlastnost.</span><span class="sxs-lookup"><span data-stu-id="b86c8-186">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="b86c8-187">Hodnota `index_convention` vlastnosti musí být jedna z povolených hodnot uvedených v tabulce 1.</span><span class="sxs-lookup"><span data-stu-id="b86c8-187">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="b86c8-188">Pokud `index_convention` je hodnota `mulliken` , potom pro každý prvek `two_electron_integrals` množství zhuštěného pole, analyzátor načítající dokument Broombridge musí vytvořit instanci Hamiltonianho výrazu, který se rovná druhému operátoru $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $, kde $i $, $j $, $k $ a $l $ musí být celá čísla v rozsahu od 1 do počtu Electrons zadaného `n_electrons` vlastností objektu integrální sady a kde $h _ {i, j, k, l} $ je prvek `[i, j, k, l, h(i, j, k, l)]` množství zhuštěného pole.</span><span class="sxs-lookup"><span data-stu-id="b86c8-188">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="b86c8-189">Symmetries</span><span class="sxs-lookup"><span data-stu-id="b86c8-189">Symmetries</span></span> ######

<span data-ttu-id="b86c8-190">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-190">This section is normative.</span></span>

<span data-ttu-id="b86c8-191">Pokud `index_convention` `two_electron_integrals` je vlastnost objektu rovna `mulliken` , pak pokud je přítomen element s indexy `[i, j, k, l]` , následující indexy nesmí být přítomny, pokud nejsou rovny `[i, j, k, l]` :</span><span class="sxs-lookup"><span data-stu-id="b86c8-191">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="b86c8-192">Vzhledem k tomu `index_convention` , že vlastnost je objekt zhuštěného množství, žádné indexy nelze opakovat na různých prvcích.</span><span class="sxs-lookup"><span data-stu-id="b86c8-192">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="b86c8-193">Konkrétně, pokud je přítomen element s indexy `[i, j, k, l]` , žádné další prvky nemohou mít tyto indexy.</span><span class="sxs-lookup"><span data-stu-id="b86c8-193">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="b86c8-194">Příklad</span><span class="sxs-lookup"><span data-stu-id="b86c8-194">Example</span></span> #######

<span data-ttu-id="b86c8-195">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-195">This section is informative.</span></span>

<span data-ttu-id="b86c8-196">Následující objekt určuje Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="b86c8-196">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="b86c8-197">$ $ H = \frac12 \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} \Biggr (1,6 a ^ {\dagger} \_ {1; \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {1, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {3, \rho} a { \_ 2, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {2, \rho} a \_ {3, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6} \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} a \_ {2, \rho} a \_ {3, \sigma} $ $ $ $-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2. \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {1, \rho} a \_ {6, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3 , \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3, \rho} a \_ {1, \Rho} a \_ {6, \sigma}\Biggr) \\ , \textrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="b86c8-197">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

##### <a name="particlehole-representation-object"></a><span data-ttu-id="b86c8-198">Částic – objekt reprezentace otvoru</span><span class="sxs-lookup"><span data-stu-id="b86c8-198">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="b86c8-199">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-199">This section is normative.</span></span>

<span data-ttu-id="b86c8-200">Objekt reprezentace částic určuje, zda jsou uložené integrály definovány s ohledem na otvor v podobě otvorů a Annihilation, popisujících excitations od používaného referenčního stavu, jako je Hartree – Fock stav.</span><span class="sxs-lookup"><span data-stu-id="b86c8-200">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="b86c8-201">Objekt je nepovinný.</span><span class="sxs-lookup"><span data-stu-id="b86c8-201">The object is OPTIONAL.</span></span>
<span data-ttu-id="b86c8-202">Pokud objekt není zadán, bude Hamiltonian interpretován tak, jak není zadáno v vyjádření částic.</span><span class="sxs-lookup"><span data-stu-id="b86c8-202">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="b86c8-203">Je-li k dispozici, hodnota `particle_hole_representation` musí být objekt množství zhuštěného pole, jehož indexy jsou čtyři celá čísla a jejichž hodnoty jsou číslo a řetězec.</span><span class="sxs-lookup"><span data-stu-id="b86c8-203">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="b86c8-204">Část řetězce hodnoty každého elementu musí obsahovat pouze znaky `'+'` a, `'-'` které určují, zda daný faktor v daném termínu je operátor vytvoření nebo Annihilation v vyjádření částic – díra.</span><span class="sxs-lookup"><span data-stu-id="b86c8-204">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="b86c8-205">Například `"-+++"` mikroreaguje na díru vytvořenou v lokalitě $i $ a částice, které jsou vytvářeny v lokalitách $j, k $ a $l $.</span><span class="sxs-lookup"><span data-stu-id="b86c8-205">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="b86c8-206">Jako hodnota `particle_hole_representation` je objekt množství zhuštěného pole, `unit` `format` musí být zadány vlastnosti a.</span><span class="sxs-lookup"><span data-stu-id="b86c8-206">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="b86c8-207">Přijatelné jednotky jsou uvedeny v tabulce 1.</span><span class="sxs-lookup"><span data-stu-id="b86c8-207">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="b86c8-208">`format`Vlastnost je povinná a označuje, zda jsou Hamiltonian koeficienty zadány jako husté nebo zhuštěné pole.</span><span class="sxs-lookup"><span data-stu-id="b86c8-208">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="b86c8-209">V aktuální verzi jsou podporována pouze zhuštěná pole s výkladem, že všechny neurčené prvky jsou $0 $, ale budoucí verze mohou přidat podporu pro další hodnoty `format` Vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="b86c8-209">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="b86c8-210">Oddíl počáteční stav</span><span class="sxs-lookup"><span data-stu-id="b86c8-210">Initial State Section</span></span> ###

<span data-ttu-id="b86c8-211">Objekt initial_state_suggestion Určuje počáteční stavy, které mají zájem na zadaný Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="b86c8-211">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="b86c8-212">Tento objekt musí být pole `state` objektů JSON.</span><span class="sxs-lookup"><span data-stu-id="b86c8-212">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="b86c8-213">Stavový objekt</span><span class="sxs-lookup"><span data-stu-id="b86c8-213">State object</span></span> ####

<span data-ttu-id="b86c8-214">Každý stav představuje nadpozici obsazené orbitals.</span><span class="sxs-lookup"><span data-stu-id="b86c8-214">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="b86c8-215">Každý objekt stavu musí mít `label` vlastnost obsahující řetězec.</span><span class="sxs-lookup"><span data-stu-id="b86c8-215">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="b86c8-216">Každý objekt stavu musí mít `superposition` vlastnost obsahující pole základních stavů a jejich nenormalizované amplitudy.</span><span class="sxs-lookup"><span data-stu-id="b86c8-216">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="b86c8-217">Například počáteční stavy $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) + 0,2 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \uparrow}a ^ {\dagger} \_ {2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0,2 | ^ 2}} \ket {0} $ $ jsou reprezentovány</span><span class="sxs-lookup"><span data-stu-id="b86c8-217">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
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

#### <a name="basis-set-object"></a><span data-ttu-id="b86c8-218">Základní objekt sady</span><span class="sxs-lookup"><span data-stu-id="b86c8-218">Basis Set Object</span></span> ####

<span data-ttu-id="b86c8-219">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-219">This section is normative.</span></span>

<span data-ttu-id="b86c8-220">Každý objekt integrální sady může mít `basis_set` vlastnost.</span><span class="sxs-lookup"><span data-stu-id="b86c8-220">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="b86c8-221">Je-li k dispozici, hodnota `basis_set` vlastnosti musí být objekt se dvěma vlastnostmi `type` a `name` .</span><span class="sxs-lookup"><span data-stu-id="b86c8-221">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="b86c8-222">Základní funkce identifikované hodnotou `basis_set` vlastnosti musí být reálné.</span><span class="sxs-lookup"><span data-stu-id="b86c8-222">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="b86c8-223">Předpokladem, že všechny základní funkce jsou reálné, mohou být v budoucích verzích této specifikace uvolněny.</span><span class="sxs-lookup"><span data-stu-id="b86c8-223">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="b86c8-224">Tabulky a seznamy</span><span class="sxs-lookup"><span data-stu-id="b86c8-224">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="b86c8-225">Tabulka 1.</span><span class="sxs-lookup"><span data-stu-id="b86c8-225">Table 1.</span></span> <span data-ttu-id="b86c8-226">Povolené fyzické jednotky</span><span class="sxs-lookup"><span data-stu-id="b86c8-226">Allowed Physical Units</span></span> ###

<span data-ttu-id="b86c8-227">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-227">This section is normative.</span></span>

<span data-ttu-id="b86c8-228">Libovolný řetězec určující jednotku musí být jeden z následujících:</span><span class="sxs-lookup"><span data-stu-id="b86c8-228">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="b86c8-229">Analyzátory a producenti musí považovat následující jednoduché objekty množství jako ekvivalentní:</span><span class="sxs-lookup"><span data-stu-id="b86c8-229">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="b86c8-230">Tabulka 2.</span><span class="sxs-lookup"><span data-stu-id="b86c8-230">Table 2.</span></span> <span data-ttu-id="b86c8-231">Povolené konvence indexu</span><span class="sxs-lookup"><span data-stu-id="b86c8-231">Allowed Index Conventions</span></span> ###

<span data-ttu-id="b86c8-232">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-232">This section is normative.</span></span>

<span data-ttu-id="b86c8-233">Libovolný řetězec určující konvenci indexu musí být jeden z následujících:</span><span class="sxs-lookup"><span data-stu-id="b86c8-233">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="b86c8-234">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-234">This section is informative.</span></span>

<span data-ttu-id="b86c8-235">V budoucích verzích této specifikace se můžou zavést další konvence indexu.</span><span class="sxs-lookup"><span data-stu-id="b86c8-235">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="b86c8-236">Výklad konvencí indexů</span><span class="sxs-lookup"><span data-stu-id="b86c8-236">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="b86c8-237">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="b86c8-237">This section is informative.</span></span>
