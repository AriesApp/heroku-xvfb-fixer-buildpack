# heroku-xvfb-fixer-buildpack

Add support for apt-based dependencies during both compile and runtime.

Fixes broken xvfb installation on heroku. 

Note the xvfb installation is not included. It needs to be installed by another buildpack. Some hints: 

[heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) 
[heroku-buildpack-apt](https://github.com/ddollar/heroku-buildpack-apt)

Script copied from: [https://gist.github.com/fxtentacle/960cdb96ece01add8686](https://gist.github.com/fxtentacle/960cdb96ece01add8686)
