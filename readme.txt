Visual Studio 2019 GUI build files for:
	scintilla
	SciTE



created intermediate projects for:

	lib_lex.lib	: lexlib - support functions for lexing

	lib_lexers.lib	: consolidated lexer library
		\_ uses lib_lex.lib

	lib_sci.lib	: platform neutral part of edit control
		\_ uses lib_lex.lib [and optionally lib_lexers.lib]

	lib_lua.lib	: LUA language support

	lib_te.lib	: platform neutral part of text editor
		\_ uses lib_sci.lib,lib_lua.lib

...to reduce overlap of build processes.

Options in the build configurations cause some additional files to be
output of the libraries they should be in. For example, the lexer
catalog has two build forms. So, where used it needs to be included in
the project.


Installing SciTE in three different ways:

	SciTE_portable.exe

	SciTE.exe
	SciLexer.dll
or
	SciTE.exe
	Scintilla.dll
	Lexilla.dll
