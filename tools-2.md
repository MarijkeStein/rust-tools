# More great tools, written in Rust :)

## 11. Avoid committing secrets in the first place

Use `ripsecrets` instead of `gitleaks`.

Tip: Register it as a Git pre-commit hook to avoid committing passwords or tokens. 

```bash
$ ripsecrets


```
![image](ripsecrets.png)


## 13. Organize tabs and panes -- with commands pre-configured 

Use `zellij` if you often use the same tools in a particular layout configuration.

Example:
* A two-pane widget
* On the left, an activated Python environment (using `uv`) that automatically launches IPython
* On the right, a normal console.
* Keybindings etc. shown at the bottom.
* No tabs.

Download: [ipython-layout.kdl](ipython-layout.kdl)
```
layout {
    pane split_direction="vertical" {
        pane command="uv" {
            args  "run" "ipython"
            focus true
        }
        pane split_direction="horizontal" {
            pane
        }
    }
    pane size=2 borderless=true {
        plugin location="zellij:status-bar"
    }
}
```

```bash
$ zellij -l ipython-layout.kdl
```

![image](zellij-ipython.png)

# ... more to come :)


# Installation

### On Ubuntu 22.04

a) As normal user: 

```bash
$ cargo install ripsecrets zellij
```

### Weblinks

* ripsecrets: https://github.com/sirwart/ripsecrets
* zellij: https://zellij.dev    
