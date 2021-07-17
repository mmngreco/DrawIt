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

|<kdb><left></kdb>| move and draw left|
|<kdb><right></kdb>| move and draw right, inserting lines/space as needed
|<kdb><up></kdb>| move and draw up, inserting lines/space as needed|
|<kdb><down></kdb>| move and draw down, inserting lines/space as needed|
|<kdb><s-left></kdb>| move left|
|<kdb><s-right></kdb>| move right, inserting lines/space as needed|
|<kdb><s-up></kdb>| move up, inserting lines/space as needed|
|<kdb><s-down></kdb>| move down, inserting lines/space as needed|
|<kdb><space></kdb>| toggle into and out of erase mode|
|<kdb>></kdb>| draw `->` arrow|
|<kdb><</kdb>| draw `<-` arrow|
|<kdb>^</kdb>| draw `^` arrow|
|<kdb>v</kdb>| draw `v` arrow|
|<kdb><pgdn></kdb>| replace with a \, move down and right, and insert a \|
|<kdb><end></kdb>| replace with a /, move down and left, and insert a /|
|<kdb><pgup></kdb>| replace with a /, move up and right, and insert a /|
|<kdb><home></kdb>| replace with a \, move up and left, and insert a \|
|<kdb>\></kdb>| draw fat -> arrow|
|<kdb>\<</kdb>| draw fat <- arrow|
|<kdb>\^</kdb>| draw fat ^ arrow|
|<kdb>\v</kdb>| draw fat v arrow|
|<kdb>\a</kdb>| draw arrow based on corners of visual-block|
|<kdb>\b</kdb>| draw box using visual-block selected region|
|<kdb>\e</kdb>| draw an ellipse inside visual-block|
|<kdb>\f</kdb>| fill a figure with some character|
|<kdb>\h</kdb>| create a canvas for \a \b \e \l|
|<kdb>\l</kdb>| draw line based on corners of visual block|
|<kdb>\s</kdb>| adds spaces to canvas|
|<kdb><leftmouse></kdb>| select visual block|
|<kdb><s-leftmouse></kdb>| drag and draw with current brush (register)|
|<kdb>\ra</kdb>| ... <kdb>\rz</kdb> replace text with given brush/register|
|<kdb>\pa</kdb>| ... like <kdb>\ra</kdb> ... <kdb>\rz</kdb>, except that blanks are considered|
to be transparent

Thank you for ranking DrawIt!
