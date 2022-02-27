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
- Halo's Gate 
  - Hook every single one of the NT function (the objective in here is to make Halo's Gate cant find ANY Syscall ID).
  - Use IntrumentationCallback to detects syscalls and check if the return address is outside NTDLL.
- FreshyCalls / SysWhispers2 / "get syscall ID from sorting the syscall stub address"
  - Implant a modded-NTDLL where the Syscall ID doesnt correspond with the position of the syscall stub on memory.
  - Use IntrumentationCallback to detects syscalls and check if the return address is outside NTDLL.
- SysWhispers1 / "include your own syscall stub on your program"
  - Use IntrumentationCallback to detects syscalls and check if the return address is outside NTDLL.
  - Detect syscall instruction inside PEs

### “Nothing is perfect, nothing is imperfect. Perfection and imperfection reside in your perception.” 
