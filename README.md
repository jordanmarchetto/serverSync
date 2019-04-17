This script is used to keep files in sync between a local filesystem and a remote one using rsync.  The general flow is to set up a local workspace that will get mapped to the remote one.  Then we hook the script into vim so that on every save we push our change up to the remote workspace.


Make sure you set up your ssh key before using any of this

To use serverSync:

1. set up your config

2. add it to your $PATH

3. put this in your vimrc:

```autocmd BufWritePost * silent !serverSync <afile>```



usage: serverSync [-h] [-p] [-a] [-t] [filename]

positional arguments:

  filename    file to upload, required unless using -p

optional arguments:

  -h, --help  show this help message and exit

  -p, --pull  pull down this directory from remote workspace

  -a, --all   pull down entire remote workspace, must be used with -p

  -t, --test  only print rsync command, does not run command

example:

  serverSync filename.html  #push single file

  serverSync -p filename.html #pull single file

  serverSync -ap #pull entire remote workspace
