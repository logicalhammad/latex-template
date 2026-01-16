# 📘 Final Year Project LaTeX Template

Follow this template to create your Final Year Project (FYP) in LaTeX **without needing to learn LaTeX first**.

📌 **Important:**
Read this document from start to end.
This will be the **only thing you need** to understand and use LaTeX with this template.

---

## ✨ What is LaTeX?

LaTeX is a tool used to write documents, especially:
* Research papers
* Theses
* Books
* Technical reports
* And FYP reports like this one 😃📚

Instead of clicking buttons like in Word, you **write text and commands**, and LaTeX turns it into a beautiful, professional PDF.

---

## 🔥 Why use LaTeX?

Here are some benefits:
* 📄 **Perfect formatting** automatically
* 📚 **Best for long documents** (like FYPs and theses)
* 🔢 **Great for equations, tables, and references**
* 🧠 **No formatting headache**, you focus only on content
* 🎓 Standard for academic and technical writing

---

## � Nature of LaTeX Basics
Before you start, here are 4 simple rules to understand how LaTeX works:

1.  **Commands start with a backslash (`\`)**
    *   Examples: `\chapter`, `\section`, `\textbf` (bold), `\textit` (italic).
2.  **Arguments go inside curly braces `{...}`**
    *   Example: `\chapter{Introduction}` creates a chapter named "Introduction".
    *   Example: `\textbf{This is bold}` makes the text inside bold.
3.  **Environments start and end**
    *   Blocks of complex content (like tables or figures) start with `\begin{name}` and end with `\end{name}`.
4.  **Files end in `.tex`**
    *   Your source code lives in `.tex` files.
    *   **⚠️ Important:** When you build the PDF, LaTeX creates many "junk" files (`.aux`, `.log`, `.toc`, etc.). **Do not touch or open them.** They are automatically handled by the system.


---

## �🛠 How to Install and Use This Template

### Step 1: Install LaTeX on Windows
Download and install:
* [**TeX Live**](https://www.tug.org/texlive/) (Recommended) or **MiKTeX**

### Step 2: Install VS Code
Download and install:
* [**Visual Studio Code (VS Code)**](https://code.visualstudio.com/)

### Step 3: Open This Project in VS Code
1. Open VS Code
2. Click **File → Open Folder**
3. Select this project folder

### Step 4: Install Required Extensions
In VS Code, search specifically for and install:
* **LaTeX Workshop**

### Step 5: Build the PDF
1. Open the file `main.tex`
2. Click the **Play** button (Build LaTeX project) in the top right, or press `Ctrl + Alt + B`
3. A PDF file will be generated in the root folder
4. You can view the PDF inside VS Code
5. Changes appear in **real time** upon saving (`Ctrl + S`) 🎯

> **Note:** You might see an error/warning in `Chapter 2` related to layout. Please **IGNORE** this error. The PDF builds perfectly fine without any problems.

---

## 📂 How This Template is Organized

This is how your project folder looks:

```
Report/
├── chapters/       # Your main content (Introduction, Literature Review, etc.)
├── endmatter/      # Bibliography, Plagiarism Report, etc.
├── figures/        # Images organized by chapter
├── frontmatter/    # Title page, Declaration, Abstract, etc.
├── tables/         # Custom table templates and config
├── main.tex        # The master file (Don't edit this)
├── preamble.tex    # Settings and packages (Don't edit this)
├── references.bib  # Your citations
└── README.md       # This guide
```

### 🧠 Main Files
* `main.tex`: The master file that connects everything.
* `preamble.tex`: Contains all style definitions and packages.

👉 **Do not edit these files** unless you know what you are doing. They are already configured for the university format.

---

### 📝 Writing Your Content

#### 1️⃣ Front Matter
Go to the **`frontmatter`** folder.
Fill in these files:
* `titlepage.tex` (Project title, names, supervisors)
* `declaration.tex`
* `dedication.tex`
* `acknowledgements.tex`
* `executive_summary.tex`

👉 Replace the placeholder text with your own.

#### 2️⃣ Chapters
Go to the **`chapters`** folder.
Start writing your content in:
* `chapter1.tex` (Introduction)
* `chapter2.tex` (Requirements Specification and Analysis)
* ...
* `chapter6.tex` (Software Deployment)

👉 Write your full project here.

#### 📌 Headings Guide (Don't forget the curly braces `{}`)
* `\chapter{Your Chapter Title}` = **Heading 1** (Starts on a new page)
* `\section{Your Section Title}` = **Heading 2**
* `\subsection{Your Subsection Title}` = **Heading 3**

> **Tip:** If you need a new heading style (e.g., Heading 4), ask an AI tool: *"Generate LaTeX code for a 4th level heading style and tell me where to put it in preamble.tex"*. Then paste it into `preamble.tex`.

---

### 🖼 Figures (Images)

* All figures go inside the **`figures`** folder.
* Organize them by chapter, e.g., `figures/chapter1/`, `figures/chapter2/`.

#### 📌 Figure Template (Paste where needed)

```latex
% --- FIGURE ---
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{figures/chapter1/your_image.png} 
    \caption{Your figure caption here}
    \label{fig:unique_label_name}
\end{figure}
```
- Replace path with your image location
- Change width as needed (0.5 - 1.0 is standard)

#### 🔗 Referencing a Figure in Text
The text inside the \label{ } is used to reference the figure in the text, however this text is not visible in the document.

```latex
As shown in Figure~\ref{fig:unique_label_name}, note that captions are grey and italicized automatically, and the numbering is automatic...
```

---

### 📊 Tables (Modern Style)

We have created a custom **Modern Table** style for this project.

#### 📌 Modern Table Template (Paste where needed)

```latex
% --- MODERN TABLE TEMPLATE ---
\begin{table}[H]
    \centering
    \setModernTableStyle % Applies the custom grey/white theme
    
    % defined columns: |l|X|c| -> Left fixed, Auto-expand, Center fixed
    \begin{tabularx}{\textwidth}{|l|X|c|}
        \hline
        % Header Row: Use \tableHeaderStyle
        \tableHeaderStyle Parameters & Description & Value \\ \thickhline
        
        % Data Rows
        Voltage & Operating voltage of the component & 5V \\ \hline
        Current & Max current draw & 2A  \\ \hline
        Status  & Component state & Active \\ \hline
    \end{tabularx}
    
    \caption{Description of the modern table}
    \label{tab:my_table}
\end{table}
```

* Only use `\setModernTableStyle` inside the table environment.
* Use `\tableHeaderStyle` for the header row.
* Use `\thickhline` after the header for a professional look.

> **Understanding Tables:**
> Tables can look confusing in code!
> * Columns are separated by the **`&`** symbol.
> * Rows end with **`\\`** (double backslash).
> * The `tabularx` environment helps columns auto-fit the page width.

#### 🔗 Referencing a Table in Text
```latex
See Table~\ref{tab:my_table} for the exact specifications.
```

---

### 📚 References (Citations)

All references are stored in `references.bib`.
This template uses **IEEE style** automatically.

#### 📌 Reference Template (Paste inside `references.bib`)

```bibtex
% Book
@book{book_key,
  author    = {John Smith},
  title     = {The Future of AI},
  publisher = {Tech Press},
  year      = {2023}
}

% Website
@online{web_key,
  author = {OpenAI},
  title  = {ChatGPT Documentation},
  year   = {2024},
  url    = {https://openai.com/chatgpt}
}

% Conference Paper (Most Used)
@inproceedings{paper_key,
  author    = {Alice Doe and Bob Lee},
  title     = {Novel sorting algorithms},
  booktitle = {Proceedings of the IEEE Conference on Computing},
  year      = {2022},
  pages     = {45--50}
}
```

> **What is `book_key` / `web_key`?**
> This is a **unique nickname** for the reference. It is **NOT** shown in the final text. You use it only to tell LaTeX which reference to pick (e.g., `\cite{book_key}`).

#### 🔗 Citing in Your Text
```latex
This algorithm was proposed by \cite{unique_key}.
```

---

## 🧱 Other Features

* **Code Snippets**: Use `lstlisting` for code.
* **Math**: Use standard math environments like `\begin{equation} ... \end{equation}`.
* **Spacing**: Paragraphs and lines are already spaced according to university guidelines.

## 🛡️ Save Your Work (Git)
We highly recommend using **Git** to track your changes.
*   **Where to put this:** You can place this wherever you like, but we recommend placing this entire folder inside your project repo, e.g., `MyProject/docs/report/`.
*   **Why?** If you break something or delete a chapter by mistake, Git allows you to "undo" and go back to a working version. It saves you from disasters!
*   **What to commit:** Only commit the `.tex` files, `.bib` files, figures, and this README. **Ignore** the generated PDF and junk files (the `.gitignore` file provided here is already set up for this).

## ✅ Workflow Checklist

1. [  ] Install LaTeX & VS Code.
2. [  ] Fill out the `frontmatter` files.
3. [  ] Put your images in `figures/`.
4. [  ] Write your chapters in `chapters/`.
5. [  ] Add your references to `references.bib`.
6. [  ] Build `main.tex` and celebrate! 🎉
