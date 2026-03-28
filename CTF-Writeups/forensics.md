## DISKO 1 (easy)
#### Description
Can you find the flag in this disk image?

#### Thought Process
First time using Disk Images/doing Forensic CTFs so needed to use the hint (which was "Maybe Strings could help? If only there was a way to do that?"). Figured I could use the Strings Command on the Disk image. The output was large, so required the Grep command

#### Solution
strings disko-1.dd | grep pico. This gave me a few strings, one of which was the flag. Later found strings disko-1.dd | grep picoCTF would have been better as only the flag was returned.

## information (easy)
#### Description
Files can always be changed in a secret way. Can you find the flag?

#### Thought Process
Again had to look at the hint for a clue. It stated "Look at the details of the file". I tried ls -lah, file, stat and lsattr on the cat.jpg file but nothing significant. Looked up other ways to view details and figured it was probably something to do with the metadata. 

#### Solution
Using an EXIF tool, I looked through the metadata. On the first pass over, nothing seemed out of the ordinary, but when I went back, I saw the license section had a random string of characters associated. I figured it was encoded somehow, so tried base64 decode, and it gave me the flag.

## Riddle Registry (Easy)
#### Description
Hi, intrepid investigator! 📄🔍 You've stumbled upon a peculiar PDF filled with what seems like nothing more than garbled nonsense. But beware! Not everything is as it appears. Amidst the chaos lies a hidden treasure—an elusive flag waiting to be uncovered.

#### Thought process
I figured metadata was the way to go, despite this, I covered my bases by checking the pdf contents first. After seeing some blacked out sections, I was reminded of a trick where you can copy the text that is hidden under the blacked out sections, then paste it elsewhere to see what it says. I tried this, and while I could now see the hidden text, It presented no flag. So I went back to plan A and looked at metadata.

#### Solution
I looked at the properties of the pdf, but no information was found. I then used an online tool to see all the metadata. The Author seemed to be an encrypted string, and by the look of it, It was base64 encoded. After plugging it into cyberchef and decoding the base64 string, I was given the flag.

## Hidden in plainsight (Easy)
#### Description
You’re given a seemingly ordinary JPG image. Something is tucked away out of sight inside the file. Your task is to discover the hidden payload and extract the flag.

#### Though Process
It seemed a natural first step to view the Exif data of the jpg file. After doing this, the main thing that jumped out at me was the comment of the file, so I went from there.

#### Solution
It looked to be a base64 encoded message so I decoded the comment which lead to a new message containing "steghide" and another base64 encoded string. I looked into steghide and found a command to use "steghide extract -sf img.jpg", so I just needed the password. I decrypted the base64 again and it showed the password for the steghide file. After then running the command with the new found password, the hidden data was written to "flag.txt". I output the flag.txt file and I was given the flag.

## Flag in Flame (Easy)
#### Description
The SOC team discovered a suspiciously large log file after a recent breach. When they opened it, they found an enormous block of encoded text instead of typical logs. Could there be something hidden within?

#### Thought process
I looked at the hint for this CTF which told me to decrypt the data into an image. So I output the file, figured it was base64 and then decoded it into a jpg file (base64 -d logs.txt > logs.jpg).

#### Solution
After getting the image from the logs, I opened it to find a long line of text that looked to be hexadump. I grabbed the text from the file using an online tool and then used CyberChef to decode the hex and the flag was provided.

## Corrupted file (Easy)
#### Description
This file seems broken... or is it? Maybe a couple of bytes could make all the difference. Can you figure out how to bring it back to life?

#### Thought process
Looking at the file contents, I saw JFIF at the start of the file. It seemed relevant so I looked it up and It pointed to me that the file should be a JPG file.

#### Solution
After digging around a bit, I found that JPG has a specific file signiture / "magic code". I did a hexdump and found that the file signiture didn't align with the jpg file signiture. I used a tool to edit the code into the proper file signiture, Saved it as a jpg file and opened it. The image was the flag, so I copied the text over and completed the CTF.

## RED (Easy)
#### Description
RED, RED, RED, RED

#### Thought process
After checking all the obvious areas (metadata ect), the only clue I could find was a poem.

#### Solution
After looking at the first letter of each line in the poem, I noted it said "Check lsb", lsb being least significant bit. So, I opened cyberchef, imported the file and plugged in Extract LSB. After putting in some colour patterns, I quickly found a base64 string repeating itself. Decoding the base64 gave me the flag.

## Verify (Easy)
#### Description
People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.

#### Thought Process
I first looked at what files / directories I had to work with. I saw a checksum (sha256 hash), a script and a file containing a number of ascii files. I decided to get the sha256 hash of all the files in the "files" directory, and to then find the file that matched the checksum.

#### Solution
I could have done this easier with grep, however upon using "sha256sum files/*" I had the sha256 of all the files, so I then searched through all the results. I found the file that had the checksum match, and then ran the script with that file, which then decrypted the file and gave me the correct flag. NOTE: I did try to run the script on all the files in "files", however this did not work.

## Scan Surprise (Easy)
#### Description
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?

#### Thought Process / Solution
I was provided an image, a QR code. Before I scanned it, I thought Ide check the metadata first. After looking at the metadata (no hints), I scanned the QR code, which then provided me with the flag.