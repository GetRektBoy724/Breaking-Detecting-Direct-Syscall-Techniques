# Breaking/Detecting Direct Syscall Techniques
This is a repository that filled with ideas to break/detect direct syscall techniques. Contribution is really appreciated.

- Dual-Loading NTDLL from disk 
  - Can be traced/detected from hooking NtMapViewOfSection.
  - Use IntrumentationCallback to detects syscalls and check if the return address is outside NTDLL.
- Manual-Mapping NTDLL from disk 
  - Can be traced/detected from hooking NtReadFile.
  - Use IntrumentationCallback to detects syscalls and check if the return address is outside NTDLL.
- Hell's Gate
  - Hook the NT functions.
- Halo's Gate / Tartarus Gate
  - Hook every single one of the NT function (the objective in here is to make Halo's Gate cant find ANY Syscall ID).
  - Use IntrumentationCallback to detects syscalls and check if the return address is outside NTDLL.
  - Use vaccinated-NTDLL from [SyscallShuffler](https://github.com/GetRektBoy724/SyscallShuffler).
- FreshyCalls / SysWhispers2 / "get syscall ID from sorting the syscall stub address"
  - Implant a modded-NTDLL where the Syscall ID doesnt correspond with the position of the syscall stub on memory.
  - Use IntrumentationCallback to detects syscalls and check if the return address is outside NTDLL.
  - Use vaccinated-NTDLL from [SyscallShuffler](https://github.com/GetRektBoy724/SyscallShuffler).
- SysWhispers1 / "include your own syscall stub on your program"
  - Use IntrumentationCallback to detects syscalls and check if the return address is outside NTDLL.
  - Detect syscall instruction inside PEs

### “Nothing is perfect, nothing is imperfect. Perfection and imperfection reside in your perception.” 

# Sources
- https://www.cyberbit.com/blog/endpoint-security/malware-mitigation-when-direct-system-calls-are-used/
- https://www.mdsec.co.uk/2020/12/bypassing-user-mode-hooks-and-direct-invocation-of-system-calls-for-red-teams/
- https://alice.climent-pommeret.red/posts/direct-syscalls-hells-halos-syswhispers2/
- https://outflank.nl/blog/2019/06/19/red-team-tactics-combining-direct-system-calls-and-srdi-to-bypass-av-edr/
