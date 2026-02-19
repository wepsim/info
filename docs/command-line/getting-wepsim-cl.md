
# Getting WepSIM

From Linux/Unix command line, please:
* Check you have installed Node v18.20+, and Bash 5.2+:
  ```bash
  sudo apt-get install nodejs npm bash -y
  ```
* Get WepSIM by executing:
  ```bash
  wget https://github.com/wepsim/wepsim/releases/download/v2.3.8/wepsim-2.3.8.zip
  unzip wepsim-2.3.8.zip
  cd wepsim-2.3.8
  npm install terser jq jshint yargs clear inquirer@8.2.6 fuzzy \
           inquirer-command-prompt inquirer-autocomplete-prompt@1
  ``` 
* Execute wepsim.sh with the help flag in order to show the available command switches:
  ```bash
  ./wepsim.sh -h
  ```

