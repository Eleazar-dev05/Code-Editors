
## 1. Estructura de Directorios

Para mantener el sistema limpio, utilizaremos una estructura donde la configuración y los datos residen dentro de la carpeta oculta `~/.vim/`.

```text
~/.vim/
├── vimrc            # Archivo de configuración principal
├── autoload/        # Contiene el script del gestor de plugins (plug.vim)
├── colors/          # (Opcional) Temas instalados manualmente
└── plugins/         # Directorio donde se descargan los plugins automáticamente
```

---

## 2. Instalación del Gestor de Plugins (vim-plug)

Vim requiere el script `plug.vim` en la carpeta `autoload` para habilitar los comandos de gestión. Descárgalo ejecutando el siguiente comando en tu terminal:

```bash
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    [https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim](https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim)
```

---

## 3. Archivo de Configuración (`~/.vim/vimrc`)

Crea o edita el archivo con `nano ~/.vim/vimrc` y pega el siguiente contenido. Esta configuración está optimizada para ser ligera y funcional sin depender de Node.js.

```vim
" ============================================================================
" 1. SECCIÓN DE PLUGINS (Gestión con vim-plug)
" ============================================================================
call plug#begin('~/.vim/plugins')

" --- Apariencia y Temas ---
Plug 'joshdick/onedark.vim'                  " Tema moderno y limpio
Plug 'vim-airline/vim-airline'               " Barra de estado informativa

" --- Utilidades de IDE ---
Plug 'preservim/nerdtree'                    " Explorador de archivos
Plug 'ryanoasis/vim-devicons'                " Iconos (Requiere Nerd Font)
Plug 'sheerun/vim-polyglot'                  " Resaltado de sintaxis optimizado

call plug#end()

" ============================================================================
" 2. CONFIGURACIÓN BÁSICA Y ESTÉTICA
" ============================================================================
syntax on                                    " Habilitar resaltado de sintaxis
set number                                   " Mostrar números de línea
set relativenumber                           " Números relativos para saltos rápidos
set mouse=a                                  " Soporte total para ratón
set clipboard=unnamedplus                    " Integración con portapapeles del sistema
set sw=4 sts=4 ts=4 et                       " Indentación estándar (4 espacios)
set cursorline                               " Resaltar línea bajo el cursor
set termguicolors                            " Soporte de colores reales (24-bit)

" --- Configuración del Tema ---
set background=dark
autocmd vimenter * colorscheme onedark

" ============================================================================
" 3. MAPEOS DE TECLAS (Atajos)
" ============================================================================
let mapleader = " "                          " Tecla líder: Barra Espaciadora

" Abrir/Cerrar Explorador de archivos (Espacio + n)
nnoremap <leader>n :NERDTreeToggle<CR>

" Navegación básica entre ventanas
nnoremap <C-h> <C-w>h
nnoremap <C-j> <C-w>j
nnoremap <C-k> <C-w>k
nnoremap <C-l> <C-w>l
```

---

## 4. Instalación de Plugins y Dependencias

### Paso 1: Dependencias del Sistema (openSUSE)
Para asegurar que el portapapeles y los iconos funcionen correctamente, instala los siguientes paquetes:

```bash
# Para el portapapeles (clipboard=unnamedplus)
sudo zypper install xclip

# Recomendado: Instala una Nerd Font (ej. JetBrainsMono) para ver los iconos
```

### Paso 2: Activar Plugins en Vim
1. Abre Vim desde la terminal: `vim`
2. Ejecuta el comando de instalación: `:PlugInstall`
3. Espera a que finalicen las descargas y reinicia Vim.

---

## 5. Uso Básico del IDE
- **Explorador de archivos**: Presiona `Espacio` + `n` para abrir el panel lateral. Dentro de NERDTree, usa `m` para el menú de archivos (crear, borrar, renombrar).
- **Autocompletado básico**: Usa `Ctrl + n` en modo insertar para sugerencias basadas en el texto actual.
- **Portapapeles**: Copia con `y` y pega con `p` directamente hacia/desde aplicaciones externas.
