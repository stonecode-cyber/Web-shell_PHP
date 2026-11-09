INVESTIGATION SCENERIO

You have been called to investigate potential signs of a compromise on a WordPress site. Suspicious activity has been reported, and your goal is to analyze the available logs to identify indicators of web shell usage.

The first step in the task is to reach the affect system through ssh using the command **_ssh ubuntu@10.48.138.210,_** enter the password and get access.

<img width="458" height="349" alt="Image" src="https://github.com/user-attachments/assets/f63ed7d2-2680-4c0d-8b24-09423e0d3457" />
In this task the indicator i will be lookimg out for in the webshell attack  will be :

- Repeated or suspicious requests (especially ones to .php files)
- Strange request patterns (look for different response codes)
- Unusual user-agents (e.g. curl/0.00.0)
After the remote access i make use of the command _**cat /var/log/apache2/access.log | grep "404"**_ to read the logs.

**Which IP address likely belongs to the attacker?**

i found a n IP with suspiscious repeated request  shown inthe screenshot below:

<img width="487" height="381" alt="Image" src="https://github.com/user-attachments/assets/8469e7fc-90aa-413d-9795-3976a887ef7d" />
**203.0.113.66**

**What is the first directory that the attacker successfully identifies?**

I look for the directory the attacker first identify and the  /WORDPRESS directory as shown in the screenshot below:

<img width="457" height="287" alt="Image" src="https://github.com/user-attachments/assets/008b9c46-512d-4f8d-9d51-688a4035e45a" />

**What is the name of the .php file the attacker uses to upload the web shell?**

In this task i made use of command by change the grep command to search forsuccesfull upload  as  **_cat /var/log/apache2/access.log | grep "200"_**

This reveal the  file name to be **upload_form.php** as shown below:

<img width="945" height="388" alt="Image" src="https://github.com/user-attachments/assets/ddb9c4bd-bdd7-4779-9c71-7b5942b1a2e3" />

**What is the first command run by the attacker using the newly uploaded web shell?**
As shown below, the first command the attacker used was the whoami command as shown below:

<img width="945" height="388" alt="Image" src="https://github.com/user-attachments/assets/ba4dd8bd-3a2e-41c0-9932-fc922c3bcd4e" />

**After gaining access via the web shell, the attacker uses a command to download a second file onto the server. What is the name of this file?**


<img width="945" height="388" alt="Image" src="https://github.com/user-attachments/assets/ad06e865-8d19-4b9a-b2fd-052835943347" />

As shown above the  file downloaded is **_linpeas.sh_**

**The attacker has hidden a secret within the web shell.
Use cat to investigate the web shell code and find the flag.**
 
In this task i  use the command  **_cat /var/www/html/wordpress/wp-content/uploads/shadyshell.php_** that read the content of thr shadyshell.php tp find the flag as **THM{W3b_Sh3ll_Int3rnals}** as shown in the screenshot below;

<img width="378" height="106" alt="Image" src="https://github.com/user-attachments/assets/e8fd8ec0-b36c-4790-a3b9-5b86bd56a324" />
