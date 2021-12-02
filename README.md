## Local Setup



In case you have root access on your computer, and/or ruby already installed, you can skip the next steps.

### rbenv

(open https://github.com/rbenv/rbenv#basic-github-checkout)
```
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.zshrc
~/.rbenv/bin/rbenv init
```


restart the shell

`
curl -fsSL https://github.com/rbenv/rbenv-installer/raw/main/bin/rbenv-doctor | bash
`

now everything should be ok except rbenv install

## rbenv install

```
git clone https://github.com/rbenv/ruby-build.git "$(rbenv root)"/plugins/ruby-build
```

then type
```
rbenv install 2.6.8
rbenv local 2.6.8
open ~./bash_profile
```



and add to that file
```
# rbenv
export PATH=~/.rbenv/shims:$PATH
```


finally type 
```
source ~/.bash_profile
gem env home
```
it should now show the local path.

## Jekyll

go to a folder on your computer in which you want the source code of the website to be in.

```
git cone https://github.com/AlToGeLiS/altogelis.github.io.git
cd altogelis.github.io
```

if you followed the instrucitons for `rbenv` above, then activate the local ruby , e.g.
```
rbenv local 2.6.8
```

and then 
```
gem install jekyll
gem install bundler
bundle install
bundle exec jekyll serve
```

the website should now be visible in your browser locally.
