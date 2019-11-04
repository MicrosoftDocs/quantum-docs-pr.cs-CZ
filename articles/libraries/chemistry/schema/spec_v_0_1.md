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
# <a name="broombridge-specification-v01"></a><span data-ttu-id="0895f-102">Specifikace Broombridge v 0,1</span><span class="sxs-lookup"><span data-stu-id="0895f-102">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="0895f-103">Klíčová slova "musí", "nesmí", "požadováno", "musí", "nesmí", "by" neměla "," by "neměla být", "doporučeno", "by" měly být "nepovinné" v tomto dokumentu budou interpretována tak, jak je popsáno v [dokumentu RFC 2119](https://tools.ietf.org/html/rfc2119).</span><span class="sxs-lookup"><span data-stu-id="0895f-103">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="0895f-104">Jakýkoli postranní panel s nadpisy "Poznámka", "informace" nebo "upozornění" jsou informativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-104">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="0895f-105">Představení</span><span class="sxs-lookup"><span data-stu-id="0895f-105">Introduction</span></span> ##

<span data-ttu-id="0895f-106">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-106">This section is informative.</span></span>

<span data-ttu-id="0895f-107">Dokumenty Broombridge jsou určené ke sdělování instancí problémů simulace v chemii doby zpracování za použití simulace využití a programování sady nástrojů.</span><span class="sxs-lookup"><span data-stu-id="0895f-107">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="0895f-108">Serializace</span><span class="sxs-lookup"><span data-stu-id="0895f-108">Serialization</span></span> ##

<span data-ttu-id="0895f-109">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-109">This section is normative.</span></span>

<span data-ttu-id="0895f-110">Dokument Broombridge musí být serializován jako [dokument YAML 1,2](http://yaml.org/spec/) REPREZENTUJÍCÍ objekt JSON, jak je popsáno v [dokumentu RFC 4627](https://tools.ietf.org/html/rfc4627) oddíl 2,2.</span><span class="sxs-lookup"><span data-stu-id="0895f-110">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="0895f-111">Objekt serializovaný do YAML musí mít vlastnost `"$schema"` jejíž hodnota je `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`a musí být platný podle konceptu schématu JSON-06 specifikace [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="0895f-111">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="0895f-112">Pro zbytek této specifikace "objekt Broombridge" bude odkazovat na objekt JSON deserializaci z dokumentu Broombridge YAML.</span><span class="sxs-lookup"><span data-stu-id="0895f-112">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="0895f-113">Pokud není výslovně uvedeno jinak, objekty nesmí mít další vlastnosti nad rámec těch, které jsou výslovně uvedené v tomto dokumentu.</span><span class="sxs-lookup"><span data-stu-id="0895f-113">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="0895f-114">Další definice</span><span class="sxs-lookup"><span data-stu-id="0895f-114">Additional Definitions</span></span> ##

<span data-ttu-id="0895f-115">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-115">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="0895f-116">Množství objektů</span><span class="sxs-lookup"><span data-stu-id="0895f-116">Quantity Objects</span></span> ###

<span data-ttu-id="0895f-117">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-117">This section is normative.</span></span>

<span data-ttu-id="0895f-118">_Objekt množství_ je objekt JSON a musí mít vlastnost, `units` jejíž hodnota je jedna z povolených hodnot uvedených v tabulce 1.</span><span class="sxs-lookup"><span data-stu-id="0895f-118">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="0895f-119">Objekt množství je _jednoduchý objekt množství_ , pokud má jednu vlastnost `value` kromě vlastnosti `units`.</span><span class="sxs-lookup"><span data-stu-id="0895f-119">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="0895f-120">Hodnota vlastnosti `value` musí být číslo.</span><span class="sxs-lookup"><span data-stu-id="0895f-120">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="0895f-121">Objekt množství je objekt s _vazbou množství_ , pokud má vlastnosti `lower` a `upper` kromě jeho vlastnosti `units`.</span><span class="sxs-lookup"><span data-stu-id="0895f-121">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="0895f-122">Hodnoty vlastností `lower` a `upper` musí být čísla.</span><span class="sxs-lookup"><span data-stu-id="0895f-122">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="0895f-123">Objekt vázaného množství může mít vlastnost, `value` jejíž hodnota je číslo.</span><span class="sxs-lookup"><span data-stu-id="0895f-123">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="0895f-124">Objekt množství je objekt množství _zhuštěného pole_ , pokud má vlastnost `format` a vlastnost `values` kromě vlastnosti `units`.</span><span class="sxs-lookup"><span data-stu-id="0895f-124">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="0895f-125">Hodnota `format` musí být `sparse`řetězce.</span><span class="sxs-lookup"><span data-stu-id="0895f-125">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="0895f-126">Hodnota vlastnosti `values` musí být pole.</span><span class="sxs-lookup"><span data-stu-id="0895f-126">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="0895f-127">Každý prvek `values` musí být pole reprezentující indexy a hodnotu množství zhuštěného pole.</span><span class="sxs-lookup"><span data-stu-id="0895f-127">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="0895f-128">Indexy pro každý prvek objektu množství zhuštěného pole musí být jedinečné v celém objektu množství zhuštěného pole.</span><span class="sxs-lookup"><span data-stu-id="0895f-128">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="0895f-129">Pokud je index přítomen s hodnotou `0`, analyzátor musí zacházet s objektem množství zhuštěného pole stejně jako objekt množství zhuštěného pole, ve kterém index není přítomen vůbec.</span><span class="sxs-lookup"><span data-stu-id="0895f-129">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="0895f-130">Objekt množství musí být buď</span><span class="sxs-lookup"><span data-stu-id="0895f-130">A quantity object MUST either be</span></span>

- <span data-ttu-id="0895f-131">jednoduchý objekt množství,</span><span class="sxs-lookup"><span data-stu-id="0895f-131">a simple quantity object,</span></span>
- <span data-ttu-id="0895f-132">objekt s ohraničeným množstvím nebo</span><span class="sxs-lookup"><span data-stu-id="0895f-132">a bounded quantity object, or</span></span>
- <span data-ttu-id="0895f-133">objekt množství zhuštěného pole</span><span class="sxs-lookup"><span data-stu-id="0895f-133">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="0895f-134">Příklady</span><span class="sxs-lookup"><span data-stu-id="0895f-134">Examples</span></span> ###

<span data-ttu-id="0895f-135">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-135">This section is informative.</span></span>

<span data-ttu-id="0895f-136">Jednoduché množství představující $1.9844146837\,\mathrm{Ha} $:</span><span class="sxs-lookup"><span data-stu-id="0895f-136">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="0895f-137">Ohraničené množství představující jednotnou distribuci v intervalu $ [-7,-6]\,\mathrm{Ha} $:</span><span class="sxs-lookup"><span data-stu-id="0895f-137">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="0895f-138">Následuje množství zhuštěného pole s elementem `[1, 2]` rovno `hello` a elementu `[3, 4]` rovno `world`:</span><span class="sxs-lookup"><span data-stu-id="0895f-138">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="0895f-139">Formátovat oddíl</span><span class="sxs-lookup"><span data-stu-id="0895f-139">Format Section</span></span> ##

<span data-ttu-id="0895f-140">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-140">This section is normative.</span></span>

<span data-ttu-id="0895f-141">Objekt Broombridge musí mít vlastnost `format` jejíž hodnota je objekt JSON s jednou vlastností nazvanou `version`.</span><span class="sxs-lookup"><span data-stu-id="0895f-141">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="0895f-142">Vlastnost `version` musí mít hodnotu `"0.1"`.</span><span class="sxs-lookup"><span data-stu-id="0895f-142">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="0895f-143">Příklad:</span><span class="sxs-lookup"><span data-stu-id="0895f-143">Example</span></span> ###

<span data-ttu-id="0895f-144">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-144">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="0895f-145">Oddíl integrálních sad</span><span class="sxs-lookup"><span data-stu-id="0895f-145">Integral Sets Section</span></span> ##

<span data-ttu-id="0895f-146">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-146">This section is normative.</span></span>

<span data-ttu-id="0895f-147">Objekt Broombridge musí mít vlastnost, `integral_sets` jejíž hodnota je pole JSON.</span><span class="sxs-lookup"><span data-stu-id="0895f-147">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="0895f-148">Každá položka v hodnotě vlastnosti `integral_sets` musí být objekt JSON, který popisuje jednu sadu integrálních objektů, jak je popsáno ve zbývající části této části.</span><span class="sxs-lookup"><span data-stu-id="0895f-148">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="0895f-149">Ve zbývající části této části se pojem "objekt" integrální sady "odkazuje na položku v hodnotě vlastnosti `integral_sets` objektu Broombridge.</span><span class="sxs-lookup"><span data-stu-id="0895f-149">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="0895f-150">Každý objekt integrální sady musí mít vlastnost, `metadata` jejíž hodnota je objekt JSON.</span><span class="sxs-lookup"><span data-stu-id="0895f-150">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="0895f-151">Hodnota `metadata` může být prázdný objekt JSON (tj. `{}`) nebo může obsahovat další vlastnosti definované implementací.</span><span class="sxs-lookup"><span data-stu-id="0895f-151">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="0895f-152">Oddíl Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="0895f-152">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="0895f-153">Přehled</span><span class="sxs-lookup"><span data-stu-id="0895f-153">Overview</span></span> ####

<span data-ttu-id="0895f-154">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-154">This section is informative.</span></span>

<span data-ttu-id="0895f-155">Vlastnost `hamiltonian` každého objektu integrální sady popisuje Hamiltonian pro konkrétní chemii problému při práci s procesorem, a to tak, že uvádí své první a dvě tělo jako zhuštěná pole reálných čísel.</span><span class="sxs-lookup"><span data-stu-id="0895f-155">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="0895f-156">Hamiltonian operátory popsané každým objektem integrální sady mají formu.</span><span class="sxs-lookup"><span data-stu-id="0895f-156">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="0895f-157">$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} H\_\{IJ\} ^\{\dagger\}\_{i , \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} h\_{IJKL} a ^ \dagger\_{i , \sigma} a ^ \dagger\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="0895f-157">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="0895f-158">Tady $h _ {IJKL} = (IJ | kl) $ v konvenci Mulliken.</span><span class="sxs-lookup"><span data-stu-id="0895f-158">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="0895f-159">Pro přehlednost je pojem jednorázový</span><span class="sxs-lookup"><span data-stu-id="0895f-159">For clarity, the one-electron term is</span></span>

<span data-ttu-id="0895f-160">$ $ H_ {IJ} = \int {\mathrm d} x \psi ^ \*\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="0895f-160">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="0895f-161">a dva elektronické podmínky jsou</span><span class="sxs-lookup"><span data-stu-id="0895f-161">and the two-electron term is</span></span>

<span data-ttu-id="0895f-162">$ $ h\_\{IJKL\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psi\_l (x\_2).</span><span class="sxs-lookup"><span data-stu-id="0895f-162">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="0895f-163">Jak je uvedeno v našem popisu [vlastnosti`basis_set`](#basis-set-object) každého prvku `integral_sets` vlastnosti, explicitně předpokládáme, že použité základní funkce jsou reálné.</span><span class="sxs-lookup"><span data-stu-id="0895f-163">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="0895f-164">To umožňuje použít následující symmetries mezi podmínkami pro komprimaci reprezentace Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="0895f-164">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="0895f-165">$ $ H_ {IJKL} = H_ {ijlk} = H_ {jikl} = H_ {jilk} = H_ {klij} = H_ {klji} = H_ {lkij} = H_ {LKJI}.</span><span class="sxs-lookup"><span data-stu-id="0895f-165">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="0895f-166">Obsah</span><span class="sxs-lookup"><span data-stu-id="0895f-166">Contents</span></span> ####

<span data-ttu-id="0895f-167">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-167">This section is normative.</span></span>

<span data-ttu-id="0895f-168">Každá celočíselná sada musí mít vlastnost, `hamiltonian` jejíž hodnota je objekt JSON.</span><span class="sxs-lookup"><span data-stu-id="0895f-168">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="0895f-169">Hodnota vlastnosti `hamiltonian` je označována jako objekt Hamiltonian a musí mít `one_electron_integrals` vlastnosti a `two_electron_integrals`, jak je popsáno ve zbývající části této části.</span><span class="sxs-lookup"><span data-stu-id="0895f-169">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="0895f-170">Objekt Hamiltonian může mít také vlastnost `particle_hole_representation`.</span><span class="sxs-lookup"><span data-stu-id="0895f-170">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="0895f-171">Je-li k dispozici, hodnota `particle_hole_representation` musí odpovídat formátu popsanému ve zbývající části této části.</span><span class="sxs-lookup"><span data-stu-id="0895f-171">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="0895f-172">Objekt s jedním elektronovým integrálem</span><span class="sxs-lookup"><span data-stu-id="0895f-172">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="0895f-173">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-173">This section is normative.</span></span>

<span data-ttu-id="0895f-174">Vlastnost `one_electron_integrals` objektu Hamiltonian musí být množstvím zhuštěného pole, jehož indexy jsou dvě celá čísla a jejichž hodnoty jsou čísla.</span><span class="sxs-lookup"><span data-stu-id="0895f-174">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="0895f-175">Každý termín musí mít indexy `[i, j]`, kde `i >= j`.</span><span class="sxs-lookup"><span data-stu-id="0895f-175">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="0895f-176">ZNAČTE To odráží symetrii, který $h _ {IJ} = H_ {ji} $, což je podsekvence faktu, že Hamiltonian je Hermitian.</span><span class="sxs-lookup"><span data-stu-id="0895f-176">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="0895f-177">Příklad:</span><span class="sxs-lookup"><span data-stu-id="0895f-177">Example</span></span> ######

<span data-ttu-id="0895f-178">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-178">This section is informative.</span></span>

<span data-ttu-id="0895f-179">Následující množství zhuštěného pole představuje Hamiltonian $ $ H = \left (-5,0 (a ^\{\dagger\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1 , \downarrow}) + 0,17 (a ^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 , \downarrow} a\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{2, \downarrow}) \right)\\, \mathrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="0895f-179">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="0895f-180">Broombridge používá indexování založené na 1.</span><span class="sxs-lookup"><span data-stu-id="0895f-180">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="0895f-181">Objekt dvoumístné integrály</span><span class="sxs-lookup"><span data-stu-id="0895f-181">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="0895f-182">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-182">This section is normative.</span></span>

<span data-ttu-id="0895f-183">Vlastnost `two_electron_integrals` objektu Hamiltonian musí být množstvím zhuštěného pole s jednou další vlastností nazvanou `index_convention`.</span><span class="sxs-lookup"><span data-stu-id="0895f-183">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="0895f-184">Každý prvek hodnoty `two_electron_integrals` musí mít čtyři indexy.</span><span class="sxs-lookup"><span data-stu-id="0895f-184">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="0895f-185">Každá vlastnost `two_electron_integrals` musí mít vlastnost `index_convention`.</span><span class="sxs-lookup"><span data-stu-id="0895f-185">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="0895f-186">Hodnota vlastnosti `index_convention` musí být jedna z povolených hodnot uvedených v tabulce 1.</span><span class="sxs-lookup"><span data-stu-id="0895f-186">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="0895f-187">Pokud je hodnota `index_convention` `mulliken`, pak pro každý prvek `two_electron_integrals` množství zhuštěného pole musí být analyzátorem načítání dokumentu Broombridge vytvořen Hamiltonian výraz, který se rovná dvěma elektronům, $h _ {i, j, k, l} a ^ \dagger_i a ^ \dagger_j a_k a_l $ , kde $i $, $j $, $k $, a $l $, musí být celá čísla v rozsahu od 1 do počtu Electrons určených vlastností `n_electrons` objektu integrální sady a kde $h _ {i, j, k, l} $ je prvek `[i, j, k, l, h(i, j, k, l)]` množství zhuštěného pole.</span><span class="sxs-lookup"><span data-stu-id="0895f-187">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="0895f-188">Symmetries</span><span class="sxs-lookup"><span data-stu-id="0895f-188">Symmetries</span></span> ######

<span data-ttu-id="0895f-189">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-189">This section is normative.</span></span>

<span data-ttu-id="0895f-190">Pokud je vlastnost `index_convention` objektu `two_electron_integrals` rovna hodnotě `mulliken`, pak pokud je přítomen element s indexy `[i, j, k, l]`, nesmí být následující indexy přítomny, pokud nejsou rovny `[i, j, k, l]`:</span><span class="sxs-lookup"><span data-stu-id="0895f-190">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="0895f-191">Vzhledem k tomu, že vlastnost `index_convention` je objekt zhuštěného množství, nemohou být žádné indexy opakovány na různých prvcích.</span><span class="sxs-lookup"><span data-stu-id="0895f-191">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="0895f-192">Zejména pokud je k dispozici element s indexy `[i, j, k, l]`, žádné další prvky nemohou mít tyto indexy.</span><span class="sxs-lookup"><span data-stu-id="0895f-192">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="0895f-193">Příklad:</span><span class="sxs-lookup"><span data-stu-id="0895f-193">Example</span></span> #######

<span data-ttu-id="0895f-194">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-194">This section is informative.</span></span>

<span data-ttu-id="0895f-195">Následující objekt určuje Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="0895f-195">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="0895f-196">$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{6} , \sigma} a ^ {\dagger}\_{1, \rho}\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{2, \rho} a\_{3 , \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{2 , \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2 , \rho} a\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2 , \sigma} a ^ {\dagger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="0895f-196">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

##### <a name="particlehole-representation-object"></a><span data-ttu-id="0895f-197">Částic – objekt reprezentace otvoru</span><span class="sxs-lookup"><span data-stu-id="0895f-197">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="0895f-198">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-198">This section is normative.</span></span>

<span data-ttu-id="0895f-199">Objekt reprezentace částic určuje, zda jsou uložené integrály definovány s ohledem na vyjádření otvorů částic podle toho, jak Annihilation operátory vytváření a operátorů popisují excitations od používaného referenčního stavu, jako je Hartree – Stav Fock</span><span class="sxs-lookup"><span data-stu-id="0895f-199">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="0895f-200">Objekt je nepovinný.</span><span class="sxs-lookup"><span data-stu-id="0895f-200">The object is OPTIONAL.</span></span>
<span data-ttu-id="0895f-201">Pokud objekt není zadán, bude Hamiltonian interpretován tak, jak není zadáno v vyjádření částic.</span><span class="sxs-lookup"><span data-stu-id="0895f-201">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="0895f-202">Je-li k dispozici, hodnota `particle_hole_representation` musí být objekt množství zhuštěného pole, jehož indexy jsou čtyři celá čísla a jejichž hodnoty jsou číslo a řetězec.</span><span class="sxs-lookup"><span data-stu-id="0895f-202">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="0895f-203">Část řetězce hodnoty každého elementu musí obsahovat pouze znaky `'+'` a `'-'`, které určují, zda daný faktor v daném termínu je operátor vytvoření nebo Annihilation v vyjádření částic – díra.</span><span class="sxs-lookup"><span data-stu-id="0895f-203">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="0895f-204">Například `"-+++"` mikroreaguje na díru vytvořenou v lokalitě $i $ a částicích, které jsou vytvářeny v lokalitách $j, k $ a $l $.</span><span class="sxs-lookup"><span data-stu-id="0895f-204">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="0895f-205">Jako hodnota `particle_hole_representation` je objekt množství zhuštěného pole, musí být zadány vlastnosti `unit` a `format`.</span><span class="sxs-lookup"><span data-stu-id="0895f-205">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="0895f-206">Přijatelné jednotky jsou uvedeny v tabulce 1.</span><span class="sxs-lookup"><span data-stu-id="0895f-206">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="0895f-207">Vlastnost `format` je povinná a označuje, zda jsou Hamiltonian koeficienty zadány jako zhuštěné nebo zhuštěné pole.</span><span class="sxs-lookup"><span data-stu-id="0895f-207">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="0895f-208">V aktuální verzi jsou podporována pouze zhuštěná pole s výkladem, že všechny neurčené prvky jsou $0 $, ale budoucí verze mohou přidat podporu pro další hodnoty vlastnosti `format`.</span><span class="sxs-lookup"><span data-stu-id="0895f-208">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="0895f-209">Oddíl počáteční stav</span><span class="sxs-lookup"><span data-stu-id="0895f-209">Initial State Section</span></span> ###

<span data-ttu-id="0895f-210">Objekt initial_state_suggestion Určuje počáteční stavy, které mají zájem o zadaný Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="0895f-210">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="0895f-211">Tento objekt musí být pole objektů JSON `state`.</span><span class="sxs-lookup"><span data-stu-id="0895f-211">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="0895f-212">Stavový objekt</span><span class="sxs-lookup"><span data-stu-id="0895f-212">State object</span></span> ####

<span data-ttu-id="0895f-213">Každý stav představuje nadpozici obsazené orbitals.</span><span class="sxs-lookup"><span data-stu-id="0895f-213">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="0895f-214">Každý objekt stavu musí mít vlastnost `label` obsahující řetězec.</span><span class="sxs-lookup"><span data-stu-id="0895f-214">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="0895f-215">Každý objekt stavu musí mít vlastnost `superposition` obsahující pole základních stavů a jejich nenormalizované amplitudy.</span><span class="sxs-lookup"><span data-stu-id="0895f-215">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="0895f-216">Například počáteční stavy $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1 , \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0,2 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0,2 | ^ 2}} \ket{0} $ $ jsou reprezentované</span><span class="sxs-lookup"><span data-stu-id="0895f-216">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
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

#### <a name="basis-set-object"></a><span data-ttu-id="0895f-217">Základní objekt sady</span><span class="sxs-lookup"><span data-stu-id="0895f-217">Basis Set Object</span></span> ####

<span data-ttu-id="0895f-218">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-218">This section is normative.</span></span>

<span data-ttu-id="0895f-219">Každý objekt integrální sady může mít vlastnost `basis_set`.</span><span class="sxs-lookup"><span data-stu-id="0895f-219">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="0895f-220">Je-li k dispozici, hodnota vlastnosti `basis_set` musí být objekt se dvěma vlastnostmi, `type` a `name`.</span><span class="sxs-lookup"><span data-stu-id="0895f-220">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="0895f-221">Základní funkce identifikované hodnotou vlastnosti `basis_set` musí být reálné.</span><span class="sxs-lookup"><span data-stu-id="0895f-221">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="0895f-222">Předpokladem, že všechny základní funkce jsou reálné, mohou být v budoucích verzích této specifikace uvolněny.</span><span class="sxs-lookup"><span data-stu-id="0895f-222">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="0895f-223">Tabulky a seznamy</span><span class="sxs-lookup"><span data-stu-id="0895f-223">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="0895f-224">Tabulka 1.</span><span class="sxs-lookup"><span data-stu-id="0895f-224">Table 1.</span></span> <span data-ttu-id="0895f-225">Povolené fyzické jednotky</span><span class="sxs-lookup"><span data-stu-id="0895f-225">Allowed Physical Units</span></span> ###

<span data-ttu-id="0895f-226">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-226">This section is normative.</span></span>

<span data-ttu-id="0895f-227">Libovolný řetězec určující jednotku musí být jeden z následujících:</span><span class="sxs-lookup"><span data-stu-id="0895f-227">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="0895f-228">Analyzátory a producenti musí považovat následující jednoduché objekty množství jako ekvivalentní:</span><span class="sxs-lookup"><span data-stu-id="0895f-228">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="0895f-229">Tabulka 2.</span><span class="sxs-lookup"><span data-stu-id="0895f-229">Table 2.</span></span> <span data-ttu-id="0895f-230">Povolené konvence indexu</span><span class="sxs-lookup"><span data-stu-id="0895f-230">Allowed Index Conventions</span></span> ###

<span data-ttu-id="0895f-231">Tato část je normativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-231">This section is normative.</span></span>

<span data-ttu-id="0895f-232">Libovolný řetězec určující konvenci indexu musí být jeden z následujících:</span><span class="sxs-lookup"><span data-stu-id="0895f-232">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="0895f-233">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-233">This section is informative.</span></span>

<span data-ttu-id="0895f-234">V budoucích verzích této specifikace se můžou zavést další konvence indexu.</span><span class="sxs-lookup"><span data-stu-id="0895f-234">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="0895f-235">Výklad konvencí indexů</span><span class="sxs-lookup"><span data-stu-id="0895f-235">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="0895f-236">Tato část je informativní.</span><span class="sxs-lookup"><span data-stu-id="0895f-236">This section is informative.</span></span>
