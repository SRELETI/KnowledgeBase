## Installing multiple versions of java on Mac 

### Check paths of all java versions currently installed

* /usr/libexec/java_home -V

### Installing multiple versions

* Easiest way to install and manage multiple versions of java on Mac is using homebrew and jenv.
* Install `homebrew` by running `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
`
* Install `jenv` by running `brew install jenv`
* On `zsh` shell, run 
  ```
	$ echo 'export PATH="$HOME/.jenv/bin:$PATH"' >> ~/.zshrc
	$ echo 'eval "$(jenv init -)"' >> ~/.zshrc
  ```
 * Restart the terminal. Run `jenv add <java_installation_path>` to add a java installation to jenv. 
 * `brew cask search java` to search different versions of java and install using `brew cask install java<version>` 
 * Add versions to `jenv` using `jenv add <java_installation_path>`
 * Configure global version
	```
	  $ jenv global oracle64-1.6.0.39
	```
 * Configure local version (per directory)
	```
	  $ jenv local oracle64-1.6.0.39
	```
 * Configure shell instance version
	```
	  $ jenv shell oracle64-1.6.0.39
	```