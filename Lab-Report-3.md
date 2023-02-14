# Week 3 Lab Report


## Choosing A Command
I chose the `grep` command, which searches for a given string in a text file. 


## First Variation: -i
 The `-i` variation causes grep to ignore upper and lower case. This means that "Hello" and "hEllO" look the same to `grep `.
 In our first instance, lets try `grep -r -i " Very" */*/*/Abernathy/ch1.txt>grep-results.txt`. What this line essentially does is look for any variation of "very" in ch.1txt found in the Abernathy directoy.
 It then puts it into the grep-results.txt file for easy viewing. 
 note: I am going to truncate really long outputs to make viewing easier with ...
 
 Input: 
 ```
 grep -r -i " Very" */*/*/Abernathy>grep-results.txt
 ```
 Output:
 ```
 The transformation of U.S. clothing and textile manufacturing is very much still in progress and has by no means been successful for every...
The conventional wisdom explains the industry’s decline in this ...very ...
For our purposes, we can represent growing product diversity in the form of a ... very ...
Regardless of where Quick Response has succeeded, however, our research indicates that very ...
```
 
Now let's try again with:

Input: 
```
grep -r -i " neither" */*/*/Fletcher>grep-results.txt
```
Output:
```
written_2/non-fiction/OUP/Fletcher/ch1.txt:§5. Neither slavery nor involuntary servitude, except as a punishment for crime whereof the party shall...
written_2/non-fiction/OUP/Fletcher/ch10.txt:But there is another model of thinking that recognizes ...sure that neither ...
written_2/non-fiction/OUP/Fletcher/ch2.txt:The Gettysburg Address, as written, apparently did not contain the reference to “this nation, under God.” As he spoke, Lincoln ... neither ...
written_2/non-fiction/OUP/Fletcher/ch5.txt:Modern philosophical approaches toward equality all suffer from the same flaw. They are strongly ... neither questioned nor justified.
written_2/non-fiction/OUP/Fletcher/ch5.txt:Gettysburg forged a link between the nation and egalitarian thinking that we sometimes forget. ... acquire neither until well into the twentieth century.
written_2/non-fiction/OUP/Fletcher/ch6.txt:Remarkably, the eight justices who signed the Court’s opinion invalidating the Civil Rights Act of 1875 used the vocabulary neither ...
```
The first shows how the -i causes grep to ignore capitlization, as it only found "very" variations of our inputted "Very". The second shows that it also finds other variations, such as the inputter "Neither" and the all lowercase "neither."
This is extremely useful as sometimes you need to find a word, phrase, or couple of words in a document and don't know the exact capilization or it comes in many capitilizations.
One thing to note is that example 2 gave the file path as I specified a directory in example 2 but a txt file in example 1.

## Variation 2: -c
The -c variant only outputs count of the word found.

 Input: `grep -r -c " Very" */*/*/Castro>grep-results.txt`
 Output:
 ```
 written_2/non-fiction/OUP/Castro/chA.txt:0
written_2/non-fiction/OUP/Castro/chB.txt:0
written_2/non-fiction/OUP/Castro/chC.txt:0
written_2/non-fiction/OUP/Castro/chL.txt:0
written_2/non-fiction/OUP/Castro/chM.txt:0
written_2/non-fiction/OUP/Castro/chN.txt:0
written_2/non-fiction/OUP/Castro/chO.txt:0
written_2/non-fiction/OUP/Castro/chP.txt:0
written_2/non-fiction/OUP/Castro/chQ.txt:0
written_2/non-fiction/OUP/Castro/chR.txt:0
written_2/non-fiction/OUP/Castro/chV.txt:0
written_2/non-fiction/OUP/Castro/chW.txt:0
written_2/non-fiction/OUP/Castro/chY.txt:0
written_2/non-fiction/OUP/Castro/chZ.txt:0
```
Now lets try again with 

 Input: 
 ```
 grep -r -c " Very" */*/*/HandRHawaii.txt>grep-results.txt
 ```
 Output:
 ```
 1
 ```
In the first example, I gave a directory and it checked each file in the Castro directory for the string "Very", and told me each file contained none. 
In the second example, I gave it a single file and it said that "Very" occured once. Something to note is that -i is not present so grep is case sensitive.
This can be useful if you want to know how many times a word or phrase appears in a text.

## Variation 3: -V
The -v variant inverts the match, or returns everything that doesn't have the item to be searched for.

Input: 
```
grep -r -v " the" */*/*/Abernathy/ch1.txt>grep-results.txt
```
 Output:
 ```



Five Decades of Change
A Dying Industry—or Not?
The Channel Perspective: Five Propositions
Proposition 1:  The retail, apparel, and textile sectors are increasingly linked as a channel through information and distribution relationships.
Proposition 3:  The assembly room—the traditional focus of attention for industry competitiveness—can provide competitive benefits only if other more ...
Similar dynamics are cropping up in nonclothing areas as well. Grocery stores now stock a profusion of toothbrushes, Home Depot has shelves and shelves...
How This Book Is Organized




```

Now let's try again with

Input: 
```
grep  -v "the" written_2/travel_guides/berlitz2/Amsterdam-History.txt>grep-results.txt
```
 Output:
 ```



a brief History
From Fishing to Trading
Religious Strife
Towards Independence
Decline and Fall
The 20th Century
The Modern State




```
One minor issue that can be seen is that it also outputs lines that are completely empty, which does indeed mean that that line does not contain the inputted string.
This command can be usefull so that you can search for what you don't know what you want but do know what you don't want.


## Variation 4: -l
The -l variant returns the name of files with the given input

 Input: 
 ```
 grep -r  -l "United States" */travel_guides >grep-results.txt
 ```
 Output:
 ```
 written_2/travel_guides/berlitz1/HistoryGreek.txt
written_2/travel_guides/berlitz1/IntroJamaica.txt
written_2/travel_guides/berlitz1/IntroJerusalem.txt
written_2/travel_guides/berlitz1/IntroLasVegas.txt
written_2/travel_guides/berlitz1/WhatToFWI.txt
written_2/travel_guides/berlitz1/WhatToGreek.txt
written_2/travel_guides/berlitz1/WhereToDublin.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/WhereToGreek.txt
written_2/travel_guides/berlitz1/WhereToHongKong.txt
written_2/travel_guides/berlitz1/WhereToLosAngeles.txt
written_2/travel_guides/berlitz2/Athens-History.txt
written_2/travel_guides/berlitz2/Bahamas-History.txt
written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
written_2/travel_guides/berlitz2/Boston-WhereToGo.txt
written_2/travel_guides/berlitz2/California-History.txt
written_2/travel_guides/berlitz2/California-WhatToDo.txt
written_2/travel_guides/berlitz2/California-WhereToGo.txt
written_2/travel_guides/berlitz2/Canada-History.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
written_2/travel_guides/berlitz2/China-History.txt
written_2/travel_guides/berlitz2/Cuba-History.txt
written_2/travel_guides/berlitz2/Cuba-WhereToGo.txt
written_2/travel_guides/berlitz2/NewOrleans-History.txt
written_2/travel_guides/berlitz2/Paris-WhatToDo.txt
written_2/travel_guides/berlitz2/Poland-History.txt
written_2/travel_guides/berlitz2/PuertoRico-History.txt
```

Now let's try again with:

 Input: 
 ```
 grep -r  -l "z" */non-fiction/OUP/Fletcher >grep-results.txt
 ```
 Output:
 ```
 written_2/non-fiction/OUP/Fletcher/ch1.txt
written_2/non-fiction/OUP/Fletcher/ch10.txt
written_2/non-fiction/OUP/Fletcher/ch2.txt
written_2/non-fiction/OUP/Fletcher/ch5.txt
written_2/non-fiction/OUP/Fletcher/ch6.txt
written_2/non-fiction/OUP/Fletcher/ch9.txt
```

As you can see, the only thing that is outputted is a file name. This works best on directories, as if you use it on individual files, it will output at most 1 line. 
That can still be useful if you only want to check if one file contains a string, but its generally more useful to test it on entire directories. This variation can be 
useful if you just want to know if a file even contains the desired string, and nothing else matters.












