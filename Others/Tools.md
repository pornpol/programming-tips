# Tools

## iTerm2

- install iTerm2

* install zsh

```
brew install zsh
```

- install [oh-my-zsh](https://ohmyz.sh)

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

- change theme (powerlevel10k)

```
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

1. Then edit your ~/.zshrc .

```
ZSH_THEME="powerlevel10k/powerlevel10k"
POWERLEVEL9K_MODE="awesome-patched"
```

2. [install missing font](https://github.com/Falkor/dotfiles/blob/master/fonts/SourceCodePro%2BPowerline%2BAwesome%2BRegular.ttf)

3. set iTerm2 Font (iTerm → Preferences → Profiles → Text → Change Font)
4. set VSCode terminal font (CMD + ,)

```
"terminal.integrated.fontFamily": "'SourceCodePro+Powerline+Awesome Regular'"
```

5. config theme

```
p10k configure
```

- auto suggest

1. Clone this repository into \$ZSH_CUSTOM/plugins (by default ~/.oh-my-zsh/custom/plugins)

```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

2. Add the plugin to the list of plugins for Oh My Zsh to load (inside ~/.zshrc):

```
plugins=(zsh-autosuggestions)
```

---

## Post Man

- [สองคลิกรู้เรื่อง มาสร้าง API Documentation ด้วย Postman สำหรับคนไม่โค้ดดด](https://medium.com/the-existing/generate-documentation-by-postman-81d9828c27f2?fbclid=IwAR3rrUsQ8QPH3Z3pvkkUSOhhQSaqtBNRTck_o-n_vdhv0Y37Af3pqjYSx5Q)

- การสร้าง Document ดู ใน course Node.js [[Link]](https://www.udemy.com/course/nodejs-api-masterclass)
