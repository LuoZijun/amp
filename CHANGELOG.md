### 0.5.0

* Added caching to syntax highlighting, to improve performance for large buffers
  * See https://medium.com/@jordan_98525/incremental-parsing-in-amp-ba5e8c3e85dc for details

### 0.4.1

* Fixed syntax highlighting
  * Scopes were bleeding into one another; we now defer to HighlightIterator
  * See https://github.com/jmacdonald/amp/issues/22 for details

### 0.4.0

* Application event loop is now threaded
  * Most notably, open mode indexing is now run in a separate thread
* Scrolling is now line wrap-aware
* View now redraws when terminal is resized
* Search/select modes now have empty state messages
  * e.g. open mode will now display "Enter a query" rather than "No results" when no query is present
* Open mode now displays its path when indexing
* Escape in normal mode now scrolls cursor to center, via new default keybinding
* app_dirs dependency bumped to a version that compiles on newer versions of Rust
* Type-specific configuration now supports full filenames (e.g. "Makefile")
* Various refactoring

### 0.3.4

* Documentation updates
* Added the ability to save new buffers without paths (created in normal mode
  using the `B` key binding); a new "path" mode prompts before saving.
* Added the ability to load user/custom themes from the `themes` configuration
  sub-directory
* Added a benchmark for buffer rendering
* Bumped native clipboard library dependency
* Added semi-colon delete key binding to select line mode

### 0.3.3

* Documentation updates
* buffer::backspace command no longer switches to insert mode
  (this is relegated to the default keymap)
* Invalid keymap configurations now display the offending mode

### 0.3.2

* Fix case-insensitive open mode search with uppercase characters
* Add class and struct identifiers to symbol mode whitelist
* Documentation and README updates

### 0.3.1

* Bumped copyright year to 2018
* Updated CI config to run on stable release channel
* Documentation site and content updates
* Added `application::display_default_keymap` command
* Added ability to delete current result in search mode

### 0.3.0

* Switched to Rust stable release channel
* New command mode (run any built-in commands through a search/select UI)
* User-defined preferences, syntaxes, and keymaps
* New confirm mode, applied primarily to closing or reloading buffers
* New command to view syntax scope at cursor
* Extracted all logic from input handlers
* Migrated input handling to simple key => command mappings
* New select_all command
* Updated native clipboard library


### 0.2.0

* Added theme selection mode
* Quality improvements to command error reporting
* Updated search mode to better handle "no matches" state
* Treat hash/pound symbol as delimeter when using word-based movement
* Added initial preference implementation
* Under the hood improvements to search/select modes (open, symbol, theme, etc.)
* Updated search/select modes to perform case insensitive searches

### 0.1.0

* Initial release
* Added proper error handling to all commands
* Updated main loop to display command errors
