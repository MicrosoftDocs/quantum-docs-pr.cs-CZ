# <a name="articles"></a>Články

V tomto adresáři najdete články pro dokumentaci k vývojové sadě pro plnění. Tento adresář obsahuje:

- **Adresáře článků**: obsahují články pro každou část dokumentace. V těchto adresářích můžete najít následující obsah:
  
  - Každý adresář obsahuje `toc.yml` soubor pro zobrazení obsahu adresáře v hlavní tabulce obsahu (TOC).
  - Markdownu články, které obsahují dokumentaci. Tyto články by měly postupovat podle pokynů [Microsoft docs příručce pro přispěvatele](https://docs.microsoft.com/en-us/contribute/).
  - Články podadresáře. Tyto podadresáře by měly obsahovat také vlastní `toc.yml` soubor.

> :p encil: i když je možné odkázat `*.md` soubory přímo v nadřazeném `TOC.yml` souboru, aby se vám objednaly věcí, na které se vztahují jenom z `toc.yml` aktuálního adresáře.

- **Hlavní `TOC.yml` soubor obsahu (TOC)**: v tomto souboru jsou uvedeny části obsahu webu spolu s odkazem na hlavní `toc.yml` soubor adresáře každého oddílu.
- **`index.yml`** YAML s konfigurací cílové stránky dokumentace.
- **`\media`**: Adresář, do kterého se mají ukládat všechny image používané v dokumentaci. Obsahuje `\media\src` podadresář pro ukládání zdrojových souborů imagí.
- **Soubory s licencí**: soubory s platnými licencemi
- **Technické soubory**: soubory obsahující makra a metadata.

## <a name="guidelines"></a>Pokyny

Některé obecné pokyny týkající se organizace tohoto adresáře pro přispěvatele:

- Každý adresář nebo podadresář by měl obsahovat vlastní `toc.yml` soubor, ve kterém jsou uvedeny články na stejné úrovni nebo `toc.yml` soubory jeho podřízených adresářů.
- Organizace adresářů v úložišti by měla být co nejblíže organizaci obsahu stránky dokumentace k obsahu.
- Všechny bitové kopie by měly být uloženy v `articles\media` a nikoli ve složce článků.
- Nadpisy článků, názvy v obsahu a *UID* metadat by měly být co nejblížeelné a musí představovat jasně hlavičku H1 dokumentu Markdownu.

## <a name="adding-images"></a>Přidávání imagí

Aby se obrázky v tmavém režimu správně vykreslit, musíte se vyhnout průhlednostem.
- Pro `*.jpg` soubory, které nepotřebujete, nemusíte dělat nic, protože formát souboru nepodporuje transparentní prvky.
- Pro `*.png` soubory musíte přidat bílé pozadí nebo změnit hodnotu alfa kanálu na 100. Nejjednodušší způsob, jak to provést ve Windows, je otevření souboru v malování a ukládání a přepsání původního souboru.
- `*.svg`V případě souborů je nutné přidat bílý obdélník do nejnižší vrstvy. Můžete to provést pomocí Inkscape:
  - Otevřete soubor `*.svg`.
  - Vyberte nástroj čtvercového tvůrce a nakreslete bílý obdélník nad původní obrázek.
  - Kliknutím na šipku dolů nebo stisknutím klávesy F1 vyberte nástroj "vybrat a transformovat objekty".
  - Když máte vybraný obdélník, klikněte na panel nástrojů "nižší výběr na konec (konec)".
  - Upravte obdélník pomocí myši nebo kláves se šipkami.
