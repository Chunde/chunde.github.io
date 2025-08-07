---
layout: post  
title: x86 Assembly Interrupt Vector Check  
date: 2025-08-06 20:30:44  
description: Analysis of assembly code detecting interrupt vector tampering  
tags: assembly x86 reverse-engineering interrupts  
tabs: true  
---

This x86 assembly code snippet checks for potential tampering with interrupt vectors (specifically INT 1 and INT 3), which is a common technique used by debuggers like SoftICE. Here's the detailed breakdown:

1. **Loading IDT Address**:
   ```assembly
   mov eax, dword ptr [pIDT+2]  ; Load upper part of IDT base address
   ```
   - `pIDT` likely points to a structure containing the IDT (Interrupt Descriptor Table) address
   - `+2` offset suggests retrieving the high-order 32 bits of a 48-bit IDT base address

2. **Calculate INT 1 Vector Address**:
   ```assembly
   add eax, 8                  ; Each interrupt descriptor is 8 bytes
   ```
   - INT 1 (debug exception) is the second entry (after INT 0)
   - Adding 8 bytes (1 entry) to reach INT 1's descriptor

3. **Store INT 1 Handler**:
   ```assembly
   mov ebx, [eax]              ; Get first 4 bytes of INT 1 descriptor
   ```
   - Stores the low 32 bits of INT 1's handler address (offset + selector)

4. **Calculate INT 3 Vector Address**:
   ```assembly
   add eax, 16                 ; Skip INT 2 to reach INT 3 (8*2=16 bytes)
   ```
   - INT 3 (breakpoint) is the fourth entry
   - Adding 16 more bytes (2 entries) to reach INT 3's descriptor

5. **Store INT 3 Handler**:
   ```assembly
   mov eax, [eax]              ; Get first 4 bytes of INT 3 descriptor
   ```

6. **Extract Offsets**:
   ```assembly
   and eax, 0FFFFh             ; Mask to get handler offset (low 16 bits)
   and ebx, 0FFFFh             ; Same for INT 1
   ```
   - Isolates the offset parts of both interrupt handlers

7. **Calculate Distance**:
   ```assembly
   sub eax, ebx                ; Find displacement between handlers
   cmp eax, 10h                ; Compare with expected value (16 bytes)
   jne HackedVector            ; Jump if not equal
   ```
   - Checks if the distance between INT 1 and INT 3 handlers is exactly 16 bytes
   - If not, assumes tampering (e.g., by SoftICE debugger)

**Key Points**:
- The code assumes legitimate interrupt handlers will have a specific memory layout
- Debuggers often modify these vectors to insert their own handlers
- The check $$ \text{INT3\_offset} - \text{INT1\_offset} = 16 $$ is used as a fingerprint
- This is anti-debugging technique commonly seen in copy protection schemes