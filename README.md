# WASI Rule Engine Host

A Rust-based **Rule Engine CLI tool** that loads and runs sandboxed **WASI plugins** to evaluate serverless rules dynamically. This project showcases secure, portable plugin execution powered entirely by Rust and WASI.

---

## Features

- Written entirely in **Rust**
- Safe, **sandboxed plugin execution** using WASI
- Accepts input via **JSON**
- Plugins are compiled to `.wasm` and loaded dynamically
- Cross-platform with no external dependencies
- Extendable: Add new rule plugins as `.wasm` files

---

## Input Format (via stdin)

Each plugin receives structured input in JSON format.

```json
{
  "event_type": "payment",
  "amount": 6000,
  "currency": "USD"
}
```

---

## Plugin Output (via stdout)

Plugins output evaluation results to stdout in JSON.

```json
{
  "result": "alert",
  "reason": "Amount exceeds threshold"
}
```

---

## Use Cases

- Fraud detection rules
- Real-time filtering
- Feature flag checks
- Dynamic pricing logic
- A/B testing workflows

---

## Security

- Runs plugins in a **WASI sandbox**
- No filesystem or network access by default
- Can limit memory, CPU, and execution time

---

## Technologies

- Rust
- WASI
- Wasmtime or Wasmer
- serde / serde\_json
- clap (command-line interface)

---

## Example Plugins

- Flag high transaction amount
- Block users under age 18
- Match rules based on location or event type

---

## License

This project is licensed under the MIT License. See the LICENSE file for details.

