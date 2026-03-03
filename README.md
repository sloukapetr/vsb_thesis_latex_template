# VŠB – LaTeX šablona pro závěrečné práce / LaTeX Thesis Template

---

## 🇨🇿 Česky

### O šabloně

Tato šablona slouží pro sazbu závěrečných prací (bakalářských, diplomových a disertačních) na **VŠB – Technické univerzitě Ostrava**, Fakultě elektrotechniky a informatiky (FEI). Šablona splňuje typografické požadavky fakulty a usnadňuje formátování práce v systému LaTeX.

### Podporované typy prací

| Volba                | Typ práce                              |
|----------------------|----------------------------------------|
| `bachelor`           | Bakalářská práce                       |
| `bachelorpractice`   | Absolvování individuální odborné praxe |
| `master`             | Diplomová práce                        |
| `phd`                | Disertační práce                       |

### Podporované jazyky

| Volba      | Jazyk      |
|------------|------------|
| `czech`    | Čeština    |
| `slovak`   | Slovenština|
| `english`  | Angličtina |

### Struktura souborů

```
MasterThesis.tex          – hlavní LaTeX soubor
diploma.cls               – třída dokumentu
diplomalst.sty            – balík pro zvýraznění zdrojových kódů
biblatex-examples.bib     – ukázkové bibliografické záznamy
coffee.bib                – bibliografický záznam pro ukázkový obrázek
FictiveThesisAssignment.pdf – ukázkové zadání práce
Chapters/
  Introduction.tex        – úvod
  SampleChapter1.tex      – ukázková kapitola 1
  SampleChapter2.tex      – ukázková kapitola 2
  TechnicalDetails.tex    – technické detaily (křížové odkazy, citace, překlad)
  Conclusion.tex          – závěr
  Appendix1.tex           – příloha 1
  Appendix2.tex           – příloha 2
Figures/                  – obrázky
SourceCodes/              – zdrojové kódy vkládané do práce
```

### Nastavení šablony

V hlavním souboru (`MasterThesis.tex`) nastavte:

```latex
\documentclass[czech,master]{diploma}  % jazyk a typ práce

\ThesisAuthor{Jméno Příjmení}
\ThesisSupervisor{Titul Jméno Příjmení, Titul}
\CzechThesisTitle{Název práce v češtině}
\EnglishThesisTitle{Thesis Title in English}
\SubmissionYear{2024}
\ThesisAssignmentFileName{ZadaniPrace.pdf}  % soubor se zadáním práce
\Acknowledgement{Text poděkování}
\CzechAbstract{Text českého abstraktu}
\CzechKeywords{klíčové slovo 1; klíčové slovo 2}
\EnglishAbstract{English abstract text}
\EnglishKeywords{keyword 1; keyword 2}
\AddAcronym{zkratka}{Vysvětlení zkratky}
```

### Překlad dokumentu

Pro překlad od základu je nutné spustit následující příkazy v daném pořadí:

```bash
pdflatex MasterThesis
biber MasterThesis
pdflatex MasterThesis
pdflatex MasterThesis
```

Doporučujeme použít IDE s podporou LaTeX, jako je **TeXstudio**, **VS Code** s rozšířením LaTeX Workshop nebo **Overleaf**.

### Požadavky

- TeX distribuce: **TeX Live** (doporučeno) nebo **MiKTeX**
- Bibliografie: **Biber** (součást TeX Live)
- Fonty: Latin Modern (`lmodern`), T1 kódování
- Požadované balíky: `babel`, `biblatex`, `csquotes`, `geometry`, `graphicx`, `hyperref`, `pdfx`, a další (viz `diploma.cls`)

### Zvýraznění zdrojového kódu

Šablona obsahuje balík `diplomalst.sty` pro zvýraznění syntaxe zdrojových kódů. Výchozí jazyk je C#. Podporované jazyky: `ansic`, `bash`, `cpp`, `csharp`, `delphi`, `html`, `java`, `latex`, `lua`, `matlab`, `octave`, `pascal`, `perl`, `php`, `python`, `ruby`, `r`, `sql`, `vb`, `vhdl`, `xml` a další.

```latex
\usepackage[cpp]{diplomalst}   % výchozí jazyk C++
```

### Licence

Toto dílo podléhá licenci **CC BY-NC-ND 3.0 CZ**. Lze jej šířit a používat pro nekomerční účely, musí být uveden autor a dokument nelze měnit. Podrobnosti: <https://creativecommons.org/licenses/by-nc-nd/3.0/cz/>

---

## 🇬🇧 English

### About the Template

This template is designed for typesetting final theses (bachelor's, master's, and PhD) at **VŠB – Technical University of Ostrava**, Faculty of Electrical Engineering and Computer Science (FEI). The template complies with the faculty's typographic requirements and simplifies document formatting in LaTeX.

### Supported Thesis Types

| Option               | Thesis Type                                    |
|----------------------|------------------------------------------------|
| `bachelor`           | Bachelor Thesis                                |
| `bachelorpractice`   | Individual Professional Practice in a Company  |
| `master`             | Diploma (Master's) Thesis                      |
| `phd`                | PhD Thesis                                     |

### Supported Languages

| Option     | Language |
|------------|----------|
| `czech`    | Czech    |
| `slovak`   | Slovak   |
| `english`  | English  |

### File Structure

```
MasterThesis.tex          – main LaTeX file
diploma.cls               – document class
diplomalst.sty            – package for source code syntax highlighting
biblatex-examples.bib     – sample bibliography entries
coffee.bib                – bibliography entry for sample figure
FictiveThesisAssignment.pdf – sample thesis assignment PDF
Chapters/
  Introduction.tex        – introduction chapter
  SampleChapter1.tex      – sample chapter 1
  SampleChapter2.tex      – sample chapter 2
  TechnicalDetails.tex    – technical details (cross-references, citations, build)
  Conclusion.tex          – conclusion chapter
  Appendix1.tex           – appendix 1
  Appendix2.tex           – appendix 2
Figures/                  – figures and images
SourceCodes/              – source code files included in the thesis
```

### Template Configuration

In the main file (`MasterThesis.tex`), configure:

```latex
\documentclass[english,master]{diploma}  % language and thesis type

\ThesisAuthor{First Last}
\ThesisSupervisor{Title First Last, Title}
\CzechThesisTitle{Název práce v češtině}
\EnglishThesisTitle{Thesis Title in English}
\SubmissionYear{2024}
\ThesisAssignmentFileName{ThesisAssignment.pdf}  % file with thesis assignment
\Acknowledgement{Acknowledgement text}
\CzechAbstract{Czech abstract text}
\CzechKeywords{keyword 1; keyword 2}
\EnglishAbstract{English abstract text}
\EnglishKeywords{keyword 1; keyword 2}
\AddAcronym{ABBR}{Abbreviation explanation}
```

### Building the Document

To build the document from scratch, run the following commands in order:

```bash
pdflatex MasterThesis
biber MasterThesis
pdflatex MasterThesis
pdflatex MasterThesis
```

It is recommended to use a LaTeX IDE such as **TeXstudio**, **VS Code** with the LaTeX Workshop extension, or **Overleaf**.

### Requirements

- TeX distribution: **TeX Live** (recommended) or **MiKTeX**
- Bibliography backend: **Biber** (included in TeX Live)
- Fonts: Latin Modern (`lmodern`), T1 encoding
- Required packages: `babel`, `biblatex`, `csquotes`, `geometry`, `graphicx`, `hyperref`, `pdfx`, and others (see `diploma.cls`)

### Source Code Highlighting

The template includes `diplomalst.sty` for syntax highlighting of source code listings. The default language is C#. Supported languages include: `ansic`, `bash`, `cpp`, `csharp`, `delphi`, `html`, `java`, `latex`, `lua`, `matlab`, `octave`, `pascal`, `perl`, `php`, `python`, `ruby`, `r`, `sql`, `vb`, `vhdl`, `xml`, and more.

```latex
\usepackage[cpp]{diplomalst}   % default language C++
```

### License

This work is licensed under **CC BY-NC-ND 3.0 CZ**. You may distribute it and use it for non-commercial purposes, but the author must be mentioned and the document cannot be changed. Details: <https://creativecommons.org/licenses/by-nc-nd/3.0/cz/deed.en>
