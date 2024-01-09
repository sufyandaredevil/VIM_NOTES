# VIM NOTES

## MODES IN VIM
- **`Normal` / `Command mode` (<kbd>Esc</kbd> or `<C-[>` which means <kbd>Ctrl</kbd>+<kbd>[</kbd> in vim's language)**:
  - Vim starts in this mode, used for entering commands
- **`Insert mode` (<kbd>i</kbd>)**:
  - Mode to insert text
- **`Visual mode` (<kbd>v</kbd>)**:
  - Mode to select text
- **`Line` / `Command Line` / `Ex mode` (<kbd>:</kbd>, <kbd>?</kbd>, <kbd>/</kbd>, <kbd>!</kbd>)**:
  - Entered when being in Normal mode enabling to enter cmds like saving, searching, locating, switching and more options related to vim

---

## KEYSTROKE CONVENTIONS
- **\<BS>** - <kbd>Backspace</kbd>
- **\<CR>** | **\<Enter>** | **\<Return>** - <kbd>Enter</kbd>
- **\<Esc>** - <kbd>Escape</kbd>
- **\<Space>** - <kbd>Space</kbd>
- **\<Up>** - <kbd>↑</kbd>
- **\<Down>** - <kbd>↓</kbd>
- **\<Left>** - <kbd>←</kbd>
- **\<Right>** - <kbd>→</kbd>
- **\<Insert>** - <kbd>Ins</kbd>
- **\<Del>** - <kbd>Del</kbd>
- **\<Home>** - <kbd>Home</kbd>
- **\<End>** - <kbd>End</kbd>
- **\<PageUp>** - <kbd>PgUp</kbd>
- **\<PageDown>** - <kbd>PgDwn</kbd>
- **\<Tab>** - <kbd>Tab</kbd>
- **\<bar>** - <kbd>|</kbd>
- **\<C-X>** - <kbd>Ctrl</kbd>+<kbd>X</kbd> (instead of X, convention can be used for any letters in the keyboard
- **\<F1>** - **\<F12>** - <kbd>F1</kbd> to <kbd>F12</kbd>

---

## NAVIGATION / MOTION CMDS
### BASIC MOVES:
  > - **<kbd>k</kbd>** - move up
  > - **<kbd>j</kbd>** - move down
  > - **<kbd>h</kbd>** - move left
  > - **<kbd>l</kbd>** - move right

### WORD WISE MOVES:
  > - **<kbd>w</kbd>** - move to next word's start position (considers punctuation as a word and whitespace)
  > - **<kbd>e</kbd>** - move to next word's end position (considers punctuation as a word and whitespace)
  > - **<kbd>b</kbd>** - move to previous word's start position (considers punctuation as a word and whitespace)
  > - **<kbd>ge</kbd>** - move to previous word's end position (considers punctuation as a word and whitespace)
  > - **<kbd>W</kbd>** - move to next word (doesn't consider punctuation as a word) considering whitespace
  > - **<kbd>E</kbd>** - move to next word's end position (doesn't consider punctuation as a word)
  > - **<kbd>B</kbd>** - move to previous word's start position (doesn't consider punctuation as a word) considering whitespace
  > - **<kbd>gE</kbd>** - move to previous word's end position (doesn't consider punctuation as a word) considering whitespace

### HORIZONTAL MOVES:
  > - **<kbd>0</kbd>** - jump to the beginning of the line
  > - **<kbd>$</kbd>** - jump to the end of the line
  > - **<kbd>^</kbd>** - jump to very first character(not a whitespace) in the line

### VERTICAL MOVES:
  > - **<kbd>+</kbd>** | **`<CR>`** - jump to very first nonblank character of next line
  > - **<kbd>\-</kbd>** - jump to very first nonblank character of previous line
  > - **<kbd>gg</kbd>** - jumps to first line in the file
  > - **<kbd>G</kbd>** - jumps to last line in the file
  > - **<kbd>:</kbd>`<line_number>`** - jump to given line_number in the file
  > - **<kbd>:$</kbd>** - jump to the end of the file

### MARKED MOVES:
  > - **<kbd>m</kbd>`<character>`** - mark current cursor's position with a character (used when we want to return to some position quickly after we traverse through a file elsewhere)
  > - **<kbd>\`</kbd>`<character>`** - move cursor to marked position (grave accent)
  > - **<kbd>'</kbd><character>** - move cursor to beginning of marked position's line (single quote)
  > - **<kbd>\`</kbd><kbd>\`</kbd>** - return to previous mark | context (grave accents)
  > - **<kbd>'</kbd><kbd>'</kbd>** - return to beginning of line containing previous mark (single quotes)

### SCROLL MOVES:
  > - **`<C-f>`** - page down
  > - **`<C-b>`** - page up
  > - **`<C-e>`** - show one more line at the bottom
  > - **`<C-y>`** - show one more line at the top
  > - **`<C-o>`** - move cursor to previous position, i.e. from where the cursor is jumped from
  > - **`<C-i>`** - move cursor to lastly changed position, i.e. to the very last position where cursor was placed
  > - **`<C-]>`** - move cursor to the highlighted text's definition below cursor
  > - **<kbd>z</kbd>`<CR>`** - scroll to top of the screen where the cursor is located
  > - **<kbd>z</kbd><kbd>.</kbd>** - scroll to middle of the screen where the cursor is located
  > - **<kbd>z</kbd><kbd>-</kbd>** - scroll to bottom of the screen where the cursor is located
  > - **<kbd>H</kbd>** - move cursor to the top of the screen
  > - **<kbd>M</kbd>** - move cursor to the middle of the screen
  > - **<kbd>L</kbd>** - move cursor to the bottom of the screen

---

## TEXT MANIPULATION / OPERATION CMDS
  > - **<kbd>x</kbd>** - delete letter present below the cursor
  > - **<kbd>X</kbd>** - delete letter present before the cursor
  > - **<kbd>D</kbd>** - deletes texts from current cursor's position to end of the line
  > - **<kbd>d</kbd>`<motion_cmd>`** - delete texts from current cursor's position upto given **`<motion_cmd>`**
  >    - **<ins>Example:</ins> <kbd>d</kbd><kbd>w</kbd>** - deletes a word from the cursor's current position
  > - **`<count>` `<operation>` `<motion_cmd>`** - delete current line and contents where cursor is <count> times upto given motion
  >   - **<ins>Example:</ins> <kbd>5</kbd><kbd>d</kbd><kbd>w</kbd>** - delete 5 words

  **<ins>NOTE:</ins>**
  - `[count]` `{operation}` `[count]` `{motion}` combo can also be performed

---

## CUT COPY PASTE (DELETE,YANK,PUT)
  > - **<kbd>D</kbd>** - cut text from cursor till end and place in the UNNAMED/DEFAULT register
  > - **<kbd>dd</kbd>** - cut line and place in the UNNAMED/DEFAULT register
  > - **<kbd>x</kbd>** - cut text and place in the UNNAMED/DEFAULT register
  > - **<kbd>P</kbd>** - put text before the cursor
  > - **<kbd>p</kbd>** - put text after the cursor
  > - **<kbd>y</kbd>`{motion}`** - yank text wrt given motion
  > - **<kbd>yy</kbd>** - yanks whole line's content present below cursor

  **<ins>NOTE:</ins>**
  - Above commands actually don't delete text, i.e they clear text and save into a register (register is a clipboard-like storage location for vim)

---

## HELP SYSTEM IN VIM

:help - opens the vim's help.txt(in readonly mode) which is a text file, where if we press <C-g> we can see the location of where the file help.txt is located
:help <command> - shows info about the <command> given from the help.txt file
Eg: :help dd
We can exit the help.txt just like we exit other files using the :q cmd

NOTE: when we see infos present within square brackets ([]) always know that they are optional
i.e. for the above example the description we see will be "Delete [count] lines [into register x] linewise.", where count and into register x are optional to be considered
We can also get help on other various subjects and this is identified by the color when help.txt is viewed in vim.
Eg: for the optional subject we saw previously ([count] which is highlighted in purple(color might vary)) can also be viewed in the help as follows:
:help count
We can also go to the definition of a highlighted word like count, linewise but keeping the cursor over it and press <C-]>

Other Important Examples:

    1 - :help :q
    NOTE: for the above definition we see that from ':q[uit]', 'uit' is placed inside [] brackets which means they are optional to type i.e. :q | :quit, both means the same

    2 - :h Ctrl-f|^f - help description for cmds with CTRL button presses. Here ^ can be used instead of typing 'Ctrl-'

    3 - :help :help
    NOTE: even for the above definition the words elp from help are optional to type i.e. :help | :h, both means the same

Also when typing :h | :help <cmd>, when we wanna see all different combinations of entered <cmd>(similar to auto suggest) we can type:
:h :q[PRESS CTRL + d now], which shows all possibilities of q i.e. :q, :quit, :quita, :qa etc., also:
:h :q[PRESS TAB BUTTON now], which does the same as above but we can select using enterkey from the possibilities shown, and SHIFT + TAB reverses the possibility traversing

Help system is also useful to know alternatives for a known command
Eg: :f can be used instead of using <C-g> which can be found from the help.txt documentation after we searching using :h ^g

----------------------------------------------------------------------------
REGISTERS IN VIM
----------------------------------------------------------------------------

Types of Registers:
    UNNAMED/DEFAULT = "" (holds text from d,c,s,x,y ops/contains last operated on text)
    NUMBERED = "0, "1,..., "9 (generally contents in these registers shift with each d or c ops)
        ("0 holds last text yanked(y))
        ("1 holds last text deleted(d) or changed(c))
    NAMED = "a, "b,..., "z (totally controlled by user also "A,..., "Z can also be used but "a & "A mean the same.
        NOTE: in context to commands when used with capital alphabets (i.e. uppercase named register) contents are appended instead of being replaced or created)
        Eg: copying something to "a and again copying something would mess up the older content so we can use "A instead of "a that in result appends the content 
    BLACKHOLE = "_ (usually used when we don't wanna mess up the numbered register's content while performing vim ops)


To view specific/all register/s --> :reg [register(s)]
Eg--> :reg - view all register's contents
Eg--> :reg 1z - view register 1 and register z's contents
Eg--> :reg " - view default register's content

To delete a line without changing the contents in the register --> "_dd

To put/paste content from a register --> "<register_type_specific><put_cmd>
Eg: "0P - put text from register 0 to the current file
NOTE: same goes for copying content to a specific type of register.
Eg: "ayy - yank whole line's content below the cursor to register a

To perform repetition with registers --> [count][register]command | [register][count]command
Eg:  2"hp | "h2p - paste(p) content from h register("h) twice(2)

----------------------------------------------------------------------------
TEXT TRANSFORMATION IN VIM
----------------------------------------------------------------------------

R - replaces text present below the cursor and beyond then stays in replace mode
r - replace only one text present below the cursor then goes to normal mode automatically

[count]cc|S - deletes/cuts whole [count] line's content preserving indentation(if any) and stays in insert mode
c<motion_cmd> - deletes/cuts from current cursor's position till given motion and stays in insert mode
C - delete/cuts from current cursor's position till end of current line and stays in insert mode(alternative to the cmd 'd$a')
s - delete letter present below the cursor and stays in insert mode

~ - Toggles a single alphabet's case present under the cursor
g~<motion> - Toggles alphabet's case present under the cursor till given motion
Eg--> g~w - toggles case of the word present under the cursor
g~~ - Toggles all alphabets case in the current cursor's line (alternative to g~$)
gU<motion> - Force toggle alphabets to uppercase under the cursor till given motion
gUU - Force toggle all alphabets to uppercase present under the cursor's line
gu<motion> - Force toggle alphabets to lowercase under the cursor till given motion
guu - Force toggle all alphabets to lowercase present under the cursor's line

[count]J - joins succeeding line to the current cursor's line by adding a space (if not present already) and repeats this [count] times
[count]gJ - same as above put doesn't include the spacing logic in this one and repeats this [count] times

----------------------------------------------------------------------------
SEARCH/FIND,REPLACE/SUBSTITUTION IN VIM
----------------------------------------------------------------------------

f<character_you're_searching_for> - forward search in cursor's line and places the cursor on the character you searched for
F<character_you're_searching_for> - backward search in cursor's line and places the cursor on the character you searched for
t<character_you're_searching_for> - forward search in cursor's line and places the cursor before the character you searched for
T<character_you're_searching_for> - backward search in cursor's line and places the cursor after the character you searched for
    ; - forward cycle(for f,t)/backward cycle(for F,T) through found searches
    , - backward cycle(for f,t)/forward cycle(for F,T) through found searches

NOTE: [count] could also be mentioned with f,F,t,T. Eg --> 2f<character_you're_searching_for> - goto 2nd search result of the character you searched for

To delete from current cursor's position uptill given searched text in the same line --> dt<the_character_uptill_you_wanna_delete>
To delete from current cursor's position upto given searched text in the same line --> df<the_character_upto_you_wanna_delete>
Eg: if 'Hello world' is the string then:
    'dtw' deletes 'Hello '
    'dfw' deletes 'Hello w'

/<text_you're_searching_for> - forward search whole file
?<text_you're_searching_for> - backward search whole file
* - forward search for the next occurence of the entire word only that's under the cursor
# - backward search for the previous occurence of the entire word only that's under the cursor
    n - forward cycle(for /,*)/backward cycle(for ?,#) through found searches
    N - backward cycle(for /,*)/forward cycle(for ?,#) through found searches

To delete from current cursor's position uptill given searched text --> d/<the_text_uptill_you_wanna_delete>
To yank text from current cursor's position uptill given searched text into a register --> "<register>y/<the_text_uptill_you_wanna_delete>

For Text Substitution:
:[range]s/{old_text}/{new_text}/[flags] - substitutes old_text to new_text for given range(can be a number n or n,m) wrt given flags

[flags] could be as follows:
g - replace all occurrences of old_text in the line (without g - only first)
i - ignore case of given old_text
I - considers case of given old_text
NOTE: the [flags] is applied per line when a range is given

[range]s could be as follows:
. - current line
$ - last line in the file
% - All lines (entire file, i.e. alternative to 1,$)
/<PATTERN-1>/,/<PATTERN-2>/ - <PATTERN-1>, <PATTERN-2> are text that can be given as a scope for substitution

Important Examples:

Eg--> :s/The/A/ - substitute occurence of 'The' to 'A' in the current cursor's line only
Eg--> :1s/The/A/g - substitute all occurences of 'The' to 'A' in the 1st line only
Eg--> :1,5s/The/A/g - substitute all occurences of 'The' to 'A' from the 1st to 5th line
Eg--> :%s/The/A/g - substitute all occurences of 'The' to 'A' from the entire file
Eg--> :.,$s/The/A/g - substitute all occurences of 'The' to 'A' from the current line to the last line in the file
Eg--> :/Start/,/End/s/The/A/g - substitute all occurences of 'The' to 'A' only within the given pattern 'Start' to 'End'
Eg--> :/Start/,$s/The/A/g - substitute all occurences of 'The' to 'A' from the given pattern 'Start' to the last line in the file

If there are forward slashes within the text itself we need to escape them while substituting
Eg: if the given text /var/spool has to be replaced with /usr/local we do the following:
--> :s/\/var\/spool/\/usr\/local/
Or there's an alternative method where we can change the pattern separator as follows:
--> :s#/var/spool#/usr/local#

----------------------------------------------------------------------------
TEXT OBJECTS IN VIM
----------------------------------------------------------------------------

NOTE:
a - includes delimiter (remember as all)
i - doesn't includes delimiter (remember as inside)

general form of creating a text object cmd:
[register(s)]{operation}{a|i}{motion|text_object}
Here operation could be d,c,g,y etc
text_object could be >,<,{,},[,],",' etc
motion could be y,w,c etc

aw - a word with the operation performed
iw - inner word with the operation performed
Eg--> daw, diw

as - a sentence with the operation performed (.,!,? is the separator)
is - inner sentence with the operation performed
Eg--> das, dis

ap - a paragraph with the operation performed(newline is the separator)
ip - inner paragraph with the operation performed
Eg--> dap, dip

To illustrate the usage of above cmds consider 'Hello World! how are you?' where we want to delete the word 'Hello'
if we perform 'dw' by placing the cursor above the first 'l' in 'Hello' we get the output: 'He World! How are you?'
but in case of 'daw' if we place the cursor anywhere but above the word 'Hello' we get the output: 'World! How are you?'
which means that Text Objects doesn't consider the place where we place our cursor but we only need to place the cursor with the motion's context i.e. if we are operating a word we need to stay above the word atleast/in case of a bracket within the scope bracket atleast

Important Examples for Text objects (Programming):

Eg: colors = ['red', 'green', 'blue']
To delete values inside [] and stay in insert mode:
--> ci[ | ci]
And to delete the brackets also:
--> da[ | da]
NOTE: same goes for <> (angular brackets) i.e. ci< | ci>' & da< | da>

Eg: print(colors)
To delete the variable within () and stay in insert mode:
--> ci( | ci) or --> cib | cib
And to delete the parenthesis also:
--> da( | da) or --> dab | dab
NOTE: same goes for {} (curly brackets) i.e. ci{ | ci}' or ciB | ciB & da{ | da} or daB | daB

Eg: NAME = "VIM"
To delete values within "" and stay in insert mode:
--> ci"
And to delete the 2 doubt quotes also:
--> da"
NOTE: same goes for ' & ` (single quote & backtick) i.e. ci' | da' & ci` | da`

Eg: <p>This is a <b>new</b> tag </p>
To delete the content present within the paragraph tag (<p> THESE_ONES </p>) and stay in insert mode:
--> cit
And to delete the angular brackets also:
--> dat
NOTE: in this example there is a nested tag(<b>new</b>) so to perform text manips. atleast place the cursor at the start of the angular bracket(OVER HERE --><b>new</b>)
Same goes for nested [],{},"" etc

----------------------------------------------------------------------------
MACROS IN VIM
----------------------------------------------------------------------------

q{register}<all_your_cmds> - to start recording and store the vim routine/macro in a register
q - to stop recording and vim routine/macro'll be saved in the particular register you mentioned while starting the recording 
[count]@{register} - replay the recorded macro from the register [count] times
:[range(s)] normal @{register} - replay the recorded macro from the register for the given range only. For more about ranges view Text Substitution in SEARCH/FIND,REPLACE/SUBSTITUTION IN VIM Section
[count]@@ - repeat most recently executed macro [count] times

NOTE: use the capital alphabets to append macros if missed while recording at start

Macro Best Practices:
    Normalize the cursor position (0)
    Perform edits & ops
    Position your cursor to enable easy replays (j)

To create macros in vimrc file:
let @<register_name> = '<key_strokes>'
Eg-->let @<register_name> = 'ITODO: ^[j'
NOTE: to create the <Esc> we need to create a literal i.e. press [CTRL] + v in normal mode that creates ^ as a literal and then press [ESC]

----------------------------------------------------------------------------
VISUAL MODE CMDS IN VIM
----------------------------------------------------------------------------

visual mode is used for selecting text
v{motion} - starts text selection continued with next motion
V{motion} - for line selection continued with next motion
<C-v>{motion} - means block selection of text continued with next motion)

gv - reselect the recently visualised text(used when you're in line A select text and deny selecting and then goto line B and thinking of selecting line A's content at ease, this can be used)
o - To switch between start and end point of selection (this cmd should be used when in visual mode and is mostly used when we forget to select a text before our start point of selection and to switch back to the end point of selection by again pressing it
O - Same as above but switches horizontally only for <C-v>

NOTE: mostly we can create an optimised vim cmd combination without visual mode cmds itself but to be sure on what text we're operating on could be better
With visual line mode(V) when appending multiple text only 'A' works and not the 'a' cmd
With visual block mode(<C-v>) when inserting multiple text only 'I' works and not the 'i' cmd
With visual block mode(<C-v>) when replacing/changing multiple text only 'c' works and for 'd' only the first selected text will be changed/replaced

After selecting a set of text and if we press ':' we get a symbol: '<,'>
after the symbol we can start typing substitution cmds as follows:
:'<,'>s/The/A/g - Replace all occurences of 'The' to 'A' within the selected scope of text
:'<,'>{center|ce}<center_within_how_many_lines> - center align the selected text within given number as limit
:'<,'>{left|le}<how far to go from the left> - left align the selected text within given number as limit
:'<,'>{right|ri}<how far to go from the right> - right align the selected text within given number as limit

Other Important Examples:

v{motion}U|u|~ - change/toggle selected text alphabets to uppercase|lowercase|opposite case
v/<the_text_upto_you_wanna_delete>d - select & delete text from current cursor's position to the_character_upto_you_wanna_delete
vi' | va' - select text present within ' | select text present within and along with '
viw | vaw - select inner word| select all current word with delimiter(space)
vip | vap - select inner paragraph| select all current paragraph with delimiter(newline)
Vr<character> - select cursor line's text and replace all with given character

----------------------------------------------------------------------------
VIMRC CONFIGS IN VIM
----------------------------------------------------------------------------

:version - shows version and info about where system & user vimrc file location

General Pattern of set commands in vim application:
:set <cmd>|no<cmd> - to enable/disable an option
:set <cmd>! - to toggle that option on/off
:set <cmd>? - to check whether cmd set/not, if <cmd> is set output is <cmd> else no<cmd>
:set <cmd1>[=val1],...,<cmd2>[=val2] - for setting multiple options
:set <cmd1>& - for setting an option value back to its default
:set - shows all the options that are set other that the defaults are displayed

Basics of :set command:
To view possible values to set for an option we can use the :h or the :help option to view an option's specifics
Eg: ':h hls' shows 'boolean (default off)' which says that the value is either true or false which can be toggle or set using the :set hls | :set hls!
if we want to reset it we can use :set nohls or toggle off with ! and check whether the change has taken place using : set hls?
NOTE: For any command try searching for all possibilities i.e. for example in case of 'history' cmd there are different ones, as follows:
:h :history 
:h 'history'(goto option documentation which we need in this case)
:h history
So try searching correctly for the one you're in need of

Now lets create a new vimrc file in ~/.vimrc (for linux, MAC) | $HOME/_vimrc (for windows) using the :e <vimrc_config_file_path> cmdline cmd | :mkvimrc [vimrc_config_file_path]
NOTE: the following .vimrc|_vimrc mockup contains description about some commands through comments(starting with ")

(.vimrc | _vimrc)____________________________________________________________________________________________________________________________________________________
| 
| "shows a menu when using tab completion
| set wildmenu
| 
| set ignorecase
| set smartcase
| 
| "set backup
| set backup
| "set bex=SOMETHING
| 
| "set color scheme
| "to see available color schemes use --> :color <TAB>
| color slate
| 
| "to download custom color scheme from internet, we can place it in:
| " $HOME/vimfiles/colors
| " ~/.vim/colors
| 
| "map KEY to a set of KEYSTROKES:
| map <F2> iSufyan<CR>CS Major<CR><ESC>
| "the above mapping says, when pressing F2 we get into insertmode(i) type Sufyan, insert newline(<CR>) repeat typing and going to normal mode(<ESC>)
| 
| "map KEY to a set of KEYSTROKES without overwriting the vim defaults:
| map <leader>w :w!<CR>
| "the above mapping says, when pressing backward slash(\ = <leader> (\ is default)) then press w it executes the :w!<CR> without overwriting the w 'cmd' that moves forward by a word
| 
| "to change the <leader> key:
| "let mapleader="<ANY_KEY>"
| 
| "NOTE: vmap - maps for visual mode only
| "nmap - maps for normal mode only
| "vnoremap - disables recursive key maps for visual mode only
| "nnoremap - disables recursive key maps for normal mode only
|____________________________________________________________________________________________________________________________________________________________________
to set and execute/run the configs from vimrc file during the editing of vimrc and runtime of vim itself without restarting the application
--> :source <vimrc_config_file_path>

Other Examples of Options that can be set in vim | vimrc file:

:set ruler - shows line and column number in lower bottom side of vim(after set few <C-g> info is hidden to avoid metadata redundancy)
:set shiftwidth=<number> - sets the number of space indents when pressing >>|<< (default=8)
:set tabstop=<number> - sets the number of tab indents when pressing tab (default=8)
[NOT SURE ABOUT THIS OPTION's USAGE/DEFINITION] :set expandtab! - toggle inserting spaces instead of tabs when pressing the tab button
:set list! - toggle whitespace characters(space,tabs,newline) to be visible with the help of a literal (highlighted blue in vim)
:set is! | incsearch! - to toggle incremental search, i.e. constantly places the cursor in the text you search and keep incrementing the placement until you're done typing your search keyword
:set hls! | hlsearch! - to toggle search highlighting 
:set nu! | number! - to toggle number line

Also to view all options available in vim
--> :h option-list
To view all options with brief description of them in vim
--> :options

----------------------------------------------------------------------------
VIM GUI(GVIM & MACVIM)
----------------------------------------------------------------------------

With GUI version we have access to system clipboard
There are other 2 different types of registers in vim GUI:

"+ - (for linux, MAC, Windows) System clipboard register
    when pressing [CTRL]|[CMD] + c in an another application the text is copied to this register
    On pressing "+P it pastes the clipboard's content in vim GUI and places cursor at the end character of copied text
    On pressing "+gP it pastes the clipboard's content in vim GUI and places cursor after end character of copied text

"* - (for MAC, Windows) Same as "+
    (for Linux) Contains text that is highlighted/text selected by mouse in an another application and pasted using middle click

Also we can yank or copy text present in vim to system's clipboard using --> "+yy

To set system clipboard as the unnamed register i.e. make vim GUI act morelike other applications by using the sys. clipboard
(for MAC, Windows) -->:set clipboard=unnamed 
(for Linux) --> :set clipboard=unnamed+ 

We do have a config specific for vim like vimrc:
.gvimrc (for MAC, Linux) | _gvimrc (for Windows)
NOTE: This file is read by vim GUI at start only after reading the vimrc file
Also :version could be used to find the location of this file

To set a different font in vim GUI:
:set gfn=*[PRESS ENTER NOW]
select the font and then apply
To view the config cmd used to set it later in vimrc use --> :set gfn?
NOTE: if fontname has spaces in it make sure to escape then when setting them in cmdline of vim

For More on GUI specifics:
:h gui

----------------------------------------------------------------------------
BUFFERS IN VIM
----------------------------------------------------------------------------

Buffers are generally something that is stored temporarily in memory and in context to vim files that are temporarily opened and stored and saved in memory
In vim when we generally open multiple files we see one at the foreground by at the back there might be multiple files running with the help of the buffer

To open multiple files with vim --> vim <file_name_1>,...<file_name_n>|<file_name(s)_with_regex

To view all buffers/opened files in vim --> :buffers | :ls

Buffer jump commands:
Specific jumps --> :buffer <file_name|buffer_number>|:b<file_name|buffer_number> (buffer_number|file_name can be found from the :buffers command | :b <your_least_text_here>[PRESS TAB NOW] to view all possibilities)
To move to next & previous buffer --> :bnext|:bn && :bprevious|:bp (cycles to start/end after reaching the end/start)
To move to buffer 1 & buffer last --> :bf & :bl
<C-^> - shift back and forth between current opened and previously opened buffers (the way we know where we jump alternatively is with the help of %a(a means active & displayed in window) and # shown in :b cmd where %a means the current file and # which was opened previously when pressing <C-^> cmd)
NOTE: also :b# | :b%a can be used to switch between buffers
Also the + sign is shown in the :b table after a change has been done to the buffer and not saved, so we need to save changes before going to the next buffer if we haven't enable the :set hidden option or we can use the force(!) operator when jumping i.e. :b<jump_to_ref>!

global substitution in all opened buffers --> :bufdo %s/#/a/g | w (change '#' to 'a' in all opened buffers) and write the changes
NOTE: | operator from the above cmd is the command separator that lets vim execute one command after another. In the above case its write after substitution

Add new buffer --> :badd <file_name>
Delete current buffer --> :bd

:wall - write all file changes that are changed
:set hidden - make a file hidden when a change is made and not saved when jumping to annother cmd
:e <file_name(s> - open file(s)
:E - open explorer (execute commands just like normal vim)

----------------------------------------------------------------------------
WINDOWS IN VIM
----------------------------------------------------------------------------

:sp[file_name] - Split window horizontally (when file_name not given, the next file present in the buffer is shown in the next window)
:vs[file_name] - Split window vertically (when file_name not given, the next file present in the buffer is shown in the next window)
:on | :only - Close all windows expect the cursor placed window:

Buffer specifics to windows:
:ba - open all buffers in a split window
:windo %s/#/@g - substitution performed in active windows

To move cursor to specific window:
--> <C-w><j|k|h|l> - to move to the bottom|top|left|right window opened
EXTRA: we can map the above cmd just in case: i.e. Eg: map <C-h> <C-w>h | map <leader>h <C-w>h

Resizing windows commands:
<C-w>+|<C-w>- - de/increase specific window height (where cursor is at)
<C-w>>|<C-w>< - de/increase specific window width (where cursor is at)
<C-w>_ - maximize height of window (where cursor is at)
<C-w>| - maximize width of window (where cursor is at)
<C-w>= - make all windows the same size
<C-w><C-w> - Switch between files in vim

Moving window commands:
<C-w>r - rearrange windows by rotating clockwise
<C-w>R - rearrange windows by rotating anti-clockwise
<C-w><J|K|H|L> - to move the current cursor's window to the very bottom|top|left|right of the screen using the full height|width of the screen

### REMAINING:
    |--------(following block to be replaced elsewhere later due to not being navigation cmds)----------------------
    |  <C-g> - displays file's name, metadata, status, current & total line, cursor's position in the current file, how far we're down a file(in %), column number where cursor is at
    |  g<C-g> - displays even more metadata that the above cmd
    |  
    |  >> - indent text
    |  << - deindent text
    |  . - repeats previous command
    |  u - undo previous change
    |  U - restore current cursor's line change
    |  <C-r> - redo previous change
    |  
    |  :e <path|file_name>- creates a new file in relative path by default
    |  :w - saves the current file
    |  :wq - write and quit
    |  :q - quit if no changes are done and if changed, warning is shown
    |  :q! - quit without write
    |  NOTE: the symbol ! when used in command/line mode(:) generally means to force an action, toggle setting, execute external cmd etc
    |  
    |  i - goto insert mode(i.e. before the cursor)
    |  I - goto 0th position in current cursor's line and goto insert mode
    |  a - goto insert mode(i.e. after the cursor)
    |  A - goto $th position in current cursor's line and goto insert mode
    |  O - Insert new line below the cursor and enter insert mode
    |  o - Insert new line above the cursor and enter insert mode
    |  
    |  for repetition of text insertion:
    |  [count] [above_cmds] <your_text_here> <Esc>
    |  Eg: 5i*<Esc> - places '*' 5 times horizontally
    |  Eg: 5o*<Esc> - places '*' 5 times vertically
    |  
    |---------------------------------------------------------------------------------------------------------------
