# nicholas-ci
Primitative continuous integration

## install

```
{
  test -d "~/bin/sh2" || {
    git clone https://github.com/temptemp3/sh2.git -b working ~/bin/sh2
  }
  test -d "~/bin/nicholas-ci" || {
    git clone https://github.com/temptemp3/nicholas-ci.git -b sakura ~/bin/nicholas-ci
  }  
  touch ~/.bashrc
  test "$( grep -e SH2 ~/.bashrc )" || {
    cat >> ~/.bashrc << EOF
SH2=~/bin/sh2
declare -x SH2
EOF
  }
  test "$( grep -e nicholas ~/.bashrc )" || {
    cat >> ~/.bashrc << EOF
alias nicholas="$( which bash ) ~/bin/nicholas-ci/nicholas.sh"
alias nicholas-debug="$( which bash ) -v -x ~/bin/nicholas-ci/nicholas.sh"
EOF
  }
}
```
