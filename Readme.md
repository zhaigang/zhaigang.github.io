# how to build this website
```
 Install nvm if not already installed
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

# Reload shell (or open a new terminal)
source ~/.bashrc

# Install latest Node.js LTS (v20+)
nvm install --lts

# Use the new Node version
nvm use --lts

# Check the version
node -v

# install docsify-cli
npm i docsify-cli -g # if your environment in wsl maybe need add sudo

https://docsify.js.org/#/more-pages  # use this tools to build pages
```