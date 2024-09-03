# Doom Emacs

- bugs
    - `emacsclient [file]` doesn't work
    - `SPC p p` is broken
    - `recentf-open-files` always deletes history

- Parenthesis completion in search-replace dialog
- colon automatically inserted when defining function.  why?
  - wouldn't be as much of a problem if I didn't have to leave edit mode to move cursor around it
  
- syntax checking -> disable flycheck-mode

- none of the modes respect tab-width, they all define their own variable
  
- eldoc is really slow over tramp

- undoing/redoing is destructive

- installing from scratch takes a long time - compiling emacs packages took an hour?

# Done
- [x] No shortcut for uncommenting selected lines
  - select line, alt+;
- [x] adding packages is complicated.  not like spacevim/spacemacs where you add a single line to config
  - e.g.
  ;; in ~/.doom.d/packages.el
  (package! ttl-mode
    :recipe (:host github :repo "jeeger/ttl-mode"))

  ;; in ~/.doom.d/config.el
  (use-package! ttl-mode
    :mode "\\.n3$"
    :mode "\\.ttl$")
  - premade packages/layers are in init.el

- [x] Characters to left of line numbers when writing file
    ![](doom.png)
- [x] Annoying completion on for every mode 
  - (starting "look" process)

- [x] autoindent of selected region doesn't work
- [x] no way to get out of /ssh:tik/ in dired/ivy (seems to be fixed in emacs 29)
