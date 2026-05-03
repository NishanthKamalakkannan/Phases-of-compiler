<div align="center">
<br />
<h1>⚙️ Compiler Phases Explorer</h1>
<p>A visual, interactive journey through the internals of a compiler</p>
<br />

![App Screenshot 1](docs/image%20(1).png)
&nbsp;
![App Screenshot 2](docs/image%20(2).jpg)
&nbsp;
![App Screenshot 3](docs/image%20(3).jpg)

<br />

<p>Type source code. Watch it compile. Understand every step.</p>
<p>An educational tool that visualizes all 7 phases of a compiler — live, in the browser, with zero setup.</p>

<br />

</div>

## 📌 Overview
**Compiler Phases Explorer** is a browser-based interactive application that walks you through the complete lifecycle of source code compilation — from raw characters to machine-level instructions — in real time.

Designed as an educational tool for students studying Compiler Design, Principles of Programming Languages, or Systems Programming, this project makes abstract compiler concepts tangible and visual.

**No installation. No dependencies. No build step. Just open and learn.**

## 🌐 Live Deployment
🔗 [https://phases-of-compiler.vercel.app/](https://phases-of-compiler.vercel.app/)

Deployed on Vercel — accessible from any device with a modern browser.

## 🎬 How It Works
1.  **Type or paste** C-like source code in the left panel.
2.  Click **"Run All Phases"** to trigger the full compilation pipeline.
3.  **Switch between phase tabs** to inspect each stage of the process.
4.  Try **built-in samples** — Basic Assignment, While Loop, Function Call, or Error Code.

Every phase updates instantly and independently, letting you explore how the compiler transforms your input at each step.

## 🔬 Compiler Phases

| Phase | Name | What Happens |
| :--- | :--- | :--- |
| 01 | 🔡 Lexical Analysis | Source code is scanned character-by-character and broken into classified tokens — keywords, identifiers, operators, literals, and punctuation. |
| 02 | 🌳 Syntax Analysis | Tokens are organized into an Abstract Syntax Tree (AST) based on the language grammar, verifying structural correctness. |
| 03 | 🔍 Semantic Analysis | The AST is checked for meaning — type compatibility, variable declaration order, scope resolution, and usage errors. |
| 04 | 📋 IR Generation | A language-independent Three-Address Code (TAC) intermediate representation is produced, decoupling the front end from the back end. |
| 05 | ⚡ Code Optimization | The IR is improved through constant folding, dead code elimination, and copy propagation to produce faster, leaner code. |
| 06 | 💻 Code Generation | Optimized IR is translated into x86-like assembly instructions (MOV, ADD, IMUL, IDIV) for the target architecture. |
| 07 | 📊 Symbol Table | A persistent lookup structure tracking every identifier's name, type, scope, memory address, and size across all phases. |

## ✨ Features
*   **Zero-setup** — single HTML file, runs entirely in the browser.
*   **Real-time pipeline** — all 7 phases execute on every run.
*   **Color-coded token visualization** — distinct styles per token class.
*   **Live AST rendering** — tree structure drawn inline from parsed output.
*   **Semantic error detection** — catches type mismatches, undeclared variables, and redeclarations.
*   **TAC intermediate code** — clean, readable three-address representation.
*   **Constant folding** — optimizer annotates which expressions were evaluated at compile time.
*   **Assembly output** — fully formed .data + .code section structure.
*   **Symbol table** — simulated memory addresses with type and size metadata.
*   **Built-in sample programs** — instantly loadable test cases including an error-prone snippet.
*   **Responsive dark UI** — works across desktop and tablet screens.

## 🧪 Sample Inputs
### Variable Declaration & Arithmetic
```c
int x = 5 + 3;
float y = x * 2.0;
if (x > 4) {
  y = y + 1;
}
```

### While Loop
```c
int i = 0;
while (i < 5) {
  i = i + 1;
}
```

### Function Result Assignment
```c
int result;
result = add(3, 4);
int x = result * 2;
```

### Semantic Error Detection
```c
int x = "hello";   // ❌ Type mismatch: string assigned to int
float y = x +;     // ❌ Incomplete expression
```

## 🗂️ Project Structure
```text
compiler-phases-explorer/
│
├── index.html          # Complete application — HTML + CSS + JS in one file
└── docs/               # Screenshots and documentation assets
```
The entire tool is intentionally self-contained in a single file for maximum portability, shareability, and ease of deployment.

## 🧠 Technical Implementation
The compiler pipeline is implemented in vanilla JavaScript with no external libraries:

| Component | Implementation |
| :--- | :--- |
| **Lexer** | Hand-written character scanner supporting keywords, identifiers, numbers, strings, operators, and punctuation with multi-character operator lookahead. |
| **Parser** | Recursive descent parser constructing a simplified AST for declarations, assignments, conditionals, and loops. |
| **Semantic Checker** | Symbol map–based checker tracking declared variables, detecting redeclarations, undeclared references, and type mismatches. |
| **IR Generator** | AST walker emitting three-address code with auto-generated temporaries (t1, t2, ...). |
| **Optimizer** | Pattern-matching pass for constant folding with inline annotation of folded expressions. |
| **Code Generator** | IR-to-assembly mapper producing .data declarations and .code instruction sequences. |
| **Symbol Table** | AST-derived table with simulated base address allocation and type-aware size computation. |

## 📚 Concepts Demonstrated
This project is ideal for understanding:
*   The distinction between lexemes, tokens, and patterns.
*   How a parse tree differs from an Abstract Syntax Tree.
*   Why semantic analysis is a separate phase from parsing.
*   The role of intermediate representations in compiler portability.
*   How constant folding reduces runtime computation.
*   The structure of assembly output and the .data / .code convention.
*   How symbol tables persist information across all compilation phases.

## 🚀 Deployment
This project is deployed on Vercel via automatic GitHub integration.

### To deploy your own fork:
1.  **Fork this repository.**
2.  Import into Vercel at [vercel.com/import](https://vercel.com/import).
3.  Vercel auto-detects static HTML — no configuration needed.
4.  Your live URL is ready in under 60 seconds.

### To run locally:
```bash
git clone https://github.com/your-username/compiler-phases-explorer.git
cd compiler-phases-explorer

# Option A — Open directly
open index.html

# Option B — Serve with Python
python -m http.server 8000
# Then visit: http://localhost:8000
```

## 🗺️ Roadmap
- [ ] Step-by-step animation mode with phase-by-phase reveal
- [ ] Support for functions, arrays, and return statements
- [ ] Export AST as downloadable JSON
- [ ] Multiple error reporting with line and column markers
- [ ] Additional optimization passes (CSE, loop unrolling)
- [ ] Syntax highlighting in the source code input panel
- [ ] Light theme variant

## 🎓 Academic Context
Developed as part of a Compiler Design college project to demonstrate the end-to-end compilation process visually. Suitable for:
*   Viva voce and lab demonstrations.
*   Course submissions and practicals.
*   Teaching aids in CS / IT undergraduate programs.
*   Self-study and concept reinforcement.

<div align="center">
<br />
⭐ Star this repo if you found it useful — it helps others discover it too.
<br />
<b>Understanding compilers, one phase at a time.</b>
</div>
