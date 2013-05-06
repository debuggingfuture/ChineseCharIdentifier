ChineseCharIdentifier
Chinese characters identifier (Java)
=====================

###Quick:
This JAVA program check if input word/Char is Chinese.
visit [ChineseCharIdentifier in github](https://github.com/vincentlaucy/ChineseCharIdentifier/)

###Usage
use `public static boolean isChineseChar(int codePoint)`  to check against code point of a character
and `public boolean isChineseWord(String s)` to check against a word. 

It is also possible to exclude filtering of particular regex patterns (e.g. accept some Alphanumeric words, like \_NOUN\_ in google data set)


##Intro:
To work on a Chinese N-Gram Analysis with the [google books Dataset](http://storage.googleapis.com/books/ngrams/books/datasetsv2.html), 
I spent sometime figure out how to identify a character is Chinese or not, which is supposed to be  quite easy.

Stuff here is not very serious or standard, just hoped to help others to understand some basics and get quick solution.



#Some Concepts:
To check whether a character is Chinese, we can use its code point, which can be obtained using Java's `Character.codePointAt()`

###Code Point
From Wikipedia
>a *code point* or *code position* is any of the numerical values that make up the code space.[1] For example, ASCII comprises 128 code points in the range 0hex to 7Fhex, Extended ASCII comprises 256 code points in the range 0hex to FFhex, and Unicode comprises 1,114,112 code points in the range 0hex to 10FFFFhex.

###What are the range of Code Point for Chinese?


This question is harder.

For English it is easy, it is from a to z, A to Z.

As accordingly to the Unicode Scheme many characters are actually not only Chinese, but common in Japanese/(traditional) Korean as well. Thus Chinese characters are contained in the set called *CJK*, where this is a disjoint set, i.e. the range is not continous

###CJK
so From the [official FAQ](http://www.unicode.org/faq/han_cjk.html):
>A: It is a commonly used acronym for "Chinese, Japanese, and Korean". The term "CJK character" generally refers to "Chinese characters", or more specifically, the Chinese (= Han) ideographs used in the writing systems of the Chinese and Japanese languages, occasionally for Korean, and historically in Vietnam

###Chinese Only!
Closer to what you want may be  "Blocks Containing Han Ideographs". This is hard to reach if you have been looking for "Chinese"

check out this [SO Thread](http://stackoverflow.com/questions/9166130/what-are-the-upper-and-lower-bound-for-chinese-char-in-utf-8) and the standard specification to get the correct range.

[Full Unicode Chart](http://unicode.org/charts/)

This is blogged in [here]()