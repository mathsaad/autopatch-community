# AutoPatch Community

<p align="center">
  <img src="electron-builder/build/icon.png" alt="AutoPatch Logo" width="128" height="128">
</p>

<p align="center">
  <strong>Um sistema completo de autopatcher para Ragnarok Online</strong><br>
  Builder visual moderno + Patcher nativo leve com configuração embutida no EXE
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Electron-38.x-47848F?logo=electron" alt="Electron">
  <img src="https://img.shields.io/badge/Vue.js-3.5-4FC08D?logo=vue.js" alt="Vue.js">
  <img src="https://img.shields.io/badge/C++-17-00599C?logo=cplusplus" alt="C++17">
  <img src="https://img.shields.io/badge/Windows-7%2F8%2F10%2F11-0078D6?logo=windows" alt="Windows">
</p>

---

## ✨ Características

- 🎨 **Builder Visual Moderno** - Interface drag-and-drop para criar patchers customizados
- 📦 **Configuração Embutida** - Tudo no EXE, sem arquivos externos (INI/JSON)
- 🖼️ **UI Customizável** - Imagem de fundo, botões, labels, WebViews e mais
- 🎬 **Vídeo de Fundo** - Suporte a vídeo MP4 como background animado
- 🔄 **Formatos de Patch** - Suporte a GRF, THOR, GPF e RGZ
- 🚀 **Executável Leve** - ~700KB, sem dependências de DLL
- 🪟 **Bordas Arredondadas** - Suporte a window border radius
- 🌐 **WebView Integrado** - Exiba notícias/páginas web dentro do patcher

## 🏗️ Arquitetura

O projeto usa uma arquitetura moderna:

| Componente   | Tecnologia                    | Descrição                              |
| ------------ | ----------------------------- | -------------------------------------- |
| **Builder**  | Electron + Vue 3 + TypeScript | Interface visual para criar patchers   |
| **Patcher**  | C++ Win32/GDI+                | Executável nativo para usuários finais |
| **Embedder** | C++                           | Embute configuração/recursos no EXE    |

## 📁 Estrutura do Projeto

```
autopatch-community/
├── electron-builder/           # 🎨 Builder Visual (Electron + Vue 3)
│   ├── src/
│   │   ├── main/               # Processo principal Electron
│   │   ├── preload/            # Bridge IPC
│   │   └── renderer/           # Interface Vue 3
│   │       ├── components/
│   │       │   └── editor/     # DesignCanvas, PropertyPanel, etc.
│   │       ├── stores/         # Pinia stores (project, ui)
│   │       └── types/          # TypeScript definitions
│   ├── native/                 # Embedder nativo
│   └── resources/              # Executáveis compilados
│
├── cpp/                        # ⚡ Patcher Nativo (C++)
│   ├── src/
│   │   ├── core/               # Biblioteca compartilhada
│   │   │   ├── config.cpp/h    # Parser de configuração JSON
│   │   │   ├── grf.cpp/h       # Parser GRF
│   │   │   ├── thor.cpp/h      # Parser THOR
│   │   │   ├── http.cpp/h      # Download HTTP (WinInet)
│   │   │   ├── patcher.cpp/h   # Lógica de patching
│   │   │   └── resources.cpp/h # Extração de recursos RC
│   │   ├── client/             # AutoPatcher.exe
│   │   │   ├── window.cpp/h    # Janela principal Win32
│   │   │   ├── ui.cpp/h        # Renderização GDI+
│   │   │   └── embedded_browser.cpp/h  # WebView MSHTML
│   │   └── builder/            # AutoPatchBuilder.exe
│   │       └── embedder.cpp/h  # Embute recursos no EXE
│   └── CMakeLists.txt
│
├── samples/                    # 📋 Arquivos de exemplo
│   ├── patcher.json            # Config de exemplo
│   └── webview_test.html       # Teste de WebView
│
└── doc/                        # 📚 Documentação
    ├── GUIA_DE_USO.md
    └── IMPLEMENTATION_PLAN.md
```

## 🚀 Começando

### Pré-requisitos

- **Node.js** 18+ (para o Builder)
- **Visual Studio 2022** com "Desktop development with C++"
- **CMake** 3.20+

### Compilando o Builder (Electron)

```bash
cd electron-builder
npm install
npm run dev          # Modo desenvolvimento
npm run build:win    # Build para Windows
```

### Compilando o Patcher (C++)

```bash
cd cpp
mkdir build && cd build
cmake ..
cmake --build . --config Release
```

Os executáveis serão gerados em `cpp/build/bin/Release/`:

- `AutoPatcher.exe` - Template do patcher
- `AutoPatchBuilder.exe` - Ferramenta de build
- `embedder.exe` - Embute recursos

### Usando o Builder

1. Execute o Builder: `npm run dev` (ou o instalador)
2. Configure as **Configurações Gerais**:
   - URLs do servidor de patches
   - Executável do jogo
   - Dimensões da janela
3. Adicione elementos no canvas:
   - 🖼️ Imagem de fundo
   - 🎬 Vídeo de fundo (MP4) com botão play/pause customizável
   - 🔘 Botões (com estados hover/pressed)
   - 📝 Labels (texto dinâmico)
   - 📊 Barra de progresso
   - 🌐 WebView (páginas web)
4. Clique em **"Gerar Patcher"**
5. O EXE gerado contém tudo embutido!

## ⚙️ Configuração do Servidor

### Estrutura de Arquivos

```
servidor/
├── patchlist.txt      # Lista de patches
├── version.json       # Versão atual (opcional)
├── patch001.thor
├── patch002.thor
└── ...
```

### Formato do patchlist.txt

```
# Comentários começam com #
# ID FILENAME
1 patch001.thor
2 patch002.thor
3 patch003.thor
```

### version.json (opcional)

```json
{
  "version": 3,
  "message": "Atualização disponível!"
}
```

## 🎬 Vídeo de Fundo

O AutoPatch suporta vídeo MP4 como plano de fundo animado, com botão play/pause totalmente customizável.

### Estrutura de Arquivos

```
pasta_do_cliente/
├── MeuPatcher.exe        # Executável do patcher
├── background.bmp        # Imagem de fundo (fallback)
└── resources/
    └── video_fundo.mp4   # Vídeo de fundo
```

### Configuração no Builder

1. No painel de **Propriedades**, ative "Vídeo de Fundo"
2. Selecione o arquivo MP4
3. Configure as opções:
   - **Mostrar controles**: Exibe botão play/pause
   - **Auto Play**: Inicia automaticamente
   - **Loop**: Repete o vídeo
4. Customize o botão play/pause:
   - Posição (arraste no canvas ou defina X/Y)
   - Tamanho
   - Cores (fundo, ícone, borda)
   - Opacidade

### Atualizando o Vídeo

Para atualizar o vídeo sem gerar novo patcher:

1. Substitua o arquivo na pasta `resources/`
2. Mantenha o mesmo nome do arquivo original
3. O patcher carregará automaticamente o novo vídeo

### Formatos Suportados

- **MP4** (H.264/AAC) - Recomendado
- **WMV** (Windows Media Video)
- **AVI** (com codecs compatíveis)

## 🎮 Ações dos Botões

| Action            | Descrição                   |
| ----------------- | --------------------------- |
| `start_game`      | Inicia o executável do jogo |
| `check_files`     | Verifica e baixa patches    |
| `close`           | Fecha o patcher             |
| `minimize`        | Minimiza a janela           |
| `url:https://...` | Abre URL no navegador       |

## 📋 Formatos Suportados

### GRF (Gravity Resource File)

- Versões: 1.02, 1.03, 2.00, 3.00
- Compressão: ZLIB
- Criptografia: DES (v1.x)

### THOR (Thor Patcher Format)

- Formato otimizado para patches incrementais
- Suporta remoção de arquivos
- Compressão ZLIB

### GPF (Gravity Patch File)

- Mesmo formato do GRF
- Usado para patches que modificam GRF existente

### RGZ (Ragnarok GZip)

- Arquivo GZIP com estrutura de diretórios
- Extrai arquivos para pasta

## 📸 Screenshots

<p align="center">
  <i>Em breve...</i>
</p>

## 🤝 Contribuindo

Contribuições são bem-vindas! Por favor:

1. Faça um Fork do projeto
2. Crie sua branch (`git checkout -b feature/MinhaFeature`)
3. Commit suas mudanças (`git commit -m 'Add MinhaFeature'`)
4. Push para a branch (`git push origin feature/MinhaFeature`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes.

## 👏 Créditos

- **Cremané** (saadrcaa@gmail.com) - Desenvolvedor e mantenedor
- Documentação GRF baseada em [GRF Editor Internals](doc/GRF_EDITOR_INTERNALS.md)
- Inspirado em Eluair, Thor Patcher e rPatchur

---

<p align="center">
  Feito com ❤️ para a comunidade de Ragnarok Online
</p>
