<!-- README BADGE BLOCK : CID POINTER SYSTEM -->

![CID-STATUS](https://img.shields.io/badge/CID--STATUS-VALID-4caf50)
![CHECKSUM](https://img.shields.io/badge/SHA256-VERIFIED-2196f3)
![POINTER-ALIGNMENT](https://img.shields.io/badge/POINTER--ALIGNMENT-SYNCHRONIZED-9c27b0)
![REALM-SCOPE](https://img.shields.io/badge/REALM--SCOPE-TRI--REALM-ff9800)
![NON-INTERACTIVE](https://img.shields.io/badge/VERIFICATION-NON--INTERACTIVE-607d8b)
![OFFLINE-CAPABLE](https://img.shields.io/badge/OFFLINE-CAPABLE-795548)
![NON-DERIVATIVE](https://img.shields.io/badge/MODE-NON--DERIVATIVE-f44336)

---

# Badge Block Overview
The badge block provides a quick visual summary of the verification state,
pointer alignment status, and operational characteristics of the CID Pointer
Alignment System. All badges are static, non-interactive, and reflect the
deterministic properties of the registry-bound verification suite.

## Badge Definitions
- **CID-STATUS** — Indicates whether the canonical CID is valid and recognized.  
- **CHECKSUM** — Confirms the SHA‑256 checksum matches the declared value.  
- **POINTER-ALIGNMENT** — Shows whether ROOT, CODEX, and DEMO pointers are synchronized.  
- **REALM-SCOPE** — Identifies the multi-realm coverage of the pointer block.  
- **NON-INTERACTIVE** — Indicates that verification requires no challenge–response.  
- **OFFLINE-CAPABLE** — Confirms that verification can be performed without network access.  
- **NON-DERIVATIVE** — Indicates the block cannot be modified or extended.  

## Placement
Place the badge block at the top of the repository README, directly under the
main title, to provide immediate visibility into the verification characteristics
of the CID Pointer Alignment System.

---

# CID POINTER BLOCK & CID‑ONLY VERIFICATION STUB
This repository contains two core components of the registry‑bound verification
architecture:

1. **CID Pointer Block** — defines realm‑separated pointer alignment for ROOT,
   CODEX, and DEMO verification stubs.  
2. **CID‑Only Verification Stub** — provides a minimal, deterministic, offline
   verification artifact for a single immutable content‑addressed payload.

Both components are non‑interactive, non‑derivative, and fully offline‑capable.

---

## 1. CID POINTER BLOCK FORMAT

### Purpose
The CID Pointer Block ensures that all realm‑separated verification stubs resolve
to the same canonical CID and checksum. It enforces pointer uniformity, prevents
drift, and maintains deterministic verification across ROOT, CODEX, and DEMO.

### File Location
`/pointer-alignment/pointer-alignment-block.trirealm.txt`

### Structure
The Pointer Block includes:

- **Header Fields** — version, realm scope, role, type, encoding  
- **Primary Identifiers** — canonical CID and SHA‑256 checksum  
- **Realm Pointers** — file names, paths, and target CIDs  
- **Alignment Rules** — CID uniformity, checksum uniformity, file name consistency, realm separation  
- **Integrity Mode** — content‑addressed, zero variance, permanent finality  

### Verification Behavior
The Pointer Block defines alignment rules but does not perform verification.

Verification consists of:

1. Reading the realm’s verification stub  
2. Computing SHA‑256  
3. Comparing to the primary checksum  
4. Confirming CID matches the primary CID  

If both match → **valid**  
If either fails → **invalid**

---

## 2. CID‑ONLY VERIFICATION STUB FORMAT

### Purpose
The CID‑Only Verification Stub provides a minimal, self‑contained artifact for
verifying a single immutable content‑addressed payload. It contains only the
identifiers required for deterministic validation.

### File Location
`/verification/cid-only/imperi-berit-suite-001--CID-STUB.txt`

### Structure
The stub includes:

- **Header Fields** — payload metadata, realm, role, type, encoding  
- **Integrity Anchor** — CID, checksum, content‑addressed mode, zero variance  
- **Verification Block** — non‑interactive, non‑derivative, offline‑capable  
- **JSON Summary** — machine‑readable verification output  

### Verification Properties
- **NON‑INTERACTIVE** — No challenge–response  
- **OFFLINE‑CAPABLE** — No network access required  
- **CONTENT‑ADDRESSED** — Integrity derived from CID and checksum  
- **NON‑DERIVATIVE** — Cannot be modified or extended  
- **DETERMINISTIC** — Same input always yields same result  

### Verification Steps
1. Read the stub  
2. Compute SHA‑256 of the canonical content  
3. Compare to declared checksum  
4. Confirm CID matches  
5. Output: `valid` or `invalid`

---

## 3. Relationship Between Components

### CID Pointer Block → defines alignment  
### CID‑Only Stub → performs verification  

The Pointer Block ensures that all realm‑separated stubs reference the same
canonical CID and checksum.  
The CID‑Only Stub provides the actual verification mechanism.

Both must remain synchronized.

---

## 4. Associated Files

### Pointer Block
- `/pointer-alignment/pointer-alignment-block.trirealm.txt`

### Realm‑Separated Verification Stubs
- `/root/registry/root-registry-payload-imperi-berit-suite-001--CID-STUB.txt`  
- `/codex/registry/codex-registry-payload-imperi-berit-suite-001--CID-STUB.txt`  
- `/demo/registry/demo-registry-payload-imperi-berit-suite-001--CID-STUB.txt`  

### CID‑Only Stub
- `/verification/cid-only/imperi-berit-suite-001--CID-STUB.txt`

All must resolve to the same CID and checksum.

---

## 5. Operational Characteristics
- Offline verification  
- Zero external dependencies  
- No challenge–response  
- Content‑addressed integrity  
- Permanent finality  
- Realm‑separated but CID‑aligned  

---

## 6. Status
All components are static, final, and non‑derivative.  
Successors must be explicitly declared through a registry‑bound successor record.

---
