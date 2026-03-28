## Super SSH (Easy)
#### Description
Using SSH to find the flag. Provided information: a user name, a domain, a port number and a password.

#### Thought Process
Simply connect to the ctf-player@titan.picoctf.net server using SSH, on the provided port. If asked for a password, input the password provided.

#### Solution
"ssh ctf-player@titan.picoctf.net -p 62914"
then entered the password when prompted. Successfully logged into the remote server. After logging in, the flag immediately displayed in the teminal.

## Binary Search (Easy)
#### Description
Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag?

#### Thought Process
Guessing game will be presented, and based on the CTF title, I will have to use Binary search. As binary search is Logarithmic Complexity, the amount of possible numbers the correct answer can be will be halfed each time until the answer is found.

#### Solution
Connect to the provided server using SSH. Guessing game is initiated, 10 guesses, number between 1 and 1000, Higher or Lower based on the guess. Using Binary search algorithm, I found the correct number after 9 guesses. Flag was then provided after the guessing game was completed.

## FANTASY CTF (Easy)
#### Description
Play this short game to get familiar with terminal applications and some of the most important rules in scope for picoCTF.

#### Thought Process / Solution.
Given a Netcat command to connect to upon starting the CTF. Connected to it and given a text based game. Each time the game prompted an option, I selected the most appropriate response given the context. At the end, The flag was presented.

## Log Hunt (Easy)
#### Description
Our server seems to be leaking pieces of a secret flag in its logs. The parts are scattered and sometimes repeated. Can you reconstruct the original flag?

#### Thought Process
I downloaded the file and tried to find a way to differentiate normal messages from the flag message, As stated in the hint, grep is a good candidate for this.

#### Solution
Outputted the whole file, seemed large, so definitely needed to use grep. All flags start with picoCTF so that was the natural first step. I found the start of the flag, but also it was cateogorised as "INFO FLAGPART:". So I did for "grep FLAGPART server.log", this returned all of the flag parts, which i them reassembled to find the final flag.

## Time Machine (Easy)
#### Description
What was I last working on? I remember writing a note to help me remember...

#### Thought Process
Given a git repo, i first checked the program that the creator of the CTF was working on. It lead to a guessing game (same one as Binary Search) so i played that again. After finding not much of note (except an error message that a file was missing) I checked the "Drop In" folder. A message stated that this is what he worked on today, and they would need to look at their commit history. Besides this message, a .git folder was present, I thought to check there next.

#### Solution
Looking at the git folder, I saw a number of files and folders, one being a "COMMIT_EDITMSG" file. I opened that and saw the flag.

## Commitment Issues (Easy)
#### Description
I accidentally wrote the flag down. Good thing I deleted it!

#### Thought Process
I was provided a git repo file. There was a text file inside that had the flag removed and "Top Secret" in its place. Naturally I knew I needed to find the information of the previous commit. After poking around, I found a file called HEAD that had two commits, the initial commit and the flag removal commit.

#### Solution
After researching how to revert back to a previous commit using the command line, I found a command i could use which was "git Checkout" along with the git commit code. This let me look at the previous commit, I use cat on the text file and the flag was there. 
Note, After looking at solutions after completing the room, I found a better way of doing it using "git log" and "git show".

## endianness (Easy)
#### Description
Know of little and big endian?

#### Thought Process
First time working with endianness. Found quite quickly that it involves converting to hexadecimal.

#### Solution
After connecting to the server using the netcat command provided, I was given a string (zapot) and asked for the little endian. I converted zapot to hexadecimal, and after confusing big and little endians for the first few attempts, I entered the little endian correctly. Following this I was prompted for the big endian, I entered it and it gave me the flag.

## Collaborative Development (Easy)
#### Description
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?

#### Thought Process
Firstly, I checked the python file provided. No flag there. Then I thought about using git logs. Nothing there, then I looked at possible branches.

#### Solution
Using the git branch command, I saw main, and three other branches. I looked at the difference between main and each of the branches, which lead me to find all three parts of the flag, which I then reconstructed.

## Blame Game (Easy)
#### Description
Someone's commits seems to be preventing the program from working. Who is it?

#### Thought Process
There was a message.py file, which had print("Hello, World!" - Missing the last bracket. Needed to find a way to see who modified the file. Thought to do git log but too many commits to find the user who made the error.

#### Solution
After some research, gitk message.py was the command i needed. It opened up a window that showed me all the changes to the file and who committed them. The name of the person who committed message.py last was the flag.

## binhexa (Easy)
#### Description
How well can you perfom basic binary operations?

#### Thought Process / Solution
After connecting to the netcat instance provided, I was presented with a sequence of binary operations I needed to perform on 2 numbers. After completing these, I needed to convert the last binary number to hexadecimal. I was given the flag after inputting it correctly.

## repetitions (Easy)
#### Description
Can you make sense of this file?

#### Thought Process
Provided with a file. Decided to check the file type. After seeing it was an ASCII file, I checked the contents and saw it was encrypted, with base64 by my best guess (featured "==" at the end which is typical base64 encoding padding).

#### Solution
After decoding the file multiple times, I finally was provided with the flag I needed.

## Big Zip (Easy)
#### Description
Unzip this archive and find the flag.

#### Thought Process
After seeing a large quantity of text files and directories inside the main file, I knew I had to grep to find the "picoCTF" flag.

#### Solution
I used grep to search the immediate text files for "picoCTF", nothing came up, so i researched how to use grep to search inside directories too. This led me to "grep -r". After using this, I found the flag.

## First Find (Easy)
#### Description
Unzip this archive and find the file named 'uber-secret.txt'

#### Thought Process
As I had just done Big Zip, Grep -r was fresh so I used that to find the flag. However as the challenge was to find the file, I thought to start again. The natural command I needed was find.

#### Solution
Using find with -type file and -name uber-secret, I found the file path. After that I used cat on the file path, and the flag was output.

## runme.py (Easy)
#### Description
Run the runme.py script to get the flag.

#### Solution
I ran the provided python script which gave me the flag. Simple.

## PW Crack 1 (Easy)
#### Description
Can you crack the password to get the flag?

#### Thought Process
After downloading the script and password.txt encrypted file, I decided to run the python script. It prompted me to enter the correct password, So i dug into the python code to see if I could find any information there.

#### Solution
Within the python code was an if statement that ran if it matched the password to the string "1e1a". So I plugged that in to the script when asked for a password and it gave me the flag.

## PW Crack 2 (Easy)
#### Description
Can you crack the password to get the flag?

#### Thought Process
As with PW Crack 1, I decided to run the script provided. After doing so, again it asked for a password, so I once again decided to start digging into the python code for some answers.

#### Solution
As before, I found an if statement, this time however, the password was encoded in hexidecimal (0x64 for example, I knew the 0x prefix denoted hexidecimal). From there I just had to convert the hexidecimal to ascii and pop in the password into the script when i ran it. The flag was then given to me.

## convertme.py (Easy)
#### Description
Run the Python script and convert the given number from decimal to binary to get the flag.

#### Thought Process
We have done 3 python scripts, why not try one more. Again download and run script. It gave me a decimal number and asked me to convert it to binary.

#### Solution
After getting the decimal number from the script, I converted it to binary. Upon inputting the binary conversion I was given the flag.

## fixme1.py (Easy)
#### Description
Fix the syntax error in this Python script to print the flag.

#### Thought Process / Solution
Downloaded and ran the code in the terminal. Saw there was an error on line 20, which is the print flag statemnent. I went into the code and saw the line had a space in front of it, making it syntactically incorrect. After fixing it and running it again, The print statement executed, giving me the flag.

## fixme2.py (Easy)
#### Description
Fix the syntax error in the Python script to print the flag.

#### Thought Process / Solution
As with the previous CTF, I ran the code in the terminal to find which line gave the error. It was an if statement line which had an equality operator error (= instead of ==). After fixing it, I ran the code and i was given the flag.

## HashingJobApp (Easy)
#### Description
If you want to hash with the best, beat this test!

#### Thought Process / Solution
After being provided a netcat server to connect to, It gave me three prompts, each asking me to convert some text into a MD5 hash. After providing the 3 hashes correctly, I was given the flag.

## Glitch Cat (Easy)
#### Description
Our flag printing service has started glitching!

#### Thought Process
I was provided a netcat server to connect to. When I did, I was given part of the flag, but the rest was encoded.

#### Solution
I quickly deduced that the final part of the flag was in hexadecimal (given that It looked like: chr(0x34), The 0x is a clear giveaway it is hexadecimal). After that, I just converted the hexadecimal numbers to text and it gave me the final part of the Flag.

## Codebook (Easy)
#### Description
Run the Python script code.py in the same directory as codebook.txt.

#### Thought Process / Solution
As instructed, I ran the python script in the same directory as codebook. It gave me the flag, no other actions needed.

## Magikarp Ground Mission (Easy)
#### Description
Do you know how to move between directories and read files in the shell?

#### Thought process
I connected to the netcat provided, and as suggested used the ls command to get started.

#### Solution
After connecting and using ls, I saw 2 text files, one that was the first of three parts to the flag, and another giving instructions to get the second part. I followed the instruction to the root directory ( cd / ) and repeated the process. found part 2 and another instruction for part 3, go to home directory ( cd ~ ). The last part of the flag was found here. Combining the three parts gave me the full flag needed.

## Python Wrangling (Easy)
#### Description
Python scripts are invoked kind of like programs in the Terminal... Can you run this Python script using this password to get the flag?

#### Thought process
After downloading the relevant files, I ran the python scrypt. It said I needed to use "-d" or "-e" and a file name. Obvious that these were for decrypt / encrypt respectively.

#### Solution
I ran the scrypt again with -d and the flag file that was provided. It asked me for a password that I then provided from the pw.txt file I was given. After this the flag was given to me.

## 2warm (Easy)
#### Description
Can you convert the number 42 (base 10) to binary (base 2)

#### Thought process / solution
I simply converted the number 42 into binary which gave me the flag contents.

## First Grep (Easy)
#### Description
Can you find the flag in this file?

#### Thought process / Solution
Obviously I needed to use grep to find the flag inside the file. After using the command, the whole file was output, suggesting the grep matched and output the whole file as it is all one line. using "wc -l file" confirmed my suspicion. Updating my grep to only include the matched regex string (grep -o 'picoCTF{a-zA-Z0-9_}'), I was provided the flag.

## Bases (Easy)
#### Description
What does this bDNhcm5fdGgzX3IwcDM1 mean? I think it has something to do with bases.

#### Thought process / Solution
Saving the provided base64 string into a text file, then decoding it using the base64 -d command gave me the contents of the flag.

## Rust fixme 1 (Easy)
#### Description
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!

#### Thought process / Solution
Looking at the rust code in an IDE showed a issues in a let statement, a return statement and a println statement. Fixing these issues and running the code provided the flag.

## Rust fixme 2 (Easy)
#### Description
The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee?

#### Thought Process / Solution
Upon inspecting the code, the functions were trying to use constants (let statements without the mutable label) in a setting where they needed to be mutable. Therefore I added mutable requirements to the variables and parameters of the functions. After running the code with these changes, the flag was provided.

## Rust fixme 3 (Easy)
#### Description
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!

#### Thought Process / Solution
Looking at the code, I could see we needed "unsafe" labels. Upon adding these, I ran the program and was given the flag.

## Tab, Tab, Attack (Easy)
#### Description
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames.

#### Thought process / Solution
I navigated through the files until i reached the end. There were 2 files here, a c file and an executable. The executable didn't have the executable permissions so I tried to chmod, however it failed to work (probably my machine). After this failed, I looked at the C file and the flag was inside there. If the chmod worked, Ide have ran the executable, which would have output the flag inside the C file.

## Wave a flag (Easy)
#### Description
Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information...

#### Thought process
Upon downloading the provided file, I checked what type of file I had downloaded. I found that It was an executable. So I knew I needed to run it.

#### Solution
After finding out it was an executable, I checked what the permissions where for the file. It lacked the executable permission so I changed the permissions to allow it to run. I then ran the executable for the first time. It told me to use the -h command when I call the executable, So I attempted that next. Once I ran the executable with the -h command, I was given the flag.

## Static ain't always noise
#### Description
Can you look at the data in this binary? The bash script might help!

#### Thought process
After downloading the two files, I changed the permissions to allow them to be executed. I tried to execute both of them in turn to see if they provided any hints.

#### Solution
The first file I tried to execute (Static) gave me a hint to try the other file. I executed the second file (ltdis.sh) and I was given a hint to run it again, but with a file as a parameter. I ran it again with Static and it created a text file. Inside this file was a lot of text / lines, So I used grep to find the flag.

## Nice netcat... (Easy)
#### Description
There is a nice program that you can talk to by using this command in a shell

#### Thought process / Solution
I knew I needed to connect to the server via netcat, and then follow some instructions. I connected and I was given a sequence of numbers, So it seemed obvious that I needed to convert this sequence into text format. I Thought hexadecimal or ASCII was the way to go, So I tried both. The flag was provided when I converted the numbers to ASCII.

## Obedient Cat (Easy)
#### Description
This file has a flag in plain sight (aka "in-the-clear").

#### Thought Process / Solution
I downloaded the file, and checked the file type. It was an ascii file, so I output the file contents. The file output the flag.

## Warmed up (Easy)
#### Description
What is 0x3D (base 16) in decimal (base 10)?

#### Thought process / Solution
I converted 3D to base 10, which was 61. This was the flag content.

## strings it (Easy)
#### Description
Can you find the flag in file without running it?

#### Thought process / Solution
I used the strings command on the file, It output a large number of Strings. I therefore Piped it with Grep to find the string that had picoCTF in it, which returned the flag.

## what's a net cat? (Easy)
#### Description
Using netcat (nc) is going to be pretty important. Can you connect to fickle-tempest.picoctf.net at port 61485 to get the flag?

#### Thought process / Solution
As the description says, I used netcat (nc) with the specified host and port numbers which provided the flag.

## Lets Warm Up (Easy)
#### Description
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

#### Thought process / Solution
I converted the hexadecimal to Ascii, which then provided me the flag contents.
