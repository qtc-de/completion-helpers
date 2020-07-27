### Completion Helpers

----

Autocompletion is one of the most important features of a command shell. It accelerates
your typing and improves the overall user experience. For *bash*, autocompletion is mostly
provided by the awesome [bash-completion project](https://github.com/scop/bash-completion).
This project not only provides completion scripts for the most common commands, it also defines
useful helper functions that are generally useful for writing autocompletion scripts.

That being said, I was missing certain helper functions that I tend to use in my own completion
scripts. These additional helper functions were [already requested](https://github.com/scop/bash-completion/issues/432)
on the *bash-completion* project and will hopefully be implemented. Until this happens, the
corresponding functions are stored inside this repository.


### Installation

----

On startup, *bash* automatically sources the file ``~/.bash_completion`` from your home directory. 
This is a good place to store autocompletion related code and the helper functions from this project
should be stored in this file too. If the file does not already exist you can just copy the version
from this repository:

```console
$ git clone https://github.com/qtc-de/completion-helpers
$ cp completion-helpers/bash_completion ~/.bash_completion
```

Apart from some helper functions, the [bash_completion](./bash_completion) file from this repository
also contains the following code:

```bash
for bcfile in ~/.bash_completion.d/* ; do
  [ -f "$bcfile" ] && . $bcfile
done
```

This code snipped sources all files contained inside the folder ``~/.bash_completion.d`` and allows
you to store completion scripts for different commands in separate files. This solution is more organized
than putting all command specific completion code inside your ``~/.bash_completion`` file.
