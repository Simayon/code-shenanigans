# Fuzzy Find Through Git Logs using FZF with preview

``` bash
git config --global alias.flog '!git log | fzf --ansi --no-sort \
--preview "echo {} | grep -o \"[a-f0-9]\\{7\\}\" | head -1 | xargs -I % git show % --color=always" \
--preview-window=right:50%:wrap --height 100% \
--bind "enter:execute(echo {} | grep -o \"[a-f0-9]\\{7\\}\" | head -1 | xargs -I % sh -c \"git show % | nvim -c \\\"setlocal buftype=nofile bufhidden=wipe noswapfile nowrap\\\" -c \\\"nnoremap <buffer> q :q!<CR>\\\"\")" \
--bind "ctrl-e:execute(echo {} | grep -o \"[a-f0-9]\\{7\\}\" | head -1 | xargs -I % sh -c \"gh browse %\")"'

```
