# Installing RobotStudio
1. Go to https://new.abb.com/products/robotics/robotstudio/downloads to get an email link to the installation files. Download and unzip the file, and run `setup.exe` in the `RobotStudio` folder
![image](https://user-images.githubusercontent.com/4022499/213512053-987b86d9-b725-41af-b4e0-c4338c3761fa.png)

2. Run the installer, selecting full installation. You will need to restart your computer.

# RPI License Setup
1. When you open RobotStudio for the first time after installation, you will see an activation dialog box. Under "Network License," choose "I want to specify a network license server or manage server licenses."
![image](https://user-images.githubusercontent.com/123105763/213563150-cc7e31fc-8891-4f6a-81d3-8a0e6d73d983.png)

2. If prompted, you can choose "No" to installing RobotWare.
![image](https://user-images.githubusercontent.com/123105763/213565512-49bb251e-5ab6-4cfa-a765-036bc0f3b68c.png)

3. Type in the license server: licsrvr33.win.rpi.edu and press "Finish"
![image](https://user-images.githubusercontent.com/123105763/213564529-55114ac5-2357-4f34-a6bc-b16ce99364f5.png)

# Install Correct RobotWare Version (Robot Controller Software)
1. Once inside RobotStudio, go to the Add-Ins tab at the top, and select on the box in the middle of the screen titled "RobotWare for IRC5." On the right side of the screen, in the drop-down menu for version of RobotWare, select 6.13. Then click "Add." 
![image](https://user-images.githubusercontent.com/123105763/213566326-4254f93c-8fa1-43a2-9fb4-1d90c60b0716.png)

2. Make sure to close and restart RobotStudio before proceeding.

# Create Project with Robot and Controller
1. Click File > New > Project. Make sure that all Names, the Robot model and RobotWare are the same as the below image. You can save the files in whatever the default directory is. Additionally, make sure that "Include a Robot and Virtual Controller" is selected to see all of the options. Click "Create".
![image](https://user-images.githubusercontent.com/123105763/213567148-8cad9fe1-238a-4868-a670-62613fb76d4f.png)

# Add EGM
1. Choose the "Controller" tab on the top of the screen, and then right click on your controller which should be listed on the left side of the screen. Choose "Change Options."
![image](https://user-images.githubusercontent.com/123105763/213568324-f554c90f-6173-4d0e-ad05-10fbb38f5c52.png)

2. In the "Change Options" menu, select "Engineering Tools" on the left side of the screen under Categories. In the middle of the screen, under Options, check the box for "689-1 Externally Guided Motion (EGM)." Make sure that all boxes on the right side of the screen under Summary are checked. Click "Ok" at the bottom of the menu.
![image](https://user-images.githubusercontent.com/123105763/213568413-0dc9314d-20a5-4254-b665-abedf126cf0f.png)

# Add Program
1. Create a new program by going to the "Rapid" tab at the top of the screen, then selecting "Program" > "New Module." 
![image](https://user-images.githubusercontent.com/123105763/213569029-6b893fe2-ebaa-452e-8069-b8e96ed2faea.png)

2. In the menu that pops up next, you can name the module anything that you want, then click "OK."
![image](https://user-images.githubusercontent.com/123105763/213569230-99c2337d-1a24-40fa-a4e6-84111407a76c.png)

3. The module editor (screen where you can type code) will open automatically. Delete the code that is there by default, and copy and paste the code from https://github.com/aelias36/robotic-deep-rolling-gui/blob/main/rapid/EGM_less_filtering.RAPID into the editor. 
![image](https://user-images.githubusercontent.com/123105763/213569669-5f6cca12-e5a1-47c2-82ac-8a8de7dedd71.png)

4. Click into the code so that your cursor is anywhere within the code. Press ctrl + shift + s together on your keyboard to save the new code into the controller. You will know that you have saved properly if a green bar appears to the left of the code.
![image](https://user-images.githubusercontent.com/123105763/213569970-4d55d683-e6e0-4ea1-a8d8-2768c1070251.png)

5. Go to the "Controller" tab at the top of the screen, then select "Configuration Editor" > "Communication." 
![image](https://user-images.githubusercontent.com/123105763/213570498-7874732a-b74b-4241-acbc-c9ae411d376d.png)

6. Make sure the UDPUC Name is EGMSensor. If not, manually change it. And click “Restart” near the upper left and wait until it’s all set.
![image](https://user-images.githubusercontent.com/123105763/213570655-86622920-a5ba-4e6b-8dbd-e18cb146767f.png)

7. Run the program by clicking the arrow icon in the middle of the screen.
![image](https://user-images.githubusercontent.com/123105763/213570815-d593cbfe-e116-41a6-85de-18f3c8674c98.png)

8. If no error messages appear at the bottom of the screen, then you have installed RobotStudio correctly.
