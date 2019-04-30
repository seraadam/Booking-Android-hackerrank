## Problem:
An anagram is a word that can be written as a permutation of the characters
of another word, like "dirty room" and "dormitory" (ignore spaces). However,
"the" and "thee" are not anagrams, since "the" only has a single "e" whereas
"thee" has two "e" characters (spaces can occur zero, or multiple times, however.)

Given a list of words as strings, you should return another list of strings,
each containing words that are mutual anagrams.

Each string of the output should be a single group of anagarms joined with commas.

Within an output string, the expression should be sorted lexicographically.
If a group contains only a single element, output that one-element group
as a single string. And the string should be also output in lexicographical
order.  Given e.g.:
```
pear
amleth
dormitory
tinsel
dirty room
hamlet
listen
silnet
```
... the output would be:
```
amleth,hamlet
dirty room,dormitory
listen,silnet,tinsel
pear
```

## Solution
```java

import java.util.Scanner;
import java.util.Arrays;
import java.util.ArrayList;

public class MyClass {
    public static void main(String args[]) {
       Scanner x = new Scanner(System.in);
       String word;
         String newWord ;
         ArrayList<String> words =new ArrayList<String>() ;
         ArrayList<String> original =new ArrayList<String>() ;

        while(x.hasNext()){
        word= x.next();
        original.add(word);
       word = word.replaceAll("\\s+","");
       word= word.toUpperCase();

       char[] chars = word.toCharArray();
        Arrays.sort(chars);

         newWord = new String(chars);

          words.add(newWord);
    }
    x.close();



    for (int i = 0; i < words.size(); i++) {
     for (int j = i + 1 ; j < words.size(); j++) {
          if ((words.get(i)).equals(words.get(j))) {

                   // got the duplicate element
             System.out.println(original.get(i)+" "+original.get(j));
          }
     }
 }

    //      for(int i=0;i<words.size();i++)
		  // {

			 //  System.out.print(words.get(i)+" -  ");


		  // }

		  //     System.out.println(" -  ");

    //      for(int i=0;i<words.size();i++)
		  // {

			 // System.out.print(original.get(i)+" -  ");

		  // }




    }
}
```
