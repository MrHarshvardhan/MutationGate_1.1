# MutationGate
Use hardware breakpoint to dynamically change SSN in run-time


## MutationGate.c
Assume NTAPI `NtDrawText` is not hooked, while NTAPI `NtQueryInformationProcess` is hooked

Set a hardware breakpoint at NtDrawText+0x8, when the address is reached, modify RAX with NtQueryInformationProcess' Syscall Number. In this way, though the program reached NtDrawText address, SSN is changed, the syscall of NtQueryInformationProcess is transited.
