# Latex Guide

LaTeX is a powerful typesetting system widely used for writing complex mathematical equations and scientific documents mostly. Its syntax allows users to easily create formulas, matrices, integrals, and various other mathematical structures.

Here's a **complete guide** on using **LaTeX for writing math** but not as a whole:

To write mathematics in LaTeX, you need to enter **math mode**. There are two common ways to do this:
- **Inline math mode**: Write math inside single dollar signs (`$`).
- **Display math mode**: Write math inside double dollar signs (`$$`) or `\[ \]`.


---

## Superscripts and Subscripts

- **Superscripts**: Use the caret `^` example, $x^2$ ,
- **Subscripts**: Use the underscore `_` example, $a_1$ 


> [!info] For multiple characters in superscripts or subscripts, wrap them in curly braces `{}`.
$x^{n+1}$ , $a_{ij}$ 

## Fractions

Use the `\frac{numerator}{denominator}` command for fractions.
$$\frac{x^2 + y^2}{z^2 + w^2}$$

##  Square Roots and N<sup>th</sup> Roots

- **Square Root**: Use the `\sqrt` command. $\sqrt{x}$  is an example
- **N<sup><b>th</b></sup> Root**: Use `\sqrt[n]{}`. $\sqrt[3]{x}$  is an example 

---

## Greek Letters

LaTeX provides commands for Greek letters ($\alpha + \beta = \gamma$ ):

| Greek Letter | LaTeX Code | Greek Letter | LaTeX Code |
| ------------ | ---------- | ------------ | ---------- |
| Alpha        | `\alpha`   | Beta         | `\beta`    |
| Gamma        | `\gamma`   | Delta        | `\delta`   |
| Epsilon      | `\epsilon` | Zeta         | `\zeta`    |
| Theta        | `\theta`   | Lambda       | `\lambda`  |
| Pi           | `\pi`      | Sigma        | `\sigma`   |
| Omega        | `\omega`   | Phi          | `\phi`     |

---
## Sums, Products and Integrals

- Use `\sum` for summation ($\sum_{n=1}^{\infty} \frac{1}{n^2}$), `\prod` for product notation ( $\prod_{i=1}^{n} i$ ) and `\int` for integrals ($\int_0^1 x^2 \, dx$ ). For double and triple integrals, use `\iint` and `\iiint` $\iint \limits_D f(x,y) \,dx\,dy$.
- Add limits in `{}` using superscripts and subscripts..
## Matrices and Binomials

You can write matrices using the `matrix`, `pmatrix` (for parentheses), `bmatrix` (for square brackets), or `vmatrix` (for vertical bars) environments. Separate elements by `&` to align the rows and columns in a single line and change rows with `\\`

$$
\begin{pmatrix}
  a & b \\
  c & d
\end{pmatrix}
$$

Use `/binom{n}{k}` to type binomials like $\binom{n}{k} = \frac{n!}{k!(n-k)!}$

---
## Common Functions

LaTeX provides built-in commands for many common mathematical functions. Some of the most frequently used functions include:

- **Trigonometric Functions**: `\sin`, `\cos`, `\tan`, `\csc`, `\sec`, `\cot`
- **Logarithmic and Exponential**: `\log`, `\ln`, `\exp`
- **Miscellaneous**: `\max`, `\min`, `\lim`, `\sup`, `\inf`, `\det`

$\lim_{x \to 0} \frac{\sin (\ln (\cot (e^x)))}{x}$

## Aligning Equations

For aligning multiple equations, use the `align` environment.

$$\begin{align*}
  x + y &= z \\
  x - y &= w
\end{align*}$$
- `&` specifies where the equations align.
- Use `\\` to separate lines.

---

## Delimiters and Parentheses

### Basic Delimiters:
- Parentheses: `()`
- Square brackets: `[]`
- Braces: `\{ \}`
- Absolute value: `| |`
- Floor: `\lfloor \rfloor`
- Ceiling: `\lceil \rceil`
 
You can adjust the size of parentheses, brackets, braces, etc., using `/small`, `\big`, `\bigg`, `\bigg` to match the size of the content inside them. Like - 

$$\left( \small(\big( \bigg( \Bigg( \right)$$
$$f(x) = \Big( \frac{a}{b+c} \Bigg)$$


### Auto-Sized Delimiters:
Use `\left` and `\right` to make delimiters auto-size based on the content. $\left( \frac{a+b}{c+d} \right)$

---

## Special Symbols

### Infinity, Empty Set, and More
- Infinity ($\infty$): `\infty`
- Empty set ($\emptyset$): `\emptyset`
- Subset ($\subseteq$): `\subseteq`
- Superset ($\supseteq4): `\supseteq`
- Union ($\cup$): `\cup`
- Intersection ($\cap$): `\cap`

### Arrows
- Right arrow ($x \rightarrow y$ ): `\rightarrow`
- Left arrow($x \leftarrow y$ ):: `\leftarrow`
- Double right arrow($x \Rightarrow y$ ):: `\Rightarrow`

---

## Advanced Features

### Piecewise Functions

Use the `cases` environment for piecewise-defined functions.

$$
f(x) =
\begin{cases}
  x^2 & \text{if } x \geq 0 \\
  -x^2 & \text{if } x < 0
\end{cases}
$$
### Accents and Decorations

- Hat ($\hat{x}$): `\hat{x}`
- Bar ($\overline{x}$): `\overline{x}`
- Tilde ($\tilde{x}$) : `\tilde{x}`
---
