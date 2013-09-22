# motions

## line

*   `^`: Go to the beginning of the line
*   `$`: Go to the end of the line
*   `f<char>`: Go to the next *<char>* match
*   `F<char>`: Go to the previous *<char>* match

Meta:

*   `;`: Go to next *<char>* match
*   `,`: Go to previous *<char>* match

## word

*   `w`: Go to the beginning of next word
*   `b`: Go to the beginning of previous word
*   `W`: Go to the beginning of next WORD
*   `B`: Go to the beginning of previous WORD

## buffer

*   `<number>gg`: Go to line *<number>*
*   `{`: Go to the top of current paragraph 
*   `}`: Go to the bottom of current paragraph 
*   `shift+h`: Go to the top (higher part) of the screen
*   `shift+m`: Go to the middle of the screen
*   `shift+l`: Go to the bottom (lower part) of the screen

Meta: 

*   `ctrl+o`: Go to the previous buffer motion (jump out)
*   `ctrl+i`: Go to the next buffer motion (jump in)

# scroll

*   `zt`: Move current line to the top of the screen
*   `zz`: Move current line to the middle of the screen
*   `zb`: Move current line to the bottom of the screen

# Learning motions

    noremap <Up> <NOP>
    noremap <Down> <NOP>
    noremap <Left> <NOP>
    noremap <Right> <NOP>
