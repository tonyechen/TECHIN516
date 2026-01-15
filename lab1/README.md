# Lab 1: Intro to Linux and ROS

![welcome_to_techin516](/assets/graphic_design_is_my_passion.png)

Most robotics technologies are developed for Linux.  
All labs for the GIX robotics studios are to be completed in the Ubuntu 22.04 distribution of Linux.  
It is highly recommended to dual-boot your machine to run Ubuntu for full compatability with robotic technologies.  
M-series Macs are not yet able to dual-boot Ubuntu.  
Linux will get easier as you use it; this lab will demonstrate the basics of the "[BASH](https://en.wikipedia.org/wiki/Bash_(Unix_shell))" terminal and ROS2.  
Thoroughly understanding the following content will make everything else in the robotics studios and beyond much easier. 


## Learning Objectives

- Functional usage of Linux and the BASH terminal: how to navigate, run programs, manipulate data, etc.
- Overview ROS2 Humble: how nodes communicate, how to add new nodes, how do inspect what is happening in a robotic system.
- Compile resources of where to look for help, links to documentation, and what terminology to use.  
- Manage ROS environments and dependencies.  


## TODO

1. Dual-boot [Ubuntu 24.04 LTS](https://ubuntu.com/download/desktop) on your computer.

2. Clone the class repo with all dependencies:
    ```bash
    git clone --recursive https://github.com/GIXLabs/TECHIN516.git
    ```
    The `--recursive` options also clones all the Turtlebot repos located in `turtlebot4_ws/src/`.  
    The scripts in this repo will not work properly without them.  
    If you already cloned the repo without this option, delete the repo and re-clone.

3. Build and enter the devcontainer.  
Refer to the [Docker guide](/docs/vscode_devcontainers.md) in the docs.  
[Install Docker](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-22-04); make sure you can run `docker` commands without `sudo`.  
Install the [Remote Development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack) extension for VS Code or Cursor.  
In a new VS Code or Cursor window, open the `turtlebot_ws` directory in this repo.  
Reopen the directory in the container.  
Build the ROS workspace inside the container.


4. Complete all [ROS 2 Humble tutorials](https://docs.ros.org/en/humble/Tutorials.html) through "Using `ros2doctor` to identify issues".  
You do not need to complete any tutorials using C++, only the python tutorials.

5. Read the remaining tutorials through the end of the intermediate section, "RViz".


## Deliverables

1. Submit your code for the tutorial "Writing a simple publisher and subscriber (Python)".

2. Submit a link to a video of your publisher and subscriber working across 2 different terminals.  
The easiest way to submit a video is to upload it to your UW Google Drive.  
Make sure the share permissions allow the reader/grader to view it.  

3. Submit a link to the bag file you recorded in the tutorial "Recording and playing back data".

4. Fill in the description and a (different) example for each of the bash commands in the following table.  
Copy and paste the table into your lab report to fill-in.  
**Hint:** for most commands and programs, you can append `--help` or `-h` to learn more about it; e.g. `ls --help`.

<<<<<<< Updated upstream
<<<<<<< Updated upstream
    | Command | Description | Text example of how to use the command |
    | - | - | - | 
    | `ls` | | | 
    | `ls -la` | | |
    | `cd` | | | 
    | `mv` | | | 
    | `rm` | | | 
    | `rm -rf` | | |
    | `cp` | | | 
    | `cp -r` | | |
    | `cat` | | | 
    | `touch` | | | 
    | `source` | | | 
    | `export` | | |
    | `grep` | | |
    | `echo` | | |
    | `sudo` | | |
    | `chmod` | | |
    | `chown` | | |
    | `*` (e.g. `rm ./*`) | | | 
    | `\|` (e.g. `cat ./file1.txt \| grep search`) | | | 
    | `.` (e.g. `python ./script.py`) | | | 
    | `..` (e.g. `cd ..`) | | | 
    | `~` (e.g. `source ~/.bashrc`)| | | 
    | `>` (e.g. `cat ./file1.txt > ./file2.txt`) | | | 
    | `>>` (e.g. `cat ./file1.txt >> ./file2.txt`) | | | 
    | `!!` (e.g. `sudo !!`)| | | 
=======
=======
>>>>>>> Stashed changes
| Command | Description | Example |
| - | - | - | 
| `ls` | Lists files and directories in the current directory | `ls /home/user/Documents` |
| `ls -la` | Lists all files (including hidden) with detailed information in long format | `ls -la ~/workspace` |
| `cd` | Changes the current directory to the specified path | `cd /opt/ros/humble` |
| `mv` | Moves or renames files and directories | `mv old_name.txt new_name.txt` |
| `rm` | Removes (deletes) files | `rm file.txt` |
| `rm -rf` | Recursively and forcefully removes directories and their contents | `rm -rf build/` |
| `cp` | Copies files from source to destination | `cp source.txt target.txt` |
| `cp -r` | Recursively copies directories and all their contents | `cp -r src dest` |
| `cat` | Displays the contents of a file | `cat ~/.bashrc` |
| `touch` | Creates an empty file or updates the timestamp of an existing file | `touch new_script.py` |
| `source` | Executes commands from a file in the current shell session | `source /opt/ros/humble/setup.bash` |
| `export` | Sets an environment variable for the current shell and child processes | `export ROS_DOMAIN_ID=42` |
| `grep` | Searches for patterns in text | `grep "error" log_file.txt` |
| `echo` | Prints text or variable values to the terminal | `echo $ROS_DISTRO` |
| `sudo` | Executes a command with administrator/root privileges | `sudo apt update` |
| `chmod` | Changes file permissions (read, write, execute) | `chmod +x test.sh` |
| `chown` | Changes the owner and/or group of a file or directory | `chown user:group file.txt` |
| `*` (e.g. `rm ./*`) | Wildcard that matches any characters; represents all files/folders | `rm ./logs/*.log` |
| `\|` (e.g. `cat ./file1.txt \| grep search`) | Pipe operator that sends output from one command as input to another | `ros2 node list \| grep turtlesim` |
| `.` (e.g. `python ./script.py`) | Represents the current directory | `colcon build --packages-select ./my_package` |
| `..` (e.g. `cd ..`) | Represents the parent directory (one level up) | `cd ../..` |
| `~` (e.g. `source ~/.bashrc`)| Represents the current user's home directory | `cd ~/ros2_ws/src` |
| `>` (e.g. `cat ./file1.txt > ./file2.txt`) | Redirects output to a file, overwriting existing content | `echo "Hello" > output.txt` |
| `>>` (e.g. `cat ./file1.txt >> ./file2.txt`) | Redirects output to a file, appending to existing content | `echo "World" >> output.txt` |
| `!!` (e.g. `sudo !!`)| Repeats the previous command | `apt update` then `sudo !!` |
<<<<<<< Updated upstream
>>>>>>> Stashed changes
=======
>>>>>>> Stashed changes


## FAQ

**Q:** I have an M-series Mac, what should I do?  
**A:** Consider purchasing a (non-ARM) Winows and/or Linux computer if you would like to pursue a career in robotics.  
Alternatively, you can use the desktops in the robotics lab area and sign in with your UW net-ID.

**Q:** Can I use a virtual machine instead of dual-booting?  
**A:** Virtual machines work for some basic features of Ubuntu and ROS2.  
They have issues utilizing GPUs for heavy computations and simulations, and have issues connecting to real robots.

**Q:** Can I use WSL2 insteaf of dual-booting?  
**A:** There are mixed reviews online about how well ROS2 works on WSL.  
You can try, but WSL unique issues will not be supported in this class. 

**Q:** Something went wrong inside the container and now I can't use ROS, what do I do?  
**A:** If your container isn't working, you can always rebuilt by opening the `turtlebot_ws` folder outside of the container and selecting:  
"Dev Container: Rebuild and Reopen in Container" from VS Code's command pallet (accessed with Control-Shift-P).  
Your ROS workspace will be saved because that folder is shared between the host machine and the container.  
**All other files will be deleted!**  
Make sure you backup anything you'll need later by moving the files to the shared workspace folder.  

**Q:** When I build the container I get an error about GPUs, what do I do?  
**A:** If your computer doesn't have a GPU, remove the line `"--gpus", "all",` from the `decontainer.json` file.

**Q:** When I build the container, it seems to load forever, the last line says "Container started", how do I make it work?  
**A:** Press the bottom left corner of VS Code and select "Close Remote Conncetion".  
Then under the "Recent" choices, select "turtlebot4_ws [Dev Container]".  

**Q:** How do I record my screen on Ubuntu?  
**A:** The built-in screenshot tool works well.  
Search for it by pressing the Windows key and searching for "screenshot".  


## Resources

[MIT Missing Semester IAP 2020](https://www.youtube.com/playlist?list=PLyzOVJj3bHQuloKGG59rS43e29ro7I57J)  
Many good lectures covering many applicable computer-science topics, including Linux.  
Highly recommend you watch [lecture 1](https://www.youtube.com/watch?v=Z56Jmr9Z34Q&t=771s) if you have never used Linux before.  

[Intro to Docker by typecraft](https://www.youtube.com/watch?v=Ud7Npgi6x8E)  
Good overview of how Docker generally works.  
Most of this is handled by VS Code or Cursor when we use devcontainers. 

[ROS2 Humble YouTube tutorials by Kevin Wood](https://www.youtube.com/playlist?list=PLSK7NtBWwmpTS_YVfjeN3ZzIxItI1P_Sr)  
Many good short tutorials, good for getting more information on topics covered in the official ROS tutorials.

[ROS2 Humble YouTube tutorials by Robotics Back-End](https://www.youtube.com/playlist?list=PLLSegLrePWgJudpPUof4-nVFHGkB62Izy)  
Longer tutorials that roughly follow the official tutorials.
 
[Linux File System/Structure Explained by DorianDotSlash](https://www.youtube.com/watch?v=HbgzrKJvDRw)  
This video goes through all linux directories explaining what each one is for.
