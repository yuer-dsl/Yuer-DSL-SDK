# Yuer-DSL-SDK

Yuer-DSL-SDK is the official developer toolkit for **Yuer DSL**,\
the expression-driven decision language designed for cognitive AI
systems\
and positioned as the execution language of the **EDCA OS** ecosystem.

This SDK provides:

-   **DSL → JSON compiler**\
-   **Semantic signature generator**\
-   **Syntax validator**\
-   **Deterministic execution adapters**\
-   **CONTROL block + SIGNATURE block builder**\
-   **Runtime integration tools for EDCA-OS**

------------------------------------------------------------------------

## 🔷 1. Yuer DSL Overview

Yuer DSL is a next-generation expression-driven AI language designed
for:

-   Deterministic execution\
-   Semantic control\
-   Behavior orchestration\
-   Multi-layer cognitive chaining\
-   Verifiable signatures for audit & intent locking

All Yuer DSL files follow the standard structure:

``` yuer
YUER v1.0   AUTHOR: <name>   DATE: <iso8601>

INTENT: ...
SCOPE: ...
ANCHOR: [...]
RULE: ...
OUTPUT: ...

CONTROL:
    energy_budget: 1.8
    stability_lambda: 0.9
    flow_enabled: false

SIGNATURE: semantic_hash_v1
HASH: <auto_generated>
DECLARATION: >
  Official Yuer DSL Behavior Packet
```

The SDK provides all tools needed to **create, validate, sign, and
execute** DSL packets.

------------------------------------------------------------------------

## 🔷 2. SDK Modules

### **2.1 Compiler --- `dsl_compiler.py`**

Converts `.yuer` files into a normalized JSON representation:

``` json
{
  "intent": "...",
  "scope": "...",
  "anchor": ["..."],
  "rules": "...",
  "control": {...},
  "signature": {...}
}
```

Consumed by **EDCA OS**.

------------------------------------------------------------------------

### **2.2 Syntax Validator --- `validator.py`**

Validates:

-   Structural fields\
-   CONTROL constraints\
-   SIGNATURE block\
-   Indentation / YAML-like structure\
-   Semantic anchors

Returns deterministic pass/fail.

------------------------------------------------------------------------

### **2.3 Signature Generator --- `signature_gen.py`**

Generates semantic-level cryptographic hash based on:

-   anchors\
-   intent\
-   control values\
-   rules

Written into the `HASH:` field.

------------------------------------------------------------------------

### **2.4 Runtime Adapters --- `adapter_runtime.py`**

Connects compiled DSL packets to:

-   EDCA OS\
-   External agents\
-   Behavior executors\
-   Cognitive chains

Guarantees deterministic consistency.

------------------------------------------------------------------------

## 🔷 3. Developer Workflow

### **Step 1 --- Write your `.yuer` file**

``` yuer
INTENT: analyze market volatility
ANCHOR: [vol, trend]
RULE: >
  Use 5-day rolling variance combined with moving momentum.
```

### **Step 2 --- Validate**

``` bash
yuer validate example.yuer
```

### **Step 3 --- Compile**

``` bash
yuer compile example.yuer --out example.json
```

### **Step 4 --- Sign**

``` bash
yuer sign example.json
```

### **Step 5 --- Execute under EDCA OS**

``` bash
yuer run example.json
```

------------------------------------------------------------------------

## 🔷 4. Future Roadmap (v1 → v2)

-   Plugin architecture\
-   Type checker\
-   Inline semantic anchors\
-   Behavior Chain Compiler (BCC)\
-   Multi-agent adapter\
-   Runtime streaming executor

------------------------------------------------------------------------

## 🔷 5. License & Ethical Notes

The Yuer-DSL-SDK is published **without a license**, meaning:

-   All rights remain with the author\
-   Reuse or redistribution requires explicit permission\
-   Public read-only access ensures timestamp and originality proof

------------------------------------------------------------------------

## 🔷 6. Author

Created by **Yuer (管瑜)**\
Designer of **EDCA OS**, **Yuer DSL**, and the **Expression-Driven
Cognitive Architecture**.
