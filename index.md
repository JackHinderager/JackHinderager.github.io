# Hello!
<div align="center">
**[GitHub](https://github.com/JackHinderager)**
**[Linkedin](https://www.linkedin.com/in/jack-hinderager-90a060252)**
**[Instagram](https://www.instagram.com/jackhinderager)**
**[Youtube](https://www.youtube.com/@jackhinderager8779)**
</div>

# Dotfiles
## .emacs
`(custom-set-variables
 '(custom-enabled-themes '(deeper-blue))
 '(package-selected-packages
   '(auto-virtualenv consult magit markdown-mode orderless pyvenv vertico)))
(custom-set-faces)

;; UI Tweaks
(tool-bar-mode -1)
(menu-bar-mode -1)
(scroll-bar-mode -1)
(setq visible-bell t)
(setq inhibit-startup-screen t)

;; Keybinds
(delete-selection-mode 1)
(global-set-key (kbd "<M-left>") 'windmove-left)
(global-set-key (kbd "<M-right>") 'windmove-right)
(global-set-key (kbd "<M-up>") 'windmove-up)
(global-set-key (kbd "<M-down>") 'windmove-down)

;; Package setup
(require 'package)
(add-to-list 'package-archives '("gnu" . "https://elpa.gnu.org/packages/") t)
(add-to-list 'package-archives '("melpa" . "https://melpa.org/packages/") t)
(add-to-list 'package-archives '("melpa-stable" . "https://stable.melpa.org/packages/") t)

(package-initialize)

;; Strap use-package
(unless (package-installed-p 'use-package)
  (package-refresh-contents)
  (package-install 'use-package))
(require 'use-package)
(setq use-package-always-ensure t)

(use-package markdown-mode
  :mode ("\\.md\\'" . markdown-mode)
  :init (setq markdown-command "pandoc --from=markdown --to=html5"))
(setq markdown-fontify-code-blocks-natively t)
(setq markdown-enable-math t)
(setq markdown-hide-urls t)

(use-package vertico
  :config
  (vertico-mode 1))

(use-package orderless
  :custom
  (completion-styles '(orderless basic))
  (completion-category-defaults nil)
  (completion-category-overrides '((file (styles orderless basic)))))

(use-package consult
  :bind ("C-x b" . consult-buffer))

(use-package pyvenv
  :ensure t
  :config (setq python-shell-interpreter "python"))`

![Volkswagen Jetta](/assets/images/tractor.jpg)
