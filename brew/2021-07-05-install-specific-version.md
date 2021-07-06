# Install specific Version

`brew install python3` is equivalent to `brew install https://github.com/Homebrew/homebrew-core/blob/master/Formula/python.rb`. 
So, if I want to install a specific version of python3, then all I need to do is change rb file as follows

```shell

for 3.4.3_2
brew install https://raw.githubusercontent.com/Homebrew/homebrew-core/bd43f59bd50bb49242259f327cb6ac7a8dd59478/Formula/python3.rb

# for 3.5.2_3
brew install https://raw.githubusercontent.com/Homebrew/homebrew-core/ec545d45d4512ace3570782283df4ecda6bb0044/Formula/python3.rb

# F=for 3.6.5_1
brew install https://raw.githubusercontent.com/Homebrew/homebrew-core/f2a764ef944b1080be64bd88dca9a1d80130c558/Formula/python.rb
```

History of this file can be found at https://github.com/Homebrew/homebrew-core/commits/master/Formula/python.rb
