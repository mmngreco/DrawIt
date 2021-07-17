# Drawit

## joshzcold fork changes

Drawing functions have been changed to global scope after running `:Drawit`

This allows for remapping the hardcoded mappings coming from Drawit

Lua:

```lua
function()
   vim.cmd[[call DrawIt#DrawItStart()]]
   vim.cmd[[set timeoutlen=100]]
   vim.api.nvim_buf_set_keymap(0, "n", "J", ":call DrawIt#DrawDown()<cr>", {noremap = true})
   vim.api.nvim_buf_set_keymap(0, "n", "K", ":call DrawIt#DrawUp()<cr>", {noremap = true})
   vim.api.nvim_buf_set_keymap(0, "n", "L", ":call DrawIt#DrawRight()<cr>", {noremap = true})
   vim.api.nvim_buf_set_keymap(0, "n", "H", ":call DrawIt#DrawLeft()<cr>", {noremap = true})
   vim.api.nvim_buf_set_keymap(0, "n", "JL", ":call DrawIt#DrawSlantDownRight()<cr>", {noremap = true})
   vim.api.nvim_buf_set_keymap(0, "n", "JH", ":call DrawIt#DrawSlantDownLeft()<cr>", {noremap = true})
   vim.api.nvim_buf_set_keymap(0, "n", "KL", ":call DrawIt#DrawSlantUpRight()<cr>", {noremap = true})
   vim.api.nvim_buf_set_keymap(0, "n", "KH", ":call DrawIt#DrawSlantUpLeft()<cr>", {noremap = true})
end

```

## original readme

This is a mirror of http://www.vim.org/scripts/script.php?script_id=40

DrawIt is a plugin which allows one to draw lines left, right, up, down, and along both slants. Optionally one may "cap" the lines with arrowheads. One may change the horizontal, vertical, slant, and crossing characters to whichever characters one wishes.

Its easy to start and stop DrawIt: use

`\di` to start DrawIt and
`\ds` to stop DrawIt.

The alpha/beta version is available at http://www.drchip.org/astronaut/vim/index.html#DRAWIT.

When DrawIt has been started you may use the number pad to leave a trail of dashes, vertical bars, etc. The lines will be expanded as needed to accomodate your drawing. DrawIt can also draw boxes and ellipses on a blank-filled area (DrawIt can produce these) which can be useful for drawing boxes around comments.

Viart's <drawing.vim> has been merged with the original DrawIt (vimscript#11) (by permission). Use visual-block selection to specify starting and ending positions and a Bresenham line drawing algorithm will be used to connect the two. DrC has written an ellipse-drawing Bresenham-style procedure: again, use the visual block selection to specify a box to contain the ellipse and \e to trigger the ellipse drawing.

DrawIt incorporates an "erase" mode, toggled by the <space> key, that will leave a trail of blanks behind and under the cursor as it is moved by the number pad. Using the shift-arrow keys, DrawIt will move the cursor, expanding lines and inserting spaces as needed, without changing underlying text.

DrawIt is now in the vimball format, which is understood by the new Vim 7.0 release. After decompressing the DrawIt.vba.gz file, edit it with Vim, and then source it (:so %). The components of DrawIt will then be placed where they belong, based on your Vim's runtimepath.

DrawIt records many user options that affect DrawIt and all maps that starting DrawIt creates. When DrawIt is terminated it restores the user's maps and options. DrawIt's number pad maps will expand the file as necessary to accomodate the drawing, automatically.

Supported Features
|||
|---|---|
|<kbd><left></kbd>| move and draw left|
|<kbd><right></kbd>| move and draw right, inserting lines/space as needed
|<kbd><up></kbd>| move and draw up, inserting lines/space as needed|
|<kbd><down></kbd>| move and draw down, inserting lines/space as needed|
|<kbd><s-left></kbd>| move left|
|<kbd><s-right></kbd>| move right, inserting lines/space as needed|
|<kbd><s-up></kbd>| move up, inserting lines/space as needed|
|<kbd><s-down></kbd>| move down, inserting lines/space as needed|
|<kbd><space></kbd>| toggle into and out of erase mode|
|<kbd>></kbd>| draw `->` arrow|
|<kbd><</kbd>| draw `<-` arrow|
|<kbd>^</kbd>| draw `^` arrow|
|<kbd>v</kbd>| draw `v` arrow|
|<kbd><pgdn></kbd>| replace with a \, move down and right, and insert a \|
|<kbd><end></kbd>| replace with a /, move down and left, and insert a /|
|<kbd><pgup></kbd>| replace with a /, move up and right, and insert a /|
|<kbd><home></kbd>| replace with a \, move up and left, and insert a \|
|<kbd>\></kbd>| draw fat -> arrow|
|<kbd>\<</kbd>| draw fat <- arrow|
|<kbd>\^</kbd>| draw fat ^ arrow|
|<kbd>\v</kbd>| draw fat v arrow|
|<kbd>\a</kbd>| draw arrow based on corners of visual-block|
|<kbd>\b</kbd>| draw box using visual-block selected region|
|<kbd>\e</kbd>| draw an ellipse inside visual-block|
|<kbd>\f</kbd>| fill a figure with some character|
|<kbd>\h</kbd>| create a canvas for \a \b \e \l|
|<kbd>\l</kbd>| draw line based on corners of visual block|
|<kbd>\s</kbd>| adds spaces to canvas|
|<kbd><leftmouse></kbd>| select visual block|
|<kbd><s-leftmouse></kbd>| drag and draw with current brush (register)|
|<kbd>\ra</kbd>| ... <kbd>\rz</kbd> replace text with given brush/register|
|<kbd>\pa</kbd>| ... like <kbd>\ra</kbd> ... <kbd>\rz</kbd>, except that blanks are considered|
to be transparent

Thank you for ranking DrawIt!
