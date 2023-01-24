# LegionDock
Legion Docker Install X11 local
Getting Legion to run on almost any system locally:
here is a step-by-step guide on how to run the program using Docker and local X11 forwarding:

Install Docker on your system.
Download the Docker image for the program by running the following command:

docker pull gvit/legion

Start the X11 server on your system. On Ubuntu, you can do this by running the following command:

sudo service lightdm start

Run the Docker container by running the following command:

sudo docker run -it --network host -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix -u 0 gvit/legion

This command will start the container and forward the X11 display to your local system.

Once the container is running, you should see the program window open on your system.

To stop the container, you can use the keyboard shortcut ctrl + c or use the docker stop command.

To create a shortcut on your desktop, you can create a shell script that starts the Docker container, and then create a desktop shortcut to that shell script.

Open a text editor and create a new file with the extension ".sh" (e.g. "run_legion.sh").

Add the following command to the file:

sudo docker run -it --network host -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix -u 0 gvit/legion

Save the file in a directory of your choice (e.g. ~/Desktop)

Open a terminal window and navigate to the directory where you saved the file.

Make the shell script executable by running the following command:

chmod +x run_legion.sh

Create a desktop shortcut by running the following command:
ln -s /path/to/run_legion.sh ~/Desktop/legion.desktop

double click the shortcut and it should execute the program.
Please note that you need to change the /path/to/run_legion.sh to the actual path of the shell script on
Properties
