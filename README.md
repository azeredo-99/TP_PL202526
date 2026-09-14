# LFun Language Interpreter

A lexer, parser and evaluator for **LFun**, a small functional language, built incrementally in four stages: tokenizing, a basic grammar, a full grammar with functions and conditionals, and finally a complete evaluator with pattern matching.

## Stages

| Stage | What it adds | Key files |
|---|---|---|
| [A — Lexer](./A/) | Tokenizes reserved words, operators and literals; line (`--`) and block (`{- -}`) comments | `lfun_lexer.py` |
| [B — Basic grammar](./B/) | Arithmetic/boolean expressions, `let` bindings, first AST nodes | `lfun_grammar.py`, `ast_nodes.py` |
| [C — Full grammar](./C/) | Function signatures/definitions, conditionals, function calls | adds `IfExpr`, `CallExpr`, `FunDef` |
| [D — Evaluator](./D/) | A decoupled evaluator (`eval.py`) over the full AST, plus pattern matching | `eval.py`, `main.py` (REPL + file runner) |

## Language features

- Integers and booleans, arithmetic/relational/logical operators
- Variable and function definitions with type signatures (`fun f : Int -> Bool`)
- Conditionals (`if E then E else E`)
- Pattern matching (`when (expr) is ... end`) with literal cases, multiple alternatives, wildcards and variable capture

## Tech stack

Python 3 · PLY (Python Lex-Yacc)

## Running

```bash
cd D
python main.py              # interactive REPL
python main.py ex1.lfun     # run a source file
python test_eval.py         # run the evaluator test suite
```

Earlier stages can be exercised the same way from `A/`, `B/` and `C/` with their respective `*_test.py`.

## Authors

Built with a small team: Guilherme Azeredo, Rodrigo Pinheiro and Leonardo — [GitHub](https://github.com/azeredo-99)
