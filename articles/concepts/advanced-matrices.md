---
title: Popis pokročilých konceptů matrice: Přečtěte si o exponenciálních eigenvectors, eigenvalues a matricích, základních nástrojích, které se používají k popisu a simulaci algoritmů.
Autor: QuantumWriter UID: Microsoft.. koncepty. Matrix-rozšířené MS. Author: v-benbra MS. Date: 12/11/2017 MS. téma: koncepční No-Loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "$$$"
- "$$$"
- "$$$"
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
# <a name="advanced-matrix-concepts"></a>Pokročilé koncepty matrice #

Teď rozšíříme své manipulace s matricemi na [*eigenvalues, eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) a [*exponenciální*](https://en.wikipedia.org/wiki/Matrix_exponential) , které tvoří základní sadu nástrojů, které potřebujeme k popisu a implementaci algoritmů.

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues a eigenvectors ##

Nechť $ M je $ čtvercová matice a $ v $ je vektor, který není vektorem všechny nuly (tj. vektor se všemi položkami rovnými $ 0 $ ).

Řekněme, $ $ že v je [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) M, pokud je v  $ $ $ = $ nějakém čísle $ jazyka c MV CV $ . Řekněme, $ $ že c je [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) odpovídající eigenvector $ v $ . Obecně $ může matice M $ transformovat vektor na jakýkoliv jiný vektor, ale eigenvector je zvláštní, protože je ponechán beze změny s výjimkou vynásobený číslem. Všimněte si, že pokud $ $ je v eigenvector s eigenvalue $ c $ , $ AV $ je také eigenvector (pro jakoukoliv nenulovou $ a $ ) se stejným eigenvalue.

Například pro matici identity je každý vektor $ v $ eigenvector s eigenvalue $ 1 $ .

Jako další příklad zvažte [*diagonální matici*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ D $ , která obsahuje pouze nenulové položky na diagonále:

$$
\begin{bmatrix}
d_1 & 0 0 0 & d_2 0 0 0 \\\\ & & \\\\ & & D_3 \end{bmatrix} .
$$

Vektory

$$\begin{bmatrix}1 \\\\ 0 \\\\ \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} a \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$

eigenvectors z této matrice s eigenvalues  $ D_1 $ , $ d_2 $ a $ D_3 $ , v uvedeném pořadí. Pokud $ D_1 $ , $ d_2 $ a $ D_3 $ mají odlišná čísla, pak jsou tyto vektory (a jejich násobky) jediným eigenvectors matice $ d $ . Obecně platí, že pro diagonální matrici je snadné číst z eigenvalues a eigenvectors. Eigenvalues jsou všechna čísla, která se zobrazují na diagonále a jejich příslušné eigenvectors jsou vektory jednotek s jednou položkou rovnající se $ 1 $ a zbývající položky rovnající se $ 0 $ .

Všimněte si výše uvedeného příkladu, že eigenvectors $ D $ tvoří základ pro trojrozměrné $ $ vektory. Základem je sada vektorů, což znamená, že každý vektor lze zapsat jako lineární kombinaci. Explicitní, $ v_1 $ , $ v_2 $ a $ v_3 $ tvoří základ, pokud je libovolný vektor $ v $ zápisu jako $ v = A_1 v_1 + a_2 v_2 + a_3 v_3 $ pro některá čísla $ A_1 $ , $ A_2 $ a $ a_3 $ .

Odvolání, že matice Hermitian (označovaná také jako samostatně rovnocenná) je složitá čtvercová matice, která se rovná své vlastní složitosti sdružené transponovat, zatímco Jednotková matice je složitá čtvercová matice, jejíž inverzní funkce se rovná jejímu sousedovi nebo složitě sdružené hodnotě.
V případě Hermitian a maticových matric, které jsou v podstatě jenom pro tyto matrice, je k dispozici obecný výsledek, který je známý jako [*spektrální věta*](https://en.wikipedia.org/wiki/Spectral_theorem), který vyhodnotí následující: pro každou Hermitian nebo jednotkovou matrici $ m $ existuje $ $ pro každou $ = \dagger $ úhlopříčnou matrici $ $ s jednotkou v jednotkách u ^ D u. Kromě toho diagonální položky $ D $ budou eigenvalues $ M $ .

Už víte, jak vypočítat eigenvalues a eigenvectors úhlopříčné matrice $ D $ . Pomocí tohoto věta víme, že pokud $ v $ je eigenvector z $ D $ s eigenvalue $ c $ , tj. $ DV = CV $ , pak $ U ^ \dagger v $ bude eigenvector z $ M $ s eigenvalue $ c $ . Důvodem je to, že

$$M (U ^ \dagger v) = u ^ \dagger d u (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger ) v = U ^ \dagger D v = c u ^ \dagger v.$$

## <a name="matrix-exponentials"></a>Exponenciální matice
Exponenciální funkce lze definovat také pomocí [*exponenciálního*](https://en.wikipedia.org/wiki/Matrix_exponential) analogie matice.  Matice exponenciálního exponentu matice $ a $ může být vyjádřena jako

$$
e ^ A = \boldone + a + \frac { a ^ 2 } { 2! } + \frac { A ^ 3 } { 3!}+\cdots
$$

To je důležité kvůli tomu, že při vývoji v mechanickém čase je popsána jednotná matice formuláře $ e ^ { IB } $ pro Hermitian Matrix $ B $ .  Z tohoto důvodu je provádění exponenciálních exponenciálních výpočetních operací základní částí výpočetní funkce a jako taková Q# nabízí vnitřní rutiny pro popis těchto operací.
Existuje mnoho způsobů, jak na klasický počítač vypočítat exponenciální exponenciálu matrice, a obecně numericky přibližně fraught s Peril.  Viz [*Cleve Moler a Charles Van půjčka. "Devatenáct podezřelých způsoby výpočtu exponenciálního podílu matice." SIAM revize 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) pro další informace o problémech, které se týkají.

Nejjednodušší způsob, jak porozumět tomu, jak vypočítat exponenciální část matice, je prostřednictvím eigenvalues a eigenvectors této matrice.  Konkrétně věta spektrální popis uvádí, že pro každou Hermitian nebo jednotnou matrici $ $ existuje jednotná matice $ u $ a šikmá matice $ D $ tak, že $ = u ^ \dagger D u $ .  Vzhledem k tomu, že vlastnosti unitarity máme $ ^ 2 = u ^ \dagger d ^ 2 u $ a podobně pro všechny síly $ p $ $ a ^ p = u ^ \dagger D ^ p u $ .  Pokud tuto část nasadíme do definice operátora exponenciálního operátoru, získáte:

$$
e ^ A = U ^ \dagger \left ( \boldone + d + \frac { d ^ 2 } { 2! } + \cdots \right ) U = u ^ \dagger \begin{bmatrix} \exp (D_ { 11 } ) & 0 0 0 & \cdots & \\\\ & \exp (D_ { 22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp (D_ { NN } ) \end{bmatrix} U.$$

Jinými slovy, pokud Transformujte na eigenbasis matice $ a $ potom výpočet exponenciální hodnoty matice je ekvivalentní s výpočetem obyčejného exponenciálního exponenciálního eigenvaluesu matice.  Tolik operací v případě, že výpočetní výkon zahrnuje provádění exponenciálních exponenciálních výpočetních funkcí, je tento způsob transformace do eigenbasis matice, aby se zjednodušila i četnost exponenciálního zobrazení operátorů.

Další užitečnou vlastností je, že $ b $ je v obou i Hermitian, tj. b $ = b ^ { -1 } = b ^ a \dagger $ $ B ^ 2 = \boldone $ . Když použijete toto pravidlo na výše uvedené rozšíření matice exponenciálního součtu a $ \boldone $ $ spojíte a a B $ , může to být vidět pro libovolnou skutečnou hodnotu $ x $ identity.

$$e ^ { iBx } = \boldone \cos (x) + iB\sin (x)$$


ryby. Tento zdvih je zvláště užitečný, protože umožňuje odůvodnění exponenciálních exponenciálních akcí, a to i v případě, že je rozměr $ b $ exponenciálně velký, pro zvláštní případ, $ Pokud $ je b jednotkou a Hermitian.
