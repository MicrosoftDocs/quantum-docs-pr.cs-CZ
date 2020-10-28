---
title: Pauli měření Popis: Naučte se pracovat s operacemi měření jednoduchých a qubit Pauli.
Autor: bradben UID: Microsoft.. koncepty. Pauli MS. Author: v-benbra MS. Date: 12/11/2017 MS. téma: No-Loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="pauli-measurements"></a>Pauli měření

V předchozích diskusích jsme se zaměřili na výpočetní základní měření.
Ve skutečnosti existují další běžná měření, ke kterým dochází v množství náročném na výpočetní výkon, který je ze zapsaných perspektiv pohodlný, aby se vyjádřily na základě výpočetních měření.
Když pracujete s Q# , nejběžnější druh měření, na který budete pracovat, bude pravděpodobně *Pauli měřením* , které generalizace výpočetních měření budou zahrnovat měření v jiných základech, a parity mezi různými qubits.
V takových případech je běžné projednávat měření operátoru Pauli, a to obecně operátor, jako je $ x, Y, Z $ nebo $ z \otimes , x \otimes x, x \otimes Y $ a tak dále.

> [!TIP]
> V nástroji Q# jsou operátory qubit Pauli obvykle zastoupeny poli typu `Pauli[]` .
> Například pro reprezentaci $ X \otimes Z \otimes Y $ lze použít pole `[PauliX, PauliZ, PauliY]` .

Projednávání měření v rámci Pauli operátorů je zvlášť běžné v podpoli s opravou chyb pro každé z nich.
V systému Q# se používá podobná konvence. nyní Vysvětleme toto alternativní zobrazení měření.

Než se pustíte do detailů o tom, jak si představit Pauli měření, je vhodné se seznámit s tím, jak měření jedné qubit v rámci počítače ve státě
Představte si, že máme $ n $ -qubit stavový stát; pak měřením jednoho qubit se okamžitě odhlásí polovinu z $ možností 2 ^ n $ , na které se stav může nacházet.
Jinými slovy, měření rozloží stav na jednu ze dvou polovičních mezer.
Můžeme zobecnit způsob, jak si myslíme na měření, aby odrážel tento Intuition.

Pro výstižnější identifikaci těchto podprostorů potřebujeme jazyk, který popisuje jejich popis.
Jedním ze způsobů, jak popsání dvou podprostorů, je jejich zadání prostřednictvím matrice, která má pouze dvě jedinečné eigenvalues, kterou zabere konvence $ \Pm 1 $ .
Pro jednoduchý příklad, jak popsat podprostory tímto způsobem, zvažte $ Z $ :

$$
\begin{align}
  Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} .
\end{align}
$$

Načtením diagonálních prvků $ matrice Pauli-Z se $ dá vidět, že $ Z $ má dvě eigenvectors, $ \ket { 0 } $ a $ \ket { 1 } $ s odpovídajícím eigenvalues $ \Pm 1 $ .
Proto pokud měříme qubit a získáme `Zero` (odpovídá stavu $ \ket { 0 } $ ), víme, že stav našeho qubit je $ + 1 $ eigenstate $ $ operátoru z.
Podobně, pokud získáme `One` , víme, že stav našeho qubit je a $ -1 $ eigenstate z z $ $ . Tento proces se označuje v jazyce Pauli měření jako "měřicí Pauli $ Z $ " a je zcela ekvivalentní k provádění výpočetních měření.

Všechna $ 2 \times 2 $ matice, která představuje jednotnou transformaci z, $ $ také splňuje tato kritéria.
To znamená, že můžeme také použít matrici $ a = U ^ \dagger Z u $ , kde $ U $ je jakákoli jiná jednotná matice, pro poskytnutí matrice, která definuje dva výsledky měření ve své $ \Pm 1 $ eigenvectors.
Zápis měření Pauli odkazuje na tuto jednotnou odchylku tím, že identifikuje $ měření X, Y, Z $ jako ekvivalentních hodnot, které může získat informace z qubit.
Tato měření jsou uvedena níže pro usnadnění práce.


||Jednotná transformace měření Pauli|
|-------------------|------------------------|
|$ $ Z |               $\boldone$             |
|$ $ X | $H               $                    |
|$ $ A | $HS – ^               {\dagger}$         |

To znamená, že při použití tohoto jazyka je "Measure $ Y $ " ekvivalentem použití $ HS ^ \dagger $ a pak se měří v výpočetním základu, kde [`S`](xref:Microsoft.Quantum.Intrinsic.S) se jedná o vnitřní operaci na základě fáze, která se někdy označuje jako "brána", a může být simulována jednotnou maticí.

$$
\begin{align}
    S =\begin{bmatrix}
        1 & 0 \\\\ 0 & i \end{bmatrix} .
\end{align}
$$

Je také ekvivalentní s použitím $ HS ^ \dagger $ na vektor stavu a následně na měření $ Z $ , aby následující operace byla rovnocenná `Measure([PauliY], [q])` :

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        Adjoint S(q);
        H(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

Správný stav by se pak našel tak, že transformuje zpátky na výpočetní základ, který se použije k použití $ SH $ na vektor stavu bez hodnoty. ve výše uvedeném fragmentu kódu se transformace zpátky na výpočetního základu automaticky zpracuje pomocí `within … apply` bloku.

V systému Q# uvádíme výsledek---to znamená, že klasické informace extrahované z interakce se stavem---jsou předány `Result` hodnotou $ j \in \\ { \texttt { nula } , \texttt { jedna označuje, } \\ } $ zda je výsledek v $ (-1) ^ j $ eigenspace operátoru Pauli.


## <a name="multiple-qubit-measurements"></a>Měření s více qubit

Měření qubitch operátorů Pauli je definováno podobně, jak je vidět na základě těchto možností:

$$
Od z 1 0 0 0-1 0 0 0 0 – 0 0 0 0 0 \otimes = \begin{bmatrix} & & & \\\\ & & & \\\\ & & & \\\\ & & & . 1 \end{bmatrix} .
$$

Proto tensor produkty dvou operátorů Pauli- $ Z $ tvoří matici tvořenou dvěma mezerami, které se skládají z $ + 1 $ a $ -1 $ eigenvalues.
Stejně jako u jediného qubitu představuje prostor, který znamená, že polovina přístupného vektorového prostoru patří do rozmezí $ + 1 $ eigenspace a zbylé polovině k $ -1 $ eigenspace.
Obecně se dá snadno zobrazit z definice tensor produktu, že se jedná o tensor $ a identitu Pauli-Z $ .
Příklad:

$$
\begin{align}
    \otimes \boldone Z =\begin{bmatrix}
        1 & 0 0 0 & &\\\\
        0 & 1 & 0 &\\\\
        0 &  0 & -1 &  0 \\\\
        0 0 0 & & & -1 \end{bmatrix} .
\end{align}
$$

Stejně jako v případě jakékoli jednotkové transformace těchto matic také popisuje dvě poloviční prostory označené $ \Pm 1 $ eigenvalues.
Například $ x \otimes x = h \otimes H (z \otimes ) h \otimes h $  od identity, která $ z = HXH $ .
Podobně jako u qubitového případu je možné všechny qubit Pauli-měření zapsat jako $ u ^ \dagger (Z \otimes \id ) u $ pro $ 4 \times 4 $ jednotkové matice $ u $ . Vytvoříme výčet transformací v následující tabulce.

> [!NOTE]
>V následující tabulce používáme $ \operatorname { swap } $ k označení matice > .$$
> \begin{align}
>     \operatorname{Prohodit } &=
>     \left( \begin { matice}
>1 & 0 0 0 & &\\\\
>         0 & 0 & 1 & 0 \\\\
>0 & 1 & 0 &\\\\
>0 & & & > \end { } \right matice > 0 0 1     \end{align}
> $$
> slouží k simulaci vnitřní operace [`SWAP`](xref:Microsoft.Quantum.Intrinsic) .

||Jednotná transformace měření Pauli|
|----------------------|------------------------|
|$ \otimes \boldone Z $ | $\boldone\otimes \boldone$|
|$ \otimes \boldone X $ | $ \otimes \boldone H $|
|$ \otimes \boldone A $ | $ HS – ^ \dagger \otimes \boldone $|
|$\boldone \otimes $ | $ \operatorname { swap } Z $|
|$\boldone \otimes $ | $ \otimes \boldone \operatorname { prohození } X (H $ )|
|$\boldone \otimes $ | $ \dagger \otimes \boldone \operatorname { swap } Y $ (HS ^)|
|$Z \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } $|
|$X \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes \boldone ) $|
|$A \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes \boldone ) $|
|$Z \otimes X $ | $ \operatorname { CNOT } \_ { 10 } ( \boldone \otimes H) $|
|$X \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (h \otimes h) $|
|$A \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes H) $|
|$Z \otimes Y $ | $ \operatorname { CNOT } \_ { 10 } ( \boldone \otimes HS ^ \dagger ) $|
|$X \otimes Y $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes HS ^ \dagger ) $|
|$A \otimes A $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes HS ^ \dagger ) $|

Tato [`CNOT`](xref:Microsoft.Quantum.Intrinsic.CNOT) operace se zobrazí z následujícího důvodu.
Jednotlivá měření Pauli, která neobsahují $ \boldone $ matici, jsou ekvivalentní až $ z z \otimes $ výše uvedeného důvodu.
Eigenvalues z z $ \otimes pouze je $ závislá na paritě qubits, která zahrnuje každý výpočetní vektor a kontrolované – nečinnosti slouží k výpočtu této parity a jejich uložení v prvním bitu.
Po měření prvního bitu můžeme obnovit identitu výsledného prostoru, který je ekvivalentní k měření Pauli operátoru.

Jedna další Poznámka: i když se může stát, že měření z z $ \otimes $ je stejné jako při sekvenčním měření $ z \otimes \mathbb { 1 } $ a potom $ \mathbb { 1 } \otimes Z $ , tento předpoklad by byl nepravdivý.
Důvodem je, že měření $ z \otimes $ projektů z projektu se stavem do $ + 1 $ nebo $ -1 $ eigenstate těchto operátorů.
Měření $ z \otimes \mathbb { 1 } $ a poté $ \mathbb { 1 } \otimes z $ projektů v projektech se vektorem stavu nepočátečních stavů nejprve na polovinu prostoru z $ \otimes \mathbb { 1 } $ a pak na polovinu prostoru $ \mathbb { 1 } \otimes z $ . Vzhledem k tomu, že jsou k dispozici čtyři výpočetní vektory, může použití obou měření snížit stav na čtvrtinové místo a tím se sníží na jeden vektor výpočetního základu.

## <a name="correlations-between-qubits"></a>Korelace mezi qubity
Další možností, jak se podívat na měření tensor produktů Pauli, jako jsou $ x \otimes x $ nebo $ z \otimes z $ , je, že tato měření vám umožní podívat se na informace, které jsou uložené v korelaci mezi těmito dvěma qubits.
Měření hodnoty $ X \otimes \id $ vám umožní podívat se na informace, které jsou místně uložené v první qubit.
I když jsou oba typy měření stejně cenné při práci ve výpočetním prostředí, bývalé osvětlení síly při práci.
To znamená, že ve výpočetním prostředí se často informace, které chcete vědět, neukládají do žádného qubit, ale místo toho, aby se ukládaly do všech qubits najednou, a proto jenom pomocí společného měření (např. $ z \otimes $ ) se tyto informace stanou manifestem.

Například při opravě chyb často chceme zjistit, k jaké chybě došlo při učení o stavu, který se snažíte chránit.
[Ukázka bitového překlápění kódu](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) ukazuje příklad toho, jak to lze provést pomocí měření, jako je z $ \otimes \otimes \id $ a $ \id \otimes z \otimes z $ . < ! --TODO: Změňte tuto hodnotu na odkaz na prohlížeč ukázek hned po zprovoznění vzorku bitového překlápění kódu. -->

Lze také změřit libovolné Pauli operátory, jako je například $ X \otimes Y \otimes Z \otimes \boldone $ .
Všechny takové produkty tensor operátorů Pauli mají pouze dvě eigenvalues $ \Pm 1 $ a oba eigenspaces představují poloviční prostory celého vektorového prostoru.
Proto se shodují s výše uvedenými požadavky.

V Q# , taková měření vrátí hodnotu $ j, $ Pokud měření vede k výsledku eigenspace znaménka $ (-1) ^ j $ .
Pauli měření jako integrovaná funkce v nástroji Q# je užitečné, protože měření takových operátorů vyžaduje dlouhé řetězy řízených a nevratných operací a základní transformace, které popisují $ bránu diagonalizing U, která $ se potřebuje k tomu, aby se operace mohla vyjádřit jako tensor produkt z $ $ a $ \id $ .
Díky možnosti určit, že chcete provést jedno z těchto předdefinovaných měření, nemusíte si dělat starosti s tím, jak transformovat svůj základ, aby výpočetní základní měření poskytovalo potřebné informace.
Q# zpracuje všechny potřebné základní transformace automaticky.
Další informace najdete v tématu [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) operace a [`MeasurePaulis`](xref:Microsoft.Quantum.Measurement.MeasurePaulis) .

## <a name="the-no-cloning-theorem"></a>No-Cloning věta

Informace o nemocném případě jsou výkonné.
Umožňuje nám dělat úžasné věci, jako jsou čísla faktorů exponenciálně rychleji než nejlepší známé klasické algoritmy, nebo efektivně simulovat korelační elektronické systémy, které Classic potřebují k přesnému simulaci exponenciálních nákladů.
Existují však určitá omezení výkonu s využitím nároku na výpočetní výkon.
Jedno takové omezení je dáno *větaem bez klonování* .

No-Cloning věta je aptly s názvem.
Neumožňuje klonování obecných stavových stavů počítačem s více než jednou.
Důkaz věta je výjimečně přímočarý.
Úplný důkaz věta bez klonování je pro naši diskuzi příliš technický, proto se v rámci našeho oboru nejedná o důkaz, že v případě žádného dalšího pomocného qubitsu není v našem rozsahu (pomocné qubits se qubits používá pro pomocné místo během výpočtu a snadno se používá a spravuje v najdete v Q# tématu [výpůjčkované qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).

V případě takového počítače s více operačními systémem musí být operace klonování popsána jednotnou maticí.
Nezakážeme měření, protože by došlo k poškození stavu, který se snažíme klonovat.
Pro simulaci operace klonování chceme, aby jednotná matice používala vlastnost, která $$
  U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}
$$
pro libovolný stav $ \ket { \psi } $ .
Vlastnost linearity matice násobení znamená, že pro libovolný $ druhý stav \ket { \phi } $

$$
\begin{align}
    U \left [ \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ] \ket { 0}
    &= \frac{ 1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}
      + \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\
    &= \frac{ 1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}
        \right) \\\\
    &\ne \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ).
\end{align}
$$

To poskytuje základní Intuition za No-Cloning věta: každé zařízení, které kopíruje neznámý stav, musí způsobit chyby alespoň u některých stavů, které kopíruje.
I když klíč předpokládá, že Cloner funguje lineárně na vstupním stavu, může být porušená přidáním a měřením pomocných qubits, takže tyto interakce také nevrací informace o systému prostřednictvím statistik měření a zabrání v takových případech přesné klonování.
Podrobnější kontrolu No-Cloning věta najdete v tématu další [informace](xref:microsoft.quantum.more-information).

No-Cloning věta je důležité pro kvalitativní porozumění výpočetním procesorům, protože pokud byste mohli naklonovat stavy nenákladných stavových procesorů, pak by vám byla udělena téměř Magical možnost učit se ze států.
Ve skutečnosti byste mohli narušit zásadu nejistoty Heisenberg vaunted.
Alternativně můžete použít optimální Cloner k získání jedné ukázky ze složitosti distribuce nečinnosti a zjistit všechno, co byste se mohli dozvědět o této distribuci jenom z jedné ukázky.
To by vypadalo jako převrácení mince a pozorování hlav a následného oznámení o tom, že na výsledek má odpovědět "Ah. rozdělení této mince musí být Bernoulliho pomocí $ p = 0.512643 \ ldots $ !"  Takový příkaz by nebyl sensical, protože jeden z bitových informací (výsledek hlav) jednoduše nemůže poskytnout mnoho informací potřebných ke kódování distribuce bez podstatných předchozích informací.
Podobně bez předchozích informací nemůžeme zcela klonovat stav, protože nemůžeme připravit komplet těchto mincí bez vědomí $ p $ .

Informace nejsou v výpočetním prostředí bezplatné.
Každá qubit měřená má jeden bit informací a No-Cloning věta ukazuje, že není k dispozici zadní vrátka, které by bylo možné zneužít k získání základních kompromisů mezi informacemi získanými v systému a jeho vyvoláním.
