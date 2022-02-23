# Breaking-Monitoring-Direct-Syscall-Techniques
This is a repository that filled with my ideas to break/detect direct syscall technqiues.

# Ideas
- Dual-Loading NTDLL from disk 
  - Can be traced/detected from hooking NtMapViewOfSection
- Manual-Mapping NTDLL from disk 
  - Can be traced/detected from hooking NtReadFile
- Hell's Gate
  - Hook the NT/ZW functions
- Halo's Gate 
  - Hook every single one of the NT/ZW function (the objective in here is to make Halo's gate cant find ANY Syscall ID)
- FreshyCalls / SysWhispers2 / "get syscall ID from sorting the syscall stub address"
  - Implant (to the whole system) a modded-NTDLL where the Syscall ID doesnt correspond with the position of the syscall stub on memory
