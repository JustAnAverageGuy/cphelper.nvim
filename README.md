# cphelper.nvim
A plugin for automating tasks in competitive programming like downloading testcases, compiling and testing. Supports C, C++, Python and Lua. Does not suppport Windows. It should work on Linux, macOS and BSDs.

## Requirements
- [competitive-companion](https://github.com/jmerle/competitive-companion) browser extension
- Plugin: [`nvim-lua/plenary.nvim`](https://github.com/nvim-lua/plenary.nvim/) (Install using your plugin manager)
- Luarocks: [`http`](https://daurnimator.github.io/lua-http/).
	- If you use packer.nvim to manage plugins you can
	```lua
	use {'p00f/cphelper.nvim', rocks = 'http', requires = 'nvim-lua/plenary.nvim'}
	```
	- Otherwise install it from luarocks using
	`sudo luarocks install http`

## Instructions
- Use `:CphReceive` and press the "parse task" button in the extension to prepare files. This will open an empty solution file in your preferred language. (See )
- `:CphTest [numbers]` to test your solution. If testcase number(s) is specified, only those cases are run, otherwise all cases are run.
- `:CphRetest [numbers]` to test the same binary without recompiling.
- `:CphEdit [number]` to edit/add a testcase.
- `:CphDelete [numbers]` to delete testcases.

The filetype of the floating window showing results is `Results`, so you can disable your indentline/cursorline plugins for this filetype.
## Prefs
- `g:cphdir` : The directory in which contests are stored (default `~/contests`) (Specify **absolute path**)
- `g:cphlang` : Preferred language for the first solution file opened. You can open another `solution.language` file for a particular problem using `:e` and that file will be used.
- `g:c_compile_command` : Command for compiling C files (default `gcc solution.c -o c.out`). The input file must be `solution.c` and the output file must be `c.out`, this pref is  only for compile flags.
- `g:cpp_compile_command`: Command for compiling C++ files. See above. (default `g++ solution.cpp -o cpp.out`)
## Directory structure
```
Contests directory (g:cphdir)
├── Judge 1
│   ├── Contest 1
│   │   ├── Problem 1
│   │   │   ├── input1
│   │   │   ├── input2
│   │   │   ├── output1
│   │   │   ├── output2
│   │   │   ├── solution.c
│   │   │   ├── solution.cpp
│   │   │   └── solution.py
│   │   └── Problem 2
│   │       ├── input1
│   │       ├── output1
│   │       ├── solution.c
│   │       ├── solution.cpp
│   │       └── solution.py
│   └── Contest 2
│       └── Problem 1
│           ├── input1
│           ├── output1
│           ├── solution.c
│           ├── solution.cpp
│           └── solution.py
└── Judge 2
    └── Contest 2
        └── Problem 1
            ├── input1
            ├── output1
            ├── solution.c
            ├── solution.cpp
            └── solution.py
```
## Screenshot
<img src="https://raw.githubusercontent.com/p00f/cphelper.nvim/main/screenshot.png" />

## Known bugs
   None as of now :)
