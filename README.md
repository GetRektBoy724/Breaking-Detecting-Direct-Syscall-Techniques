# Breaking/Detecting Direct Syscall Techniques
This is a repository that filled with ideas to break/detect direct syscall techniques. Contribution is really appreciated.

- Dual-Loading NTDLL from disk 
  - Can be traced/detected from hooking NtMapViewOfSection.
- Manual-Mapping NTDLL from disk 
  - Can be traced/detected from hooking NtReadFile.
- Hell's Gate
  - Hook the NT functions.
- Halo's Gate 
  - Hook every single one of the NT function (the objective in here is to make Halo's Gate cant find ANY Syscall ID).
- FreshyCalls / SysWhispers2 / "get syscall ID from sorting the syscall stub address"
  - Implant a modded-NTDLL where the Syscall ID doesnt correspond with the position of the syscall stub on memory.
- SysWhispers1 / "include your own syscall stub on your program"
  - Use IntrumentationCallback to detects syscalls and check if the return address is outside NTDLL.

### “Nothing is perfect, nothing is imperfect. Perfection and imperfection reside in your perception.” 
