# English Thesis Template / 英語論文テンプレート

## English

### Overview

This repository provides a LaTeX template for an English master's thesis based on `ujreport`.
It is configured for `uplatex + dvipdfmx` and includes a title page, abstract, table of contents, main chapters, acknowledgements, references, and a research achievements page.

### File Structure

- `main.tex`: Main entry file of the thesis.
- `body.tex`: Main chapter and section contents.
- `English_thesis.sty`: Local style file for title page and thesis formatting.
- `references.bib`: BibTeX database.
- `rm2c_junsrt.bst`: Bibliography style file.
- `latexmkrc`: Build configuration for `latexmk`.
- `figures/`: Directory for figures and images.
- `build/`: Output directory for auxiliary files and the generated PDF.

### Requirements

Please make sure the following tools are available in your TeX environment:

- `uplatex`
- `dvipdfmx`
- `upbibtex`
- `latexmk`

This template was prepared for a TeX Live environment.

### How to Compile

Compile the thesis from the project root:

```bash
latexmk -pdfdvi main.tex
```

The generated PDF will be placed here:

```text
build/main.pdf
```

To clean auxiliary files:

```bash
latexmk -c
```

To clean almost everything including the generated PDF:

```bash
latexmk -C
```

### How to Edit the Thesis

#### 1. Update Thesis Information

Edit the metadata in `main.tex`:

- `\年度{...}`
- `\学位種別{...}`
- `\題目{...}`
- `\指導教員{...}`
- `\所属一行目{...}`
- `\所属二行目{...}`
- `\所属三行目{...}`
- `\学籍番号{...}`
- `\氏名{...}`

#### 2. Write the Abstract

Edit the `abstract` environment in `main.tex`:

```tex
\begin{abstract}
...
\keywords{
...
}
\end{abstract}
```

#### 3. Write Main Chapters

Edit `body.tex` to add or revise chapters and sections.

Example:

```tex
\chapter{Introduction}
\section{Background}
```

#### 4. Manage References

Add bibliography entries to `references.bib`, then cite them in the thesis as usual.

The reference section is controlled in `main.tex` by:

```tex
\bibliographystyle{rm2c_junsrt}
\bibliography{references}
```

If you want to disable the bibliography temporarily, change:

```tex
\usebibliographytrue
```

to:

```tex
\usebibliographyfalse
```

#### 5. Acknowledgements

Edit the acknowledgements text in `main.tex` under:

```tex
\section*{Acknowledgements}
```

#### 6. Research Achievements

Edit the research achievements section in `main.tex` under:

```tex
\section*{Research Achievements}
```

The current template uses plain list items without numbering.
The command below can be used to underline your own name:

```tex
\achievementauthor{Your Name}
```

Example:

```tex
\item \achievementauthor{Your Name}, Coauthor, and Coauthor, ``Paper Title,'' ...
```

### Figures

Place image files in the `figures/` directory and include them in LaTeX as needed.

Example:

```tex
\begin{figure}[t]
    \centering
    \includegraphics[width=0.8\linewidth]{figures/example.pdf}
    \caption{Example figure.}
    \label{fig:example}
\end{figure}
```

### Notes

- The template is currently set up for English thesis writing.
- The title page labels and some structural names are customized in `English_thesis.sty`.
- `Acknowledgements`, `References`, and `Research Achievements` are included in the table of contents manually.

---

## 日本語

### 概要

このリポジトリは、`ujreport` をベースにした英語修士論文用の LaTeX テンプレートです。
`uplatex + dvipdfmx` でのコンパイルを前提としており、表紙、Abstract、目次、本文、謝辞、参考文献、研究業績ページを含みます。

### ファイル構成

- `main.tex`: 論文全体のメインファイル
- `body.tex`: 本文の章・節を書くファイル
- `English_thesis.sty`: 表紙や体裁を定義するスタイルファイル
- `references.bib`: BibTeX の文献データベース
- `rm2c_junsrt.bst`: 参考文献スタイル
- `latexmkrc`: `latexmk` 用のビルド設定
- `figures/`: 図ファイルを置くディレクトリ
- `build/`: 中間生成物と PDF の出力先

### 必要環境

以下のコマンドが利用できる TeX 環境を用意してください。

- `uplatex`
- `dvipdfmx`
- `upbibtex`
- `latexmk`

TeX Live 環境での利用を想定しています。

### コンパイル方法

プロジェクトのルートで次のコマンドを実行してください。

```bash
latexmk -pdfdvi main.tex
```

生成された PDF は次に出力されます。

```text
build/main.pdf
```

補助ファイルのみ削除する場合:

```bash
latexmk -c
```

PDF を含めてほぼ全て削除する場合:

```bash
latexmk -C
```

### 論文の編集方法

#### 1. 論文情報の編集

`main.tex` 内の以下を編集してください。

- `\年度{...}`
- `\学位種別{...}`
- `\題目{...}`
- `\指導教員{...}`
- `\所属一行目{...}`
- `\所属二行目{...}`
- `\所属三行目{...}`
- `\学籍番号{...}`
- `\氏名{...}`

#### 2. Abstract の記入

`main.tex` の `abstract` 環境を編集します。

```tex
\begin{abstract}
...
\keywords{
...
}
\end{abstract}
```

#### 3. 本文の記入

章・節の本文は `body.tex` を編集してください。

例:

```tex
\chapter{Introduction}
\section{Background}
```

#### 4. 参考文献の管理

文献情報は `references.bib` に追加し、本文中で通常どおり引用してください。

参考文献出力は `main.tex` の以下で設定しています。

```tex
\bibliographystyle{rm2c_junsrt}
\bibliography{references}
```

一時的に参考文献出力を止めたい場合は、

```tex
\usebibliographytrue
```

を

```tex
\usebibliographyfalse
```

に変更してください。

#### 5. 謝辞

謝辞は `main.tex` の以下を編集してください。

```tex
\section*{Acknowledgements}
```

#### 6. 研究業績

研究業績は `main.tex` の以下を編集してください。

```tex
\section*{Research Achievements}
```

現在のテンプレートでは、研究業績は番号なしのリスト形式になっています。
自分の名前に下線を付けるには、次のコマンドを使えます。

```tex
\achievementauthor{Your Name}
```

例:

```tex
\item \achievementauthor{Your Name}, Coauthor, and Coauthor, ``Paper Title,'' ...
```

### 図の追加

図ファイルは `figures/` に置き、必要に応じて読み込んでください。

例:

```tex
\begin{figure}[t]
    \centering
    \includegraphics[width=0.8\linewidth]{figures/example.pdf}
    \caption{Example figure.}
    \label{fig:example}
\end{figure}
```

### 注意

- このテンプレートは英語論文向けに調整されています。
- 表紙のラベルや一部の体裁は `English_thesis.sty` で定義されています。
- `Acknowledgements`、`References`、`Research Achievements` は手動で目次に追加しています。
