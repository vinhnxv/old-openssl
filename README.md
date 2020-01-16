# old-openssl

Missing the OpenSSL lib? 
If you read content here https://github.com/pyenv/pyenv/wiki/common-build-problems but you can't solve your problem.
I suggest solution:

## MacOS (I'm using High Sierra)
### Python new version
brew install openssl
brew --prefix openssl
LDFLAGS="-L/usr/local/opt/openssl@1.1/lib" CPPFLAGS="-I/usr/local/opt/openssl@1.1/include" pyenv install 3.6.10


### Python old version: just use an old openssl (recommend 1.0)

#### Uninstall current openssl
brew uninstall openssl (or maybe: brew uninstall --ignore-dependencies openssl)

#### Install old openssl
brew install https://raw.githubusercontent.com/vinhnxv/old-openssl/master/openssl.rb

#### Build again with LDFLAGS and CPPFLAGS:
LDFLAGS="-L/usr/local/opt/openssl/lib" CPPFLAGS="-I/usr/local/opt/openssl/include" pyenv install 3.4.0 -v


## Ubuntu:
sudo apt-get install bzip2 libreadline6 libreadline6-dev openssl

or

sudo apt install libssl1.0-dev
