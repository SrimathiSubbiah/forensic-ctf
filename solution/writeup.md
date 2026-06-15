writeup.md

###Title: Broken Transmission###

@Description

At first, 

Deep in an abandoned research station drifting beyond known space, a weak transmission echoed through dead communication channels. 

An Astronut sent an audio file which was broken through the communication disappered with trace the station needs you now!! 

Fix the broken data now find the signal

"Flag Format : ctfX{}"  

##solution:
 step 1: analyze tramission.zip - file transmission.zip.
 
 step 2: unzip transmission file, now transmission folder will be obtained, it has brkspaceship.jpeg, signal.bin
 
 step 3: analyse the files
  
 Note: diary.txt has a flag encoded in base64
 
       it is not a flag it is a pass
       
       "dGgzX0B1dGgwcg==" from base64 "th3_@uth03"
       
 step 4: steghide info brkspaceship.jpg
         "brkspaceship.jpg":
  format: jpeg
  capacity: 766.8 KB
Try to get information about embedded data ? (y/n) y
Enter passphrase: 
  embedded file "signal.bin":
    size: 151.9 KB
    encrypted: rijndael-128, cbc
    compressed: yes
    
  step 5: steghide extract -sf brkspaceship.jpg 
          passphrase: th3_@uth0r
          extracted file -signal.bin
          
  step 6: analyze the bin file its not a bin file its mp3
  
  step 7: convert mp3 to wav and obtain the morse code
  
          Morse code(input): -... ..- ..- -.... .. -.-. --.- -... .... .-- -.-- .- --- -..- . .--- --.. -.. .-. -.. ..-. . -.. --. .- -.. - .. ..-. ...-- -. . -..- .... ---.. . .--- --... .--. ..... .---
          
          Encoded text: BUU6iCqbhwyAoXEJZdRDFedGaDtif3neXH8EJ7P5j from base58 4E7)L$:8?o=07_C>0%9b0F?<?_H?N identified as rot47
          
          Actual flag: ctfX{Sign@l_fr0m_th3_unkn0wn}
    
  step 8: Final flag submitted as ctfX{Sign@l_fr0m_th3_unkn0wn}

Tools used: 
     Cyber chef
     steghide
     unzip
     
