# SHA256ALU

This project is a test project for OpenLane2 by Efabless. We keep the configuration file as simple as possible. This project runs in a different container method called nix-terminal. We used WSL and some tweaks to run it. 
We can't find the PDK_ROOT or OPENLANE_ROOT but we dont need it. We use command "openlane --pdk sky130A ~/my_designs/sha256_project/config.json" for running the project. --pdk sky130A is enough for PDK root. Also we need other files for run this project. Special thanks to @secworks for beautiful SHA-256 algorhythm. It can be found at "https://github.com/secworks/sha256/tree/master"

Also special thanks to our teacher Sezen B. for inspiration. All the team has lesser hair then beginning of this project (Feels cool and cozy :) )


Steps : 
 - Follow OpenLane2 documentation : [https://openlane2.readthedocs.io/en/latest/getting_started/newcomers/index.html](https://openlane2.readthedocs.io/en/latest/getting_started/newcomers/index.html)
     -git clone https://github.com/efabless/openlane2/ ~/openlane2
     -nix-shell --pure ~/openlane2/shell.nix

   If you want test your installation you can use : openlane --log-level ERROR --condensed --show-progress-bar --smoke-test

    //"Tip

    Double-checking: are you inside a nix-shell? Your terminal prompt should look like this:


   If not, enter the following command in your terminal:

   nix-shell --pure ~/openlane2/shell.nix" (Documentation - Running the default flow PM32 Example)\\

   Create project folder
   mkdir -p ~/my_designs/SHA256ALU
   git clone https://github.com/anildev-09/SHA256ALU
   openlane --pdk sky130A ~/my_designs/sha256_project/config.json

   That's all! You've completed all the process!


   ----NERD STUFF----

   +What the hell? You've selected PDK at command? Why?
   -Cuz' I don't know verilog or json structure and I'm too lazy to read the whole documentation. I've checked other projects, used LLM and finally read the documentation (a little bit). There's 4 variables we must use in minimum configuration. But openlane2 is too smart. It can define it automaticly. But defining PDK needs to find openlane and PDK folder location. This is docker-like container project and you must define the location of this file. But you are running inside of it. I can't find the directory. If you find, please tell me.

   
