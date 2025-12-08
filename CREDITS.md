# Credits & References

## autoPatch Community

**Author:** Cremané (saadrcaa@gmail.com)  
**License:** MIT License  
**Repository:** https://github.com/mathsaad/autopatch-community

---

## Third-Party Libraries & References

### C++ Core

| Library | License | Description | Link |
|---------|---------|-------------|------|
| **zlib** | zlib License | Compression library for GRF files | https://zlib.net/ |
| **nlohmann/json** | MIT | JSON parsing for C++ | https://github.com/nlohmann/json |
| **WinHTTP** | Microsoft | HTTP client for Windows | Built-in Windows API |
| **GDI+** | Microsoft | Graphics rendering | Built-in Windows API |
| **MSHTML/IWebBrowser2** | Microsoft | Embedded browser (IE) | Built-in Windows API |

### Electron Builder

| Library | License | Description | Link |
|---------|---------|-------------|------|
| **Electron** | MIT | Cross-platform desktop apps | https://electronjs.org/ |
| **Vue.js 3** | MIT | Frontend framework | https://vuejs.org/ |
| **Pinia** | MIT | State management for Vue | https://pinia.vuejs.org/ |
| **Tailwind CSS** | MIT | Utility-first CSS framework | https://tailwindcss.com/ |
| **TypeScript** | Apache 2.0 | Typed JavaScript | https://typescriptlang.org/ |
| **Vite** | MIT | Build tool | https://vite.dev/ |
| **electron-vite** | MIT | Electron + Vite integration | https://electron-vite.org/ |

---

## Technical References

### GRF File Format

The GRF (Gravity Resource File) format is a proprietary archive format used by Ragnarok Online.

**References:**
- OpenKore GRF Documentation: https://openkore.com/wiki/GRF
- grf.h from rAthena/Hercules projects
- GRF Editor by Tokeiburu: https://github.com/Tokeiburu/GRFEditor

**Key Implementation Details:**
- DES encryption for file entries (custom Gravity implementation)
- ZLIB compression for file data
- Entry table with filename hashing

### THOR Patch Format

THOR is a patch format designed for efficient Ragnarok Online client updates.

**References:**
- Thor Patcher by Ai4rei: http://nn.ai4rei.net/dev/thor/
- Thor format specification from community documentation

### Ragnarok Online Client

**References:**
- rAthena Project: https://github.com/rathena/rathena
- Hercules Project: https://github.com/HerculesWS/Hercules
- OpenKore: https://github.com/OpenKore/openkore

---

## Inspiration & Similar Projects

| Project | Description | Link |
|---------|-------------|------|
| **Thor Patcher** | Original THOR patcher by Ai4rei | http://nn.ai4rei.net/dev/thor/ |
| **GRF Editor** | GRF editing tool by Tokeiburu | https://github.com/Tokeiburu/GRFEditor |
| **rsu-client** | Rust-based RO client | https://github.com/Dooskington/rsu-client |
| **OpenRagnarok** | Open source RO client | Community projects |

---

## Contributors

- **Cremané** - Project creator and main developer
- Community contributors (see GitHub contributors page)

---

## Special Thanks

- The Ragnarok Online private server community
- rAthena and Hercules development teams
- All open-source contributors who made this project possible

---

## License Notices

### zlib License
```
Copyright (C) 1995-2024 Jean-loup Gailly and Mark Adler

This software is provided 'as-is', without any express or implied
warranty.  In no event will the authors be held liable for any damages
arising from the use of this software.

Permission is granted to anyone to use this software for any purpose,
including commercial applications, and to alter it and redistribute it
freely, subject to the following restrictions:

1. The origin of this software must not be misrepresented; you must not
   claim that you wrote the original software. If you use this software
   in a product, an acknowledgment in the product documentation would be
   appreciated but is not required.
2. Altered source versions must be plainly marked as such, and must not be
   misrepresented as being the original software.
3. This notice may not be removed or altered from any source distribution.
```

### MIT License (Vue.js, Electron, Pinia, Tailwind, etc.)
```
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
```
