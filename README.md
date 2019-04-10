Make sure you set up your ssh key before using any of this

To use serverSync:
add this dir to your $PATH

put this in your vimrc:
autocmd BufWritePost * silent !serverSync <afile>

