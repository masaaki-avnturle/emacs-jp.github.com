---
layout: page
title: "ac-ispell.el"
description: "ispellの auto-complete source"
package: true
category: "auto-complete"
tags: ["auto-complete"]
redirect_to: /packages/ac-ispell
---
{% include JB/setup %}

## 概要

[ac-ispell.el](https://github.com/syohex/emacs-ac-ispell)は ispellの `auto-complete` sourceです.
各種単語辞書の中から補完を行うことができます. キャメルケースやすべて大文字の単語の補完も行うことが
できます.


## スクリーンショット

![screenshot1](/images/ac-ispell.png)

## 必要要件

- Emacs 23 or higher
- auto-complete


## インストール方法

`MELPA`からインストールすることができます.

```
M-x package-install ac-ispell
```

## 設定

#### `ac-ispell-requires`(Default `3`)

補完を開始する最小文字数.


#### `ac-ispell-setup`

`auto-complete` sourceのセットアップを行う. `ac-ispell-setup`を呼び出す前に
設定をする必要がある.


#### `ac-ispell-ac-setup`

ispellの auto-complete sourceを `ac-sources`に追加する.
また `auto-complete-mode`を有効にする.


## 設定例

```lisp
;; 4文字以上の場合, 補完するようにする
(custom-set-variables
  '(ac-ispell-requires 4))

(eval-after-load "auto-complete"
  '(progn
      (ac-ispell-setup)))

(add-hook 'git-commit-mode-hook 'ac-ispell-ac-setup)
(add-hook 'mail-mode-hook 'ac-ispell-ac-setup)
```

<!--
This file has been left for redirection.
Please do not add any content.
Redirect to /packages/ac-ispell.
This file will be deleted after 6 month (2020/03/01).

;; Local Variables:
;; buffer-read-only: t
;; End:
-->
