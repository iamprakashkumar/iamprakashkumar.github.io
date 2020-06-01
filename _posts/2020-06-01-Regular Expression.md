![Reg Ex](https://github.com/prakashnoob/prakashnoob.github.io/blob/master/_site/Images/5291214561607680.png)  

Regular expressions is used to extract information from code, log files, spreadsheets, or even documents.  
In Regex everything is a character, we need to write a pattern to match those characters.   
Most patterns use ASCII but unicode characters can be used to match foreign text.  
There is no official strandard for regular expression  

**PCRE**  
Perl-Compatible Regular Expressions  
Because of its open source license and solid programming, PCRE has found its way into many programming languages and applications.   

d - Character  
\d - Metacharacter  

```
\d - Matches digits  
\D - Matches Non digits  
. - Matches any character  
[abcdef] - Matches characters which present inside the bracket  
[^abcde] - Inverse of the above. Matches the characters which are not present inside the bracket  
[a-z] - Matches the alphabet from a to z  
[0-9] - Matches the number from 0 to 9  
\w - Matches any alphanumeric character  
\W - Matches any Non-alphanumeric character  
a{n} - Matches the character 'a' n times  
a{m,n} - Set limit for matching  
* - Zero or more repititions  
+ - One or more repititions  
? - Optional  
\s - White space  
\S - Non white space  
^........$ - start and end  
(..) - Capture group  
(a(bc)) - Capture sub group  
(.*) - Capture all  
| - or  
```

Grouping  

Regex not just match text but also to extract information for further processing.  
() - all the characters present inside these are considered a group.  
It is used to extract information like phone numbers or emails from all sorts of data.  





