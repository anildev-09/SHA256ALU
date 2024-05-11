# SHA256ALU

This project is a test project for OpenLane2 by Efabless. We keep the configuration file as simple as possible. This project runs in a different container method called nix-terminal. We used WSL and some tweaks to run it. We can't find the PDK_ROOT or OPENLANE_ROOT but we dont need it. We use command like "openlane --pdk sky130A ~/my_designs/sha256_project/config.json" for running the project at the start.  --pdk sky130A is enough for PDK root. Also we need other files for run this project. Special thanks to @secworks for beautiful SHA-256 algorhythm. It can be found at "https://github.com/secworks/sha256/tree/master"

Also, special thanks to our teacher Sezen B., who inspired us to do this project. The whole team has less hair since the beginning of this project (Feels great and comfortable :))
Steps :

Follow OpenLane2 documentation : https://openlane2.readthedocs.io/en/latest/getting_started/newcomers/index.html 

- sudo apt-get update
- sudo apt-get upgrade
- git clone https://github.com/efabless/openlane2/ 
- sudo apt install make
- sudo apt install python3-pip
- sudo apt install python3.10-venv
- sudo apt install make 
- sudo apt install nix-bin
- sudo make
- sudo nix-shell --pure ~/openlane2/shell.nix  (It will take a long time )
- mkdir -p ~/my_designs
- cd ~/my_designs/
- /bin/git clone https://github.com/altinvolkan/SHA256ALU.git
- cd SHA256ALU/
- openlane -p sky130A ~/my_designs/SHA256ALU/config.json
  

If you want test your installation you can use : openlane --log-level ERROR --condensed --show-progress-bar --smoke-test

You can cancel any process in Linux with "Control + C" command. Sometimes you need to try few times. 

////////////////"Tip"\\\\\\\\\\\\\\\\\\\\\\\\\\\

Double-checking: are you inside a nix-shell? Your terminal prompt should look like this:

If not, enter the following command in your terminal:

nix-shell --pure ~/openlane2/shell.nix" 
//////////////(Documentation - Running the default flow PM32 Example)\\\\\\\\\\\\\\\\\\\\


openlane -p sky130A ~/my_designs/SHA256ALU/config.json

You can look files and folders with "ls" command. When you look, you can see the "runs" folder. You can navigate to it with "cd runs" command and you use "ls" command again. Please inspect the folders well. There's everything you need (floorplans, klayout, openroad etc.). That's all! You've completed all the process!


You can exit from nano with "Ctrl+X" combination. It will ask for save to file, you can hit "Y" key. 
Repeat! 




----NERD STUFF----

+What the hell? You've selected PDK at command? Why? -Cuz' I don't know verilog or json structure and I'm too lazy to read the whole documentation. I've checked other projects, used LLM and finally read the documentation (a little bit). There's 4 variables we must use in minimum configuration. But openlane2 is too smart. It can define it automaticly. But defining PDK needs to find openlane and PDK folder location. This is docker-like container project and you must define the location of this file. But you are running inside of it. I can't find the directory. If you find, please tell me.
