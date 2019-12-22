# Best Friends
## Here's a picture of our artificially-intelligent teammate and best friend, Pinguinul-Stie-Tot (The Omniscient Pinguin). Can you find the secret hidden behind it?

## Files: [HDD.vdi](https://drive.google.com/file/d/1reqctkHMQZ3L3yW04r3ZpUKKFef-RJsP/view?usp=sharing)
## Authors: yakuhito
After downloading the file, the first thing to do in any forensics situation is to check for strings. The strings command turned up 2 strange strings, which, after some googling, were found to help mark the file as containing data hidden by steghide. 

![alt text](https://raw.githubusercontent.com/RealAwesomeness/X-MAS-CTF/master/Best%20Friends/Images/strings.png)

There is also base64 on top as a comment that is layered with other encodings, but that is just a hint that says **Maybe B.F. stands for something other than best friend :)**.
I then used [**stegcracker**](https://github.com/Paradoxis/StegCracker) to crack the password of the file which turned out to be **celeste**. The output is a file called flag.txt with the following text:
**Maybe increasing the alphabet will make the encryption better ==m65;gVJW1O3>K5^?^YBJag<1i?Yd8RF2n?Sl,' &lt;GaR1F'iB4F&ast;(c$E\V-CA7&hUA79"\AMGqo2Dd&ast;J@:O]***

After messing around in [**Cyber Chef**](https://gchq.github.io/CyberChef/#recipe=From_Base85('!-u')&input=PT1tNjU7Z1ZKVzFPMz5LNV4/XllCSmFnPDFpP1lkOFJGMm4/U2wsJzxHYVIxRidpQjRGKihjJEVcVi1DQTcmaFVBNzkiXEFNR3FvMkRkKkpAOk9d) I found that the text below was base85 encoded.

![alt text](https://raw.githubusercontent.com/RealAwesomeness/X-MAS-CTF/master/Best%20Friends/Images/decode.png)

## X-MAS{Th3y_s@y_th4t_4n_AI_1s_4_hUm4ns_b3st_fr1end_cbdadfe1206409ac}
