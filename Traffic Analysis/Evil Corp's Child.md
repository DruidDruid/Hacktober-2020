### **Challenge prompt :**

"What is the MD5 hash of the Windows executable file? "

We were given a pretty big .pcap file to analyse , here is a snippet of some protocols used .

![2020-10-17_18-28](https://user-images.githubusercontent.com/73142671/96650705-fb986980-133b-11eb-862d-8f1cfc71fc41.png)
In order to find the executable , using wireshark go to file -> export objects -> http
Doing so we get this :

![objects](https://user-images.githubusercontent.com/73142671/96651178-f0920900-133c-11eb-9adc-b57dec3aeb17.png)

Great,now we have a png image to work with.However trying to view it we get this:

![failedtoopenpng](https://user-images.githubusercontent.com/73142671/96651216-03a4d900-133d-11eb-9096-71623efd5824.png)

Running

  > file pictures4.png 

reveals this :

  > picture4.png: PE32 executable (GUI) Intel 80386, for MS Windows

The picture is actually an .exe file . Lets try to change its suffix to .exe :

  >mv picture4.png picture4.exe

Lets run the md5sum to get the flag. 

  > md5sum picture4.exe 

Thus we get our flag : flag{a95d24937acb3420ee94493db298b295}
