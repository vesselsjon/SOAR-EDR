# SOAR EDR

## Objective

The SOAR-EDR project aimed to establish a controlled environment for simulating and detecting cyber attacks. The primary focus was to simulate an attack using the <a href="https://www.geeksforgeeks.org/retrieve-all-passwords-with-lazagne-project/">LaZagne password-cracker<a> in a controlled environment which would then send a detection alert LimaCharlie using an automated detection & response rule. LimaCharlie would then send the detection to Tines which would send a message with details to slack and an email, and prompt a user to either isolate the pc or investigate further (see reference diagram-1 down below). This hands-on experience was designed to deepen understanding of detection rules, automation, and defensive strategies.

### Skills Learned

- Advanced understanding of SOAR/EDR topics.
- Proficiency in analyzing and interpreting detections.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of LimaCharlie, Tines, and Slack.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used

- Draw.io for SOR EDR drawing.
- LimaCharlie to create a D&R rules, read detections, and analyze sensor(s).
- Slack to create an automated thread to send detailed messages to.
- Tines to create a playbook for sending messages, and prompting a user to either isolate a sensor or not.

## Steps

*Ref 1: SOAR EDR Diagram NEED TO CHANGE*

![SOAR-EDR-Drawing (1)](https://github.com/user-attachments/assets/d9d9ca3d-82d8-43ca-ad10-1dc796d7b4e6)

The infected PC gets detected by a created D&R rule. LimaCharlie sends this detection to Tines which sends a slack message, email, and user prompt containing a detailed list of information. The user is prompted to either isolate the pc or investigate further. Should a pc be isolated, the network will shut down, and a message will be sent to Slack regarding isolation status. Should a pc not be isolated, the network will remain turned on, and a message will be sent to slack mentioning the pc was not isolated.

The next step was to create a LimaCharlie organization to make a few different things. The first was creating a sensor (the pc which was to be infected), following which creating a D&R rule to catch our suspicious LaZagne.exe. Running this D&R would create a detection which can be sent to the next step for Tines.

*Ref 2: D&R rule and event test*

![image](https://github.com/user-attachments/assets/2dd03340-d77a-418d-9193-29d17657d098)

![image](https://github.com/user-attachments/assets/8bb616ba-19ca-44eb-875a-4833d7dc7f79)

![image](https://github.com/user-attachments/assets/956be440-86f0-4de1-9245-3af59a2fee2d)

With having learned how to analyze LimaCharlie and set up automations for D&R rules and a successful test, Tines was the next major aspect to this project. Tines allows for the creation of a playbook which was helpful to set up events. First, a webhook would receive detections and send a slack message, email, and user prompt. Upon getting to the user prompt, a user would be asked if they would like to isolate the pc or not. As described earlier, if a user chooses no, they will be sent a new slack message and told to investigate further. On the other hand, should a user hit yes, the PC will lose internet connectivity (the sensor would be locked) and a new slack message would be sent regarding isolation status. Below is a screenshot of the Tines playbook, a case of the user hitting no, and a case of the user hitting yes:

*Ref 3: Tines playbook*

![image](https://github.com/user-attachments/assets/717e442d-08c0-497e-b7dd-861cfb4ae301)

*Ref 4: Email and Slack message after an event occurs*

![image](https://github.com/user-attachments/assets/f7bd0847-ab63-407b-af4a-3c1555a00c1b)

![image](https://github.com/user-attachments/assets/18ab6ea4-3b5e-42a5-a7d9-d1f740d98646)

*Ref 5: If a user hits no*

![image](https://github.com/user-attachments/assets/dc86d9ba-c7dc-4bb2-b224-82be85b971d6)

![image](https://github.com/user-attachments/assets/900fdb8a-3639-4e8e-b384-350383834fb1)

*Ref 6: If a user hits yes*

![image](https://github.com/user-attachments/assets/6842804d-a892-422c-8602-46bd931d0ba0)

![image](https://github.com/user-attachments/assets/c5c7a8ef-a013-411d-97c4-6a8de59a2f5e)

Hitting rejoin network will unisolate the pc.

![image](https://github.com/user-attachments/assets/9740aef8-2029-44be-8cea-c2a4cb8a415f)












