<!-- SPDX-License-Identifier: PMPL-1.0-or-later -->
<!-- (MPL-2.0 fallback in Project.toml for Julia ecosystem) -->
<!-- Copyright (c) 2026 Jonathan D.A. Jewell (hyperpolymath) <j.d.a.jewell@open.ac.uk> -->

# TOPOLOGY.md — FirmwareAudit.jl

## Purpose

Julia library for firmware integrity auditing and verification. Provides tools for checksumming, cryptographic verification, and detailed audit reporting on firmware images and system binaries.

## Module Map

```
FirmwareAudit.jl/
├── src/
│   ├── FirmwareAudit.jl        # Module entry point
│   ├── hashing.jl              # Checksum algorithms
│   ├── verification.jl         # Cryptographic verification
│   ├── audit.jl                # Audit report generation
│   └── ... (supporting modules)
├── test/
│   └── runtests.jl             # Test suite
├── Project.toml                # Julia package metadata
└── README.adoc                 # Documentation
```

## Data Flow

```
[Firmware Binary] ──► [Hash] ──► [Verify Against Known Good] ──► [Audit Report]
                        ↓                                              ↓
                   [Signature Verify]                         [Pass/Fail Determination]
```

## Key Invariants

- Uses Julia's multiple-dispatch for flexible hash/verification strategies
- Integrates with system crypto libraries (OpenSSL, etc.)
- Registered in HyperpolymathRegistry for Julia users
