# Setup vscode
Berjalan dengan vscode + vim <br>

## Learn vim
https://medium.com/kredibel/belajar-vim-untuk-meningkatkan-produktivitas-ngoding-e3e6ce717b35 (web)
https://github.com/nauvalazhar/pengantar-vi-improved (pdf)

## VSCode with embedded Neovim
#### Semua shortcut dan implementasi nya bersumber dari channel di bawah ini, dengan beberapa modifikasi
https://www.youtube.com/watch?v=g4dXZ0RQWdw <br>

keybindings.json & settings.json semua bersumber dari material <br>
https://github.com/LunarVim/LunarVim/tree/4625145d0278d4a039e55c433af9916d93e7846a/utils/vscode_config

## How to Sync Your VS Code Settings and Extensions Across Multiple Devices
https://betterprogramming.pub/sync-visual-studio-code-settings-extensions-shortcuts-across-multiple-devices-9fa6a980f25e

## Minimal VScode UI!
https://dev.to/andrewgeorge/minimal-vscode-ui-343e

## Requirement vscode extension 
```txt
aaron-bond.better-comments
alefragnani.Bookmarks
AmrMetwally.vim-find-highlight
andrewberty.fontsy
be5invis.vscode-custom-css
crudh.vim-how
dhedgecock.radical-vscode
esbenp.prettier-vscode
formulahendry.code-runner
golang.go
hoovercj.vscode-settings-cycler
Llam4u.nerdtree
miguelsolorio.symbols
pascalsenn.keyboard-quickfix
usernamehw.errorlens
vscodevim.vim
VSpaceCode.whichkey
```

## Install extension
```py
import subprocess

extensions = [
    "aaron-bond.better-comments",
    "alefragnani.Bookmarks",
    "AmrMetwally.vim-find-highlight",
    "andrewberty.fontsy",
    "be5invis.vscode-custom-css",
    "crudh.vim-how",
    "dhedgecock.radical-vscode",
    "esbenp.prettier-vscode",
    "formulahendry.code-runner",
    "golang.go",
    "hoovercj.vscode-settings-cycler",
    "Llam4u.nerdtree",
    "miguelsolorio.symbols",
    "pascalsenn.keyboard-quickfix",
    "usernamehw.errorlens",
    "vscodevim.vim",
    "VSpaceCode.whichkey"
]

for extension in extensions:
    subprocess.run(["code", "--install-extension", extension], check=True)

print("Semua ekstensi telah diinstal.")

```
## Setup minimal Vscode UI
```bash
mkdir -p ~/.config/vscode
echo '
.tabs-and-actions-container {  
    display: none !important;  
}
' > ~/.config/vscode/custom.css

// MacOS and Linux File URL Example:
file:///Users/MyUserName/Documents/custom.css

// enter a url for your custom css file following notes below
// vscode settings.json 
"vscode_custom_css.imports": ["{URL}"]
```

## Error vscode custom css shows info: Run VS Code with admin privileges so the changes can be applied , linux
```bash
For Ubuntu/Linux users :

#for vs code:
sudo chown -R $(whoami) /usr/share/code
#for vs code insiders:
sudo chown -R $(whoami) /usr/share/code-insiders
#if you want to check your folder's owner:
ls -la /usr/share/code
#if you want to rollback this permissions back to root:
sudo chown -R root /usr/share/code
```

## Cheatsheet
```markdown
```

## Keybindings.json
```json
// Place your key bindings in this file to override the defaults
[
	// breadcrumb
	{
		"key": "ctrl+h",
		"command": "breadcrumbs.focusPrevious",
		"when": "breadcrumbsActive && breadcrumbsVisible"
	},
	{
		"key": "ctrl+j",
		"command": "list.focusDown",
		"when": "breadcrumbsActive && breadcrumbsVisible"
	},
	{
		"key": "ctrl+k",
		"command": "list.focusUp",
		"when": "breadcrumbsActive && breadcrumbsVisible"
	},
	{
		"key": "ctrl+l",
		"command": "breadcrumbs.focusNext",
		"when": "breadcrumbsActive && breadcrumbsVisible"
	},
	// explorer
	{
		"key": "r",
		"command": "renameFile",
		"when": "explorerViewletVisible && filesExplorerFocus && !explorerResourceIsRoot && !explorerResourceReadonly && !inputFocus"
	},
	{
		"key": "enter",
		"command": "-renameFile",
		"when": "explorerViewletVisible && filesExplorerFocus && !explorerResourceIsRoot && !explorerResourceReadonly && !inputFocus"
	},
	{
		"key": "j",
		"command": "list.focusDown",
		"when": "listFocus && explorerViewletVisible && filesExplorerFocus && !explorerResourceIsRoot && !explorerResourceReadonly && !inputFocus"
	},
	{
		"key": "k",
		"command": "list.focusUp",
		"when": "listFocus && explorerViewletVisible && filesExplorerFocus && !explorerResourceIsRoot && !explorerResourceReadonly && !inputFocus"
	},
	{
		"key": "enter",
		"command": "list.select",
		"when": "explorerViewletVisible && filesExplorerFocus"
	},
	// explore expand, close, open, new folder
	{
		"key": "l",
		"command": "list.select",
		"when": "explorerViewletVisible && filesExplorerFocus && !inputFocus"
	},
	{
		"key": "o",
		"command": "list.toggleExpand",
		"when": "explorerViewletVisible && filesExplorerFocus && !inputFocus"
	},
	{
		"key": "h",
		"command": "list.collapse",
		"when": "explorerViewletVisible && filesExplorerFocus && !inputFocus"
	},
	{
		"key": "a",
		"command": "explorer.newFile",
		"when": "filesExplorerFocus && !inputFocus"
	},
	{
		"key": "shift+a",
		"command": "explorer.newFolder",
		"when": "filesExplorerFocus && !inputFocus"
	},
	// move interaction
	{
		"key": "ctrl+j",
		"command": "selectNextSuggestion",
		"when": "editorTextFocus && suggestWidgetMultipleSuggestions && suggestWidgetVisible"
	},
	{
		"key": "ctrl+k",
		"command": "selectPrevSuggestion",
		"when": "editorTextFocus && suggestWidgetMultipleSuggestions && suggestWidgetVisible"
	},
	{
		"key": "ctrl+j",
		"command": "workbench.action.quickOpenNavigateNext",
		"when": "inQuickOpen"
	},
	{
		"key": "ctrl+k",
		"command": "workbench.action.quickOpenNavigatePrevious",
		"when": "inQuickOpen"
	},
	{
		"key": "ctrl+l",
		"when": "sideBarFocus",
		"command": "workbench.action.focusActiveEditorGroup"
	},
	{
		"key": "ctrl+k",
		"command": "workbench.action.focusActiveEditorGroup",
		"when": "terminalFocus"
	},
	// terminal open, close
	{
		"key": "ctrl+m",
		"command": "workbench.action.togglePanel"
	},
	{
		"key": "ctrl+j",
		"command": "-workbench.action.togglePanel"
	},
	// increase & decrease
	{
		"key": "ctrl+i",
		"command": "workbench.action.increaseViewSize"
	},
	{
		"key": "ctrl+shift+i",
		"command": "workbench.action.decreaseViewSize"
	},
  // tab 
	{
		"key": "ctrl+w",
		"command": "workbench.action.closeActiveEditor"
	},
  // next & prev suggestion
	{
		"key": "ctrl+j",
		"command": "selectNextSuggestion",
		"when": "editorTextFocus && suggestWidgetMultipleSuggestions && suggestWidgetVisible"
	},
	{
		"key": "ctrl+j",
		"command": "workbench.action.quickOpenNavigateNext",
		"when": "inQuickOpen"
	},
	{
		"key": "ctrl+k",
		"command": "selectPrevSuggestion",
		"when": "editorTextFocus && suggestWidgetMultipleSuggestions && suggestWidgetVisible"
	},
	{
		"key": "ctrl+k",
		"command": "workbench.action.quickOpenNavigatePrevious",
		"when": "inQuickOpen"
	},
	{
		"key": "tab",
		"command": "selectNextSuggestion",
		"when": "editorTextFocus && suggestWidgetMultipleSuggestions && suggestWidgetVisible"
	},
	{
		"key": "tab",
		"command": "workbench.action.quickOpenNavigateNext",
		"when": "inQuickOpen"
	},
	{
		"key": "ctrl+tab",
		"command": "selectPrevSuggestion",
		"when": "editorTextFocus && suggestWidgetMultipleSuggestions && suggestWidgetVisible"
	},
	{
		"key": "ctrl+tab",
		"command": "workbench.action.quickOpenNavigatePrevious",
		"when": "inQuickOpen"
	}
]

```

## Settings.json
```json
{
	// editor text dan formatter
	"editor.defaultFormatter": "esbenp.prettier-vscode",
	"editor.formatOnSave": true,
	"editor.formatOnPaste": true,
	"editor.formatOnType": true,
	"editor.inlayHints.enabled": "on",
	"editor.wordWrap": "on",
	"editor.codeActionsOnSave": {
		"source.fixAll": false,
		"source.sortImports": true
	},
	// editor theme  & icon
	"workbench.iconTheme": "symbols",
	"workbench.colorTheme": "Radical",
	"workbench.colorCustomizations": {
		"[Radical]": {
			// side bar aktif di sebelah kanan
			// jadi pengaturan ini mulai dari paling sebelah kanan
			// warna activity bar, komponen sebelah kanan yg ada ikon
			"activityBar.border": "#141322",
			// "activityBar.activeBorder": "#141322",
			"activityBar.background": "#141322",
			"activityBar.activeBackground": "#141322",
			// warna sidebar, komponen explorer yg ada list file dan folder
			"sideBar.border": "#141322",
			"sideBar.background": "#141322",
			// warna sidebar header, komponen bagian penamaan menu seperti,
			// Outline, Timeline dll
			"sideBarSectionHeader.background": "#141322",
			"sideBarSectionHeader.border": "#141322",
			// warna scrollbar, komponen yg berdekatan dengan editorOverviewRuler
			"scrollbar.shadow": "#141322", // shadow di bagian bawah komponen breadcrumb
			// "scrollbarSlider.background": "#141322",
			// "scrollbarSlider.hoverBackground": "#141322",
			// "scrollbarSlider.activeBackground": "#141322",
			// warna editor over view ruler, komponen yg dekat minimap
			// yg digunakan untuk menunjukan posisi kita sekarang
			"editorOverviewRuler.border": "#141322",
			"editorOverviewRuler.background": "#141322",
			// warna minimap
			"minimap.background": "#141322",
			// warna editor komponen suggest command
			"editorSuggestWidget.background": "#141322",
			"editorSuggestWidget.border": "#141322",
			"editorWidget.background": "#141322",
			"editorWidget.border": "#141322",
			// warna hover teks
			"editorHoverWidget.background": "#141322",
			"editorHoverWidget.border": "#4b1c28", //cd428f
			"editorHoverWidget.statusBarBackground": "#141322",
			"editor.selectionHighlightBorder": "#2c152e",
			// "editorBracketMatch.border": "#141322",
			// warna editor gutter, komponen bagin penomoran di editor
			"editorGutter.background": "#141322",
			// warna breadcrumb
			"breadcrumb.background": "#141322",
			// warna editor grup, komponen di atas editor aktif sekarang,
			// bagian bawah tabs dan breadcrumb
			"editorGroup.border": "#141322",
			"editorGroupHeader.border": "#141322",
			"editorGroupHeader.tabsBorder": "#141322",
			"editorGroupHeader.tabsBackground": "#141322",
			// warna title bar
			"titleBar.border": "#141322",
			// warna tab
			"tab.activeBackground": "#141322",
			"tab.inactiveBackground": "#141322",
			"tab.border": "#141322",
			// warna status bar, komponen informasi di bagian paling bawah
			"statusBar.background": "#141322",
			"statusBar.border": "#141322",
			// warna panel, komponen diatas terminal
			"panel.background": "#141322",
			"panel.border": "#141322",
			// warna terminal
			"terminal.background": "#141322",
			"terminal.border": "#141322"
		}
	},
	// editor improve ui
	"workbench.editor.tabCloseButton": "off",
	"workbench.sideBar.location": "right",
	"workbench.layoutControl.enabled": false,
	"window.title": " ",
	"telemetry.telemetryLevel": "off",
	"problems.defaultViewMode": "table",
	// "editor.padding.top": 20,
	"search.exclude": {
		"**/node_modules": true,
		"**/bower_components": true,
		"**/env": true,
		"**/venv": true
	},
	// "editor.stickyScroll.enabled": true,
	"symbols.hidesExplorerArrows": false,
	"editor.unicodeHighlight.ambiguousCharacters": false,
	// "editor.tabSize": 2, // def 4
	"editor.renderWhitespace": "none",
	"editor.minimap.enabled": false,
	"editor.guides.bracketPairsHorizontal": false,
	"editor.bracketPairColorization.enabled": false,
	"editor.guides.highlightActiveBracketPair": false,
	"editor.overviewRulerBorder": false,
	"workbench.editor.enablePreview": false,
	"workbench.startupEditor": "none",
	"workbench.tree.renderIndentGuides": "none",
	"editor.occurrencesHighlight": false,
	"editor.peekWidgetDefaultFocus": "editor",
	// editor font
	"editor.fontFamily": "Hack",
	"editor.fontWeight": "500",
	"editor.lineHeight": 22.5,
	"editor.fontSize": 17,
	"editor.fontLigatures": true,
	// terminal
	// "terminal.integrated.showExitAlert": false,
	// "terminal.integrated.gpuAcceleration": "off",
	"terminal.integrated.fontSize": 14,
	"terminal.integrated.fontWeight": "500",
	// editor snippet & suggest
	"editor.snippetSuggestions": "top",
	"editor.suggest.insertMode": "replace",
	"editor.quickSuggestions": {
		"other": true,
		"comments": true,
		"strings": true
	},
	"editor.quickSuggestionsDelay": 0,
	"editor.suggest.snippetsPreventQuickSuggestions": false,
	// editor bagian area scrollbar
	"editor.hideCursorInOverviewRuler": true,
	"editor.scrollbar.horizontal": "hidden",
	"editor.scrollbar.vertical": "hidden",
	// editor bagian kiri
	"editor.guides.indentation": false,
	"editor.glyphMargin": false,
	"editor.lineNumbers": "off",
	"editor.showFoldingControls": "never",
	// editor cursor
	"editor.cursorWidth": 5,
	"editor.cursorSmoothCaretAnimation": "on",
	"editor.renderLineHighlight": "none",
	"editor.cursorBlinking": "phase",
	// breadcrumb
	"breadcrumbs.enabled": false,
	// explorer
	"explorer.confirmDelete": false,
	"extensions.autoCheckUpdates": false,
	"explorer.confirmDragAndDrop": false,
	"explorer.compactFolders": false,
	"explorer.decorations.colors": false,
	"explorer.openEditors.visible": 0,
	// scm
	"scm.diffDecorationsIgnoreTrimWhitespace": "true",
	"scm.diffDecorations": "gutter",
	"scm.diffDecorationsGutterVisibility": "hover",
	"scm.diffDecorationsGutterWidth": 1,
	"scm.diffDecorationsGutterAction": "none",
	// extension better-comments
	"better-comments.highlightPlainText": true,
	"better-comments.tags": [
		{
			"tag": "-",
			"color": "#fcf6bd",
			"strikethrough": false,
			"underline": false,
			"backgroundColor": "transparent",
			"bold": false,
			"italic": false
		},
		{
			"tag": "bug",
			"color": "#fff",
			"strikethrough": false,
			"underline": false,
			"backgroundColor": "#be2525",
			"bold": true,
			"italic": false
		},
		{
			"tag": "?",
			"color": "#fff",
			"strikethrough": false,
			"underline": false,
			"backgroundColor": "#173FCF66",
			"bold": true,
			"italic": false
		},
		{
			"tag": "todo",
			"color": "#fff",
			"strikethrough": false,
			"underline": false,
			"backgroundColor": "#ffb703bb",
			"bold": true,
			"italic": false
		}
	],
	// extension prettier
	"prettier.useTabs": true,
	"prettier.singleQuote": true,
	"prettier.jsxSingleQuote": true,
	"prettier.semi": false,
	"prettier.arrowParens": "avoid",
	"prettier.printWidth": 120,
	// extension thunder
	"thunder-client.requestLayout": "Top/Bottom",
	"thunder-client.sidebar.hideDateModified": true,
	"thunder-client.editorFontSize": 18,
	// extension codesnap
	"codesnap.showWindowControls": false,
	// extension color-highlight
	"color-highlight.markRuler": false,
	// settings cycle
	"settings.cycle": [
		{
			"id": "activateRule",
			"values": [
				{ "editor.lineNumbers": "off" },
				{ "editor.glyphMargin": false },
				{ "editor.occurrencesHighlight": false },
				{ "editor.lineNumbers": "relative" },
				{ "editor.glyphMargin": true },
				{ "editor.occurrencesHighlight": true }
			]
		}
	],
	// // extension vscode custome
	"vscode_custom_css.imports": ["file:///home/biru/.config/vscode/custom.css"],
	// extension fontsy
	"fontsy.defaultEditorFontSize": 16,
	"fontsy.defaultTerminalFontSize": 14,
	"fontsy.step": 0.5,
	"workbench.activityBar.visible": false,
	// extension code-runner
	"code-runner.executorMap": {
		"python": "python",
		"javascript": "node",
		"c": "gcc $fileName -o $fileNameWithoutExt && $fileNameWithoutExt",
		"cpp": "g++ $fileName -o $fileNameWithoutExt && $fileNameWithoutExt",
		"java": "java -jar $fileNameWithoutExt.jar",
		"go": "go run",
		"php": "php",
		"perl": "perl",
		"ruby": "ruby",
		"powershell": "powershell -ExecutionPolicy Bypass -File",
		"batch": "cmd /C",
		"bash": "bash"
	},
	"code-runner.runInTerminal": true,
	"code-runner.clearPreviousOutput": true,
	// extension vim
	"vim.highlightedyank.enable": true,
	"vim.cursorStylePerMode.normal": "block",
	"vim.cursorStylePerMode.insert": "line-thin",
	"vim.leader": "<Space>",
	"vim.useSystemClipboard": true,
	"vim.useCtrlKeys": true,
	"vim.autoindent": true,
	"vim.easymotion": true,
	"vim.incsearch": true,
	"vim.hlsearch": true,
	"vim.foldfix": true,
	"vim.handleKeys": {
		"<C-d>": true,
		"<C-s>": false,
		"<C-z>": false,
		"<C-n>": false
	},
	"vim.normalModeKeyBindingsNonRecursive": [
		{
			"before": ["<leader>", "e"],
			"commands": ["workbench.explorer.fileView.focus"]
		},
		{
			"before": ["<leader>", "r"],
			"commands": ["code-runner.run"]
		},
		{
			"before": ["<leader>", "s"],
			"commands": ["workbench.action.files.save"]
		},
		{
			"before": ["<leader>", "w"],
			"commands": ["workbench.action.closeActiveEditor"]
		},
		{
			"before": ["<C-h>"],
			"commands": ["workbench.action.navigateLeft"]
		},
		{
			"before": ["<C-j>"],
			"commands": ["workbench.action.navigateDown"]
		},
		{
			"before": ["<C-k>"],
			"commands": ["workbench.action.navigateUp"]
		},
		{
			"before": ["<C-l>"],
			"commands": ["workbench.action.navigateRight"]
		},
		{
			"before": ["<leader>", "<leader>"],
			"commands": ["whichkey.show"]
		},
		{
			"before": ["<C-n>"],
			"commands": [":nohl"]
		},
		{
			"before": ["g", "d"],
			"commands": ["editor.action.revealDefinitionAside"]
		},
		{
			"before": ["<leader>", "n"],
			"commands": [":tabnext"]
		},
		{
			"before": ["<leader>", "p"],
			"commands": [":tabprev"]
		},
		{
			"before": ["<Leader>", "t"],
			"commands": ["workbench.action.gotoSymbol"]
		},
		{
			"before": ["<leader>", ";"],
			"commands": ["breadcrumbs.focus"]
		},
		{
			"before": ["g", "h"],
			"commands": [
				{
					"command": "editor.action.showDefinitionPreviewHover"
				}
			]
		}
	],
	"vim.insertModeKeyBindings": [
		{
			"before": ["j", "j"],
			"after": ["<ESC>"]
		}
	],
	// extension which key
	"whichkey.sortOrder": "alphabetically",
	"whichkey.bindings": [
		{
			"key": ";",
			"name": "commands",
			"type": "command",
			"command": "workbench.action.showCommands"
		},
		{
			"key": "?",
			"name": "quick help",
			"type": "command",
			"command": "workbench.action.quickOpen"
		},
		{
			"key": ":",
			"name": "vim help",
			"type": "command",
			"command": "vim-how.search"
		},
		{
			"key": "b",
			"name": "Buffers/Editors...",
			"type": "bindings",
			"bindings": [
				{
					"key": "b",
					"name": "Show all buffers/editors",
					"type": "command",
					"command": "workbench.action.showAllEditors"
				},
				{
					"key": "d",
					"name": "Close active editor",
					"type": "command",
					"command": "workbench.action.closeActiveEditor"
				},
				{
					"key": "h",
					"name": "Move editor into left group",
					"type": "command",
					"command": "workbench.action.moveEditorToLeftGroup"
				},
				{
					"key": "j",
					"name": "Move editor into below group",
					"type": "command",
					"command": "workbench.action.moveEditorToBelowGroup"
				},
				{
					"key": "k",
					"name": "Move editor into above group",
					"type": "command",
					"command": "workbench.action.moveEditorToAboveGroup"
				},
				{
					"key": "l",
					"name": "Move editor into right group",
					"type": "command",
					"command": "workbench.action.moveEditorToRightGroup"
				},
				{
					"key": "m",
					"name": "Close other editors",
					"type": "command",
					"command": "workbench.action.closeOtherEditors"
				},
				{
					"key": "n",
					"name": "Next editor",
					"type": "command",
					"command": "workbench.action.nextEditor"
				},
				{
					"key": "p",
					"name": "Previous editor",
					"type": "command",
					"command": "workbench.action.previousEditor"
				},
				{
					"key": "N",
					"name": "New untitled editor",
					"type": "command",
					"command": "workbench.action.files.newUntitledFile"
				},
				{
					"key": "u",
					"name": "Reopen closed editor",
					"type": "command",
					"command": "workbench.action.reopenClosedEditor"
				},
				{
					"key": "y",
					"name": "Copy buffer to clipboard",
					"type": "commands",
					"commands": ["editor.action.selectAll", "editor.action.clipboardCopyAction", "cancelSelection"]
				}
			]
		},
		{
			"key": "m",
			"name": "Marks",
			"bindings": [
				{
					"key": "m",
					"name": "Toggle mark",
					"type": "command",
					"command": "bookmarks.toggle"
				},
				{
					"key": "M",
					"name": "Toggle mark labeled",
					"type": "command",
					"command": "bookmarks.toggleLabeled"
				},
				{
					"key": "n",
					"name": "Jump to next",
					"type": "command",
					"command": "bookmarks.jumpToNext"
				},
				{
					"key": "N",
					"name": "Jump to previous",
					"type": "command",
					"command": "bookmarks.jumpToPrevious"
				},
				{
					"key": "l",
					"name": "List bookmark file",
					"type": "command",
					"command": "bookmarks.list"
				},
				{
					"key": "L",
					"name": "List bookmark all file",
					"type": "command",
					"command": "bookmarks.listFromAllFiles"
				},
				{
					"key": "d",
					"name": "Delete bookmark file",
					"type": "command",
					"command": "bookmarks.clear"
				},
				{
					"key": "D",
					"name": "Delete all bookmark file",
					"type": "command",
					"command": "bookmarks.clearFromAllFiles"
				}
			]
		},
		{
			"key": "d",
			"name": "Debug...",
			"type": "bindings",
			"bindings": [
				{
					"key": "d",
					"name": "Start debug",
					"type": "command",
					"command": "workbench.action.debug.start"
				},
				{
					"key": "S",
					"name": "Stop debug",
					"type": "command",
					"command": "workbench.action.debug.stop"
				},
				{
					"key": "c",
					"name": "Continue debug",
					"type": "command",
					"command": "workbench.action.debug.continue"
				},
				{
					"key": "p",
					"name": "Pause debug",
					"type": "command",
					"command": "workbench.action.debug.pause"
				},
				{
					"key": "r",
					"name": "Run without debugging",
					"type": "command",
					"command": "workbench.action.debug.run"
				},
				{
					"key": "R",
					"name": "Restart debug",
					"type": "command",
					"command": "workbench.action.debug.restart"
				},
				{
					"key": "i",
					"name": "Step into",
					"type": "command",
					"command": "workbench.action.debug.stepInto"
				},
				{
					"key": "s",
					"name": "Step over",
					"type": "command",
					"command": "workbench.action.debug.stepOver"
				},
				{
					"key": "o",
					"name": "Step out",
					"type": "command",
					"command": "workbench.action.debug.stepOut"
				},
				{
					"key": "b",
					"name": "Toggle breakpoint",
					"type": "command",
					"command": "editor.debug.action.toggleBreakpoint"
				},
				{
					"key": "B",
					"name": "Toggle inline breakpoint",
					"type": "command",
					"command": "editor.debug.action.toggleInlineBreakpoint"
				},
				{
					"key": "j",
					"name": "Jump to cursor",
					"type": "command",
					"command": "debug.jumpToCursor"
				},
				{
					"key": "v",
					"name": "REPL",
					"type": "command",
					"command": "workbench.debug.action.toggleRepl"
				},
				{
					"key": "w",
					"name": "Focus on watch window",
					"type": "command",
					"command": "workbench.debug.action.focusWatchView"
				},
				{
					"key": "W",
					"name": "Add to watch",
					"type": "command",
					"command": "editor.debug.action.selectionToWatch"
				}
			]
		},
		{
			"key": "e",
			"name": "Toggle Explorer",
			"type": "command",
			"command": "workbench.action.toggleSidebarVisibility"
		},
		{
			"key": "f",
			"name": "Find & Replace...",
			"type": "bindings",
			"bindings": [
				{
					"key": "f",
					"name": "File",
					"type": "command",
					"command": "editor.action.startFindReplaceAction"
				},
				{
					"key": "s",
					"name": "Symbol",
					"type": "command",
					"command": "editor.action.rename",
					"when": "editorHasRenameProvider && editorTextFocus && !editorReadonly"
				},
				{
					"key": "p",
					"name": "Project",
					"type": "command",
					"command": "workbench.action.replaceInFiles"
				}
			]
		},
		{
			"key": "g",
			"name": "Git...",
			"type": "bindings",
			"bindings": [
				{
					"key": "b",
					"name": "Checkout",
					"type": "command",
					"command": "git.checkout"
				},
				{
					"key": "c",
					"name": "Commit",
					"type": "command",
					"command": "git.commit"
				},
				{
					"key": "d",
					"name": "Delete Branch",
					"type": "command",
					"command": "git.deleteBranch"
				},
				{
					"key": "f",
					"name": "Fetch",
					"type": "command",
					"command": "git.fetch"
				},
				{
					"key": "i",
					"name": "Init",
					"type": "command",
					"command": "git.init"
				},
				{
					"key": "m",
					"name": "Merge",
					"type": "command",
					"command": "git.merge"
				},
				{
					"key": "p",
					"name": "Publish",
					"type": "command",
					"command": "git.publish"
				},
				{
					"key": "s",
					"name": "Stash",
					"type": "command",
					"command": "workbench.view.scm"
				},
				{
					"key": "S",
					"name": "Stage",
					"type": "command",
					"command": "git.stage"
				},
				{
					"key": "U",
					"name": "Unstage",
					"type": "command",
					"command": "git.unstage"
				}
			]
		},
		{
			"key": "h",
			"name": "Split Horizontal",
			"type": "command",
			"command": "workbench.action.splitEditorDown"
		},
		{
			"key": "i",
			"name": "Insert...",
			"type": "bindings",
			"bindings": [
				{
					"key": "j",
					"name": "Insert line below",
					"type": "command",
					"command": "editor.action.insertLineAfter"
				},
				{
					"key": "k",
					"name": "Insert line above",
					"type": "command",
					"command": "editor.action.insertLineBefore"
				},
				{
					"key": "s",
					"name": "Insert snippet",
					"type": "command",
					"command": "editor.action.insertSnippet"
				}
			]
		},
		{
			"key": "m",
			"name": "minimap",
			"type": "command",
			"command": "editor.action.toggleMinimap"
		},
		{
			"key": "n",
			"name": "highlight",
			"type": "command",
			"command": "vscode-neovim.send",
			"args": ":noh<CR>"
		},
		{
			"key": "s",
			"name": "Search...",
			"type": "bindings",
			"bindings": [
				{
					"key": "f",
					"name": "files",
					"type": "command",
					"command": "workbench.action.quickOpen"
				},
				{
					"key": "t",
					"name": "text",
					"type": "command",
					"command": "workbench.action.findInFiles"
				}
			]
		},
		{
			"key": "S",
			"name": "Show...",
			"type": "bindings",
			"bindings": [
				{
					"key": "e",
					"name": "Show explorer",
					"type": "command",
					"command": "workbench.view.explorer"
				},
				{
					"key": "s",
					"name": "Show search",
					"type": "command",
					"command": "workbench.view.search"
				},
				{
					"key": "g",
					"name": "Show source control",
					"type": "command",
					"command": "workbench.view.scm"
				},
				{
					"key": "t",
					"name": "Show test",
					"type": "command",
					"command": "workbench.view.extension.test"
				},
				{
					"key": "r",
					"name": "Show remote explorer",
					"type": "command",
					"command": "workbench.view.remote"
				},
				{
					"key": "x",
					"name": "Show extensions",
					"type": "command",
					"command": "workbench.view.extensions"
				},
				{
					"key": "p",
					"name": "Show problem",
					"type": "command",
					"command": "workbench.actions.view.problems"
				},
				{
					"key": "o",
					"name": "Show output",
					"type": "command",
					"command": "workbench.action.output.toggleOutput"
				},
				{
					"key": "d",
					"name": "Show debug console",
					"type": "command",
					"command": "workbench.debug.action.toggleRepl"
				}
			]
		},
		{
			"key": "t",
			"name": "Terminal...",
			"type": "bindings",
			"bindings": [
				{
					"key": "t",
					"name": "Toggle Terminal",
					"type": "command",
					"command": "workbench.action.togglePanel"
				}
			]
		},
		{
			"key": "T",
			"name": "UI toggles...",
			"type": "bindings",
			"bindings": [
				{
					"key": "b",
					"name": "Toggle side bar visibility",
					"type": "command",
					"command": "workbench.action.toggleSidebarVisibility"
				},
				{
					"key": "j",
					"name": "Toggle panel visibility",
					"type": "command",
					"command": "workbench.action.togglePanel"
				},
				{
					"key": "F",
					"name": "Toggle full screen",
					"type": "command",
					"command": "workbench.action.toggleFullScreen"
				},
				{
					"key": "s",
					"name": "Select theme",
					"type": "command",
					"command": "workbench.action.selectTheme"
				},
				{
					"key": "m",
					"name": "Toggle maximized panel",
					"type": "command",
					"command": "workbench.action.toggleMaximizedPanel"
				},
				{
					"key": "t",
					"name": "Toggle tool/activity bar visibility",
					"type": "command",
					"command": "workbench.action.toggleActivityBarVisibility"
				},
				{
					"key": "T",
					"name": "Toggle tab visibility",
					"type": "command",
					"command": "workbench.action.toggleTabsVisibility"
				}
			]
		},
		{
			"key": "v",
			"name": "Split Vertical",
			"type": "command",
			"command": "workbench.action.splitEditor"
		},
		{
			"key": "w",
			"name": "Window...",
			"type": "bindings",
			"bindings": [
				{
					"key": "W",
					"name": "Focus previous editor group",
					"type": "command",
					"command": "workbench.action.focusPreviousGroup"
				},
				{
					"key": "h",
					"name": "Move editor group left",
					"type": "command",
					"command": "workbench.action.moveActiveEditorGroupLeft"
				},
				{
					"key": "j",
					"name": "Move editor group down",
					"type": "command",
					"command": "workbench.action.moveActiveEditorGroupDown"
				},
				{
					"key": "k",
					"name": "Move editor group up",
					"type": "command",
					"command": "workbench.action.moveActiveEditorGroupUp"
				},
				{
					"key": "l",
					"name": "Move editor group right",
					"type": "command",
					"command": "workbench.action.moveActiveEditorGroupRight"
				},
				{
					"key": "t",
					"name": "Toggle editor group sizes",
					"type": "command",
					"command": "workbench.action.toggleEditorWidths"
				},
				{
					"key": "m",
					"name": "Maximize editor group",
					"type": "command",
					"command": "workbench.action.minimizeOtherEditors"
				},
				{
					"key": "M",
					"name": "Maximize editor group and hide side bar",
					"type": "command",
					"command": "workbench.action.maximizeEditor"
				},
				{
					"key": "=",
					"name": "Reset editor group sizes",
					"type": "command",
					"command": "workbench.action.evenEditorWidths"
				},
				{
					"key": "z",
					"name": "Combine all editors",
					"type": "command",
					"command": "workbench.action.joinAllGroups"
				},
				{
					"key": "d",
					"name": "Close editor group",
					"type": "command",
					"command": "workbench.action.closeEditorsInGroup"
				},
				{
					"key": "x",
					"name": "Close all editor groups",
					"type": "command",
					"command": "workbench.action.closeAllGroups"
				}
			]
		},
		{
			"key": "z",
			"name": "Toggle zen mode",
			"type": "command",
			"command": "workbench.action.toggleZenMode"
		}
	],
	// extension nert tree
	"nerdtree.hideSidebarWhenOpenFile": false,
	// "nerdtree.alwaysShowSidebar": true,
	// golang setting
	"[go]": {
		"editor.wordWrap": "off",
		"editor.wordWrapColumn": 80,
		"editor.insertSpaces": false,
		"editor.defaultFormatter": "golang.go",
		"editor.codeActionsOnSave": {
			"source.organizeImports": true
		},
		"editor.suggest.snippetsPreventQuickSuggestions": false
	},
	"gopls": {
		"ui.completion.usePlaceholders": true,
		"formatting.gofumpt": true,
		"ui.semanticTokens": true
	},
	"go.toolsManagement.autoUpdate": true,
	// javascript
	"javascript.updateImportsOnFileMove.enabled": "always",
	"typescript.preferences.quoteStyle": "single",
	"typescript.updateImportsOnFileMove.enabled": "always",
	// emmet
	"emmet.includeLanguages": {
		"javascript": "javascriptreact",
		"typescript": "typescriptreact"
	},
	"workbench.statusBar.visible": false,
	"window.menuBarVisibility": "toggle",
	//
	"security.workspace.trust.untrustedFiles": "open"
}

```
