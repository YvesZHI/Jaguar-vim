Jaguar-vim
==========================
# Coding Java with vim is not quite recommended.

### Introduction ###
Jaguar-vim can build a vim-plugin-based environment for java. It will install and configure YouCompleteMe and some other plugins.<br>
It allows you to search and replace words, comment and uncomment codes.<br>
It allows you to jump to definition recusively.


### Tested OS list
Ubuntu 16.04 with Maven<br>
Ubuntu 18.04 with Maven<br>
CentOS 7 with Maven


### Installation ###
Execute `./check.sh` to check if the environment is suitable for the installation.<br>
Execute `./install.sh` to do the installation.


##### Issues #####
a) YouCompleteMe may have many issues. If there are some failures about it, try to reinstall it and execute `./install_YCM.sh` manually. Here is an example:<br>
- Downloading jdt-language-server may fail while installing YCM. In this case, you need to download jdt-language-server (`jdt-language-server-0.57.0-202006172108.tar.gz` for x86_64) manually from http://download.eclipse.org/jdtls/snapshots/ and put it into `~/.vim/bundle/YouCompleteMe/third_party/ycmd/third_party/eclipse.jdt.ls/target/cache/`, then execute `./install_YCM.sh` to finish the installation.

b) Only Maven has been tested. Using Maven with the file `pom.xml` in this project is highly recommended. Using other `pom.xml` files with Maven or other Java project manager tools, such as Gradle, may cause some issues.

### General Usage ###
Execute `source ~/.bashrc` after the installation to make `vimc` work.<br>
To start a go project, execute `vimc` at the root of the project.<br>

##### Normal Mode
`:Q<CR>`: quit vim and all plugins<br>
`:W<CR>`: save all & `:Q<CR>`<br>
`<C-k>` : save<br>

`\tg`: open or close the window of taglist<br>

`<F5>`: go to shell, equivalent to `:term<CR>`<br>

`mh`: move cursor to left window<br>
`mj`: move cursor to bottom window<br>
`mk`: move cursor to top window<br>
`ml`: move cursor to right window<br>
`mw`: move cursor to window below/right of the current one<br>
`mt`: move cursor to top-left window<br>
`mb`: move cursor to bottom-right window<br>
`mp`: move cursor to previous window<br>

`+`: increase width of window towards left<br>
`-`: decrease width of window towards right<br>

`\cc`: comment one line<br>
`\cv`: comment one line with next delimiter<br>
`\cm`: comment multi lines<br>
`\c$`: comment to end of line<br>
`\cu`: uncomment<br>

`<C-p>`: search file in project<br>

`:Grep [keyword]<CR>`: search the keyword in project<br>
`\vv`: search the word under cursor in project<br>
`:Replace [keyword]<CR>`: replace the word under cursor with `keyword` in project<br>
`:Replace [target] [keyword]<CR>`: replace the word `target` with `keyword` in project<br>
`:UndoReplace<CR>`: undo `:Replace`<br>
`cgt`: save changes and close all tabs except the first, then close the bottom-right window<br>
`:ccl<CR>`: close `Grep` window<br>

`\'`: wrap selected part by "'", if no part is selected, the word under cursor will be wrapped<br>
`\\'`: remove the closest "'" wrapped the part in which the cursor is<br>
similar shortcuts: `\"` and `\\"`, `\(` and `\\(`, `\[` and `\\[`, `\{` and `\\{`, `\<` and `\\<`<br>

`<F12>`: goto definition<br>
`<C-o>`: go backword<br>
`<C-i>`: go forward<br>

##### Insert Mode
`<C-j>`: move cursor backwards out of parenthesis<br>
`<C-k>`: goto normal mode and save<br>
`<C-e>`: move the current character to the end of next word<br>
`<C-l>`: move the cursor to the end of line<br>
`<C-\>`: delete the word under the cursor<br>

To get more information about usage, click on the links at the References below.


### Tips ###
1) To debug your Maven project, first, you need to execute `:!java -agentlib:jdwp=transport=dt_socket,address=localhost:5005,server=y,suspend=y -jar xxx.jar &`, then to execute `:JDBAttach localhost:5005`.<br>
2) `vim -Nu ~/.vim/bundle/YouCompleteMe/vimrc_ycm_minimal xxx.java` to get minimal vim configuration for YCM to debug YCM.<br>
3) Debug commands of YCM: `:YcmDiags`, `YcmDebugInfo`, `YcmToggleLogs`.

### References ###
https://github.com/VundleVim/Vundle.vim<br>
https://github.com/Valloric/YouCompleteMe<br>
https://github.com/artur-shaik/vim-javacomplete2<br>
https://github.com/preservim/nerdtree<br>
https://github.com/ctrlpvim/ctrlp.vim<br>
https://github.com/scrooloose/nerdcommenter<br>
https://github.com/majutsushi/tagbar<br>
https://github.com/rstacruz/sparkup<br>
https://github.com/Yggdroot/indentLine<br>
https://github.com/jiangmiao/auto-pairs<br>
https://github.com/tpope/vim-repeat<br>
https://github.com/tpope/vim-fugitive<br>
https://github.com/Xuyuanp/nerdtree-git-plugin<br>
https://github.com/YvesZHI/vim-code-dark<br>
https://gitlab.com/Dica-Developer/vim-jdb<br>
https://github.com/YvesZHI/killersheep<br>
https://codeyarns.com/2015/03/18/how-to-test-color-setup-in-vim
