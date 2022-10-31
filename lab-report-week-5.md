### Less Command
```
isaiahjones@Isaiahs-MacBook-Pro docsearch % less -N  technical/911report/chapter-1.txt
1 
2         
3                 
4 "WE HAVE SOME PLANES"
5 
6 Tuesday, September 11, 2001, dawned temperate and nearly cloudless in the eastern United States. Millions of men and women readied themselves for work.
```
* This commands shows the line number of the files. This is a useful command you want to send code from specific lines or when you get an error. 
```
isaiahjones@Isaiahs-MacBook-Pro docsearch % less -E technical/911report/chapter-1.txt

        
                
"WE HAVE SOME PLANES"

    Tuesday, September 11, 2001, dawned temperate and nearly cloudless in the eastern United States. Millions of men and women readied themselves for work. Some made their way to the Twin Towers, the signature structures of the World Trade Center complex in New York City. 
```
*  This commands exits automatically once it reaches the end of the file. This command option is useful because it will save you some time when doing work. The first time I ran less, I did not know that you had to manually exit. Knowing this command option, it would have saved me some time. 
```
isaiahjones@Isaiahs-MacBook-Pro docsearch % less -pDECLARATION technical/911report/chapter-2.txt
THE FOUNDATION OF THE NEW TERRORISM
            A DECLARATION OF WAR
            In February 1998, the 40-year-old Saudi exile Usama Bin Ladin and a fugitive Egyptian
                physician, Ayman al Zawahiri, arranged from their Afghan headquarters for an Arabic
                newspaper in London to publish what they termed a fatwa issued in the name of a
                "World Islamic Front."
```
* The command -p finds the first instance of the word or phrase. When you want to see the first instance of the word or phrase or use it to see when you first began writing about a certain topic.

### Find Command
```
isaiahjones@Isaiahs-MBP docsearch % find technical -name chapter-1.txt
technical/911report/chapter-1.txt
```
* This command finds files with a specific name. For this example, I am finding the file with the name chapter-1.txt. This is a useful command option to use when you want to find a specific file within a large directory. 
```
isaiahjones@Isaiahs-MBP docsearch % find technical -empty             
isaiahjones@Isaiahs-MBP docsearch % 
```
* This command option is used to find empty files and directories. For this example, I use it on technical, however, since there is no empty files or directories, it returns nothing. This is a useful command option for storage purposes. As the user, you can find empty files and delete them since they are not being used. 
```
isaiahjones@Isaiahs-MBP docsearch % find technical -user isaiahjones
technical/plos/pmed.0010064.txt
technical/plos/pmed.0020158.txt
technical/plos/journal.pbio.0020042.txt
technical/plos/journal.pbio.0020297.txt
technical/plos/pmed.0020206.txt
technical/plos/pmed.0020212.txt
technical/plos/pmed.0020216.txt
technical/plos/journal.pbio.0030094.txt
...
```
* This command option is used to find files by a specific user. For this example, I am finding a file from the user isaiahjones. This is useful command for groupwork. It can be used to find files from certain group members. 

### Grep Command
```
isaiahjones@Isaiahs-MacBook-Pro docsearch % grep -i "PULL" technical/911report/chapter-1.txt
    The hijackers had planned to take flights scheduled to depart at 7:45 (American 11), 8:00 (United 175 and United 93), and 8:10 (American 77). Three of the flights had actually taken off within 10 to 15 minutes of their planned departure times. United 93 would ordinarily have taken off about 15 minutes after pulling away from the gate. When it left the ground at 8:42, the flight was running more than 25 minutes late.
    Five seconds later, Jarrah asked, "Is that it? Shall we finish it off?"A hijacker responded,"No. Not yet. When they all come, we finish it off." The sounds of fighting continued outside the cockpit. Again, Jarrah pitched the nose of the aircraft up and down. At 10:00:26, a passenger in the background said,"In the cockpit. If we don't we'll die!" Sixteen seconds later, a passenger yelled,"Roll it!" Jarrah stopped the violent maneuvers at about 10:01:00 and said,"Allah is the greatest! Allah is the greatest!" He then asked another hijacker in the cockpit," Is that it? I mean, shall we put it down?" to which the other replied,"Yes, put it in it, and pull it down."
```
* This command ignores the the case sensitivity when searching up words. This is useful you accidentally type an uppercase and it doesnt search for what you are looking for. 
```
isaiahjones@Isaiahs-MacBook-Pro docsearch % grep -n "Roll" technical/911report/chapter-1.txt
204:    Five seconds later, Jarrah asked, "Is that it? Shall we finish it off?"A hijacker responded,"No. Not yet. When they all come, we finish it off." The sounds of fighting continued outside the cockpit. Again, Jarrah pitched the nose of the aircraft up and down. At 10:00:26, a passenger in the background said,"In the cockpit. If we don't we'll die!" Sixteen seconds later, a passenger yelled,"Roll it!" Jarrah stopped the violent maneuvers at about 10:01:00 and said,"Allah is the greatest! Allah is the greatest!" He then asked another hijacker in the cockpit," Is that it? I mean, shall we put it down?" to which the other replied,"Yes, put it in it, and pull it down."
```
* This command returns the line number where the word or phrase was found. This is helpful when you want to find a specific paragraph or line that pertains to the word or phrase you are using. This command option saves time because you do not have to look through the entire file to find something. 
```
isaiahjones@Isaiahs-MacBook-Pro docsearch % grep -1 "DECLARATION" technical/911report/*.txt
technical/911report/chapter-2.txt-            THE FOUNDATION OF THE NEW TERRORISM
technical/911report/chapter-2.txt:            A DECLARATION OF WAR
technical/911report/chapter-2.txt-            In February 1998, the 40-year-old Saudi exile Usama Bin Ladin and a fugitive Egyptian
```
* This command finds the first instance of the word in a file then prints and displays the file name. This is useful when you are looking for a specific phrase. The user can use this command to find where it is located. 
