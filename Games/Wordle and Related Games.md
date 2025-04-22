# Wordle and related games

## Introduction

Wordle is a word game usually played online. This document will cover Wordle and its variants, including Quordle and Kotobade Asobu.

## Wordle

[Wordle](https://www.nytimes.com/games/wordle/index.html) is a game that's usually played on a computer where you try to guess a five-letter word within six tries. Feedback is provided to you via colored tiles. Yellow for correct letter in wrong position, and green for correct letter in correct position. The guesses must be actual words, as the game will reject answers that are not words. Overall, It has taken the world by storm because it's quick, simple, and more accessible than previous games, which I will list.

Games like Scrabble or the daily cryptic crossword in newspapers require a large dictionary in your head, so they're best suited for people of English ethnicity with a suitable socio-economic background who have had exposure to a wide variety of words over their lifetime. People of non-English ethnicity and/or with English as a second language would find it hard because there have been reduced opportunities throughout their lifetime to learn those obscure words. You have games like Sudoku or chess, which are purely logic games, and you have a lot of people of non-English descent playing them. Those require a lot of brainpower, logic, and time. Wordle has fulfilled a niche in that it's a combination of dictionary and logic that is quick to play and accessible. That's why it's become a popular game.

[This person's experiments](https://graphallthethings.com/posts/wordle/) have shown that longer words are easier to guess, so it could be concluded that the design of Wordle with its 5 letter words is a balance of not being too easy or hard.

Your success in Wordle is measured in fewest tries, so time is usually not an issue. I've made the folly of trying to make guesses quickly and wasting guesses that cannot be correct because they use letters that are known not to be in the answer. Wordle has sometimes used words that are uncommon, and this has prompted discussion about how obscure those words are online.

Because Wordle solutions aren't entirely random (they're curated and tested), there's a certain element of game theory involved. Lately, there's been a trend of choosing words that people know but're difficult to guess based on common starting words such as INBOX.

According to the [Wordle history on Wikipedia](https://en.wikipedia.org/wiki/Wordle), the game was originally British. But since being sold to the New York Times, the vocabulary has turned American. Also, some words have been removed due to the current socio political climate, and words have been chosen to reflect current events. I have mixed feelings about this.

I was also wondering whether a board game would be possible, since there is a feedback system with transparent tiles that someone would need to operate. It turns out there's an official [Wordle The Party Game](https://www.amazon.com/dp/B0B5B9CP17) that can be played by multiple people. One person is the host and they run the game. It includes reusable cards and whiteboard markers. It doesn't seem to include a word list though, which is disappointing.


### Wordle Quirks

Wordle has a specific dictionary. You can look this up online, but I've played games on Quordle where it has included some foreign words like "Spiel," which means "games" in German, and "Ramen," a particular type of Asian noodle, and it has thrown me off sometimes.

The handling of repeated letters in word or is intuitive, but not obvious. Let's say for example the word was stash but you made two other guesses. Here's what it might look like

SPURT	X...-
STATS	XXX.-
STASH	XXXXX

Because you already used t and the word only contains one t any further uses of t in the guess will turn Gray. So technically grey doesn't mean the letter doesn't exist in the word, but it means no more letters of that to place.



## Story of my Strategy

I started with Quordle first. My 1st game, I tried entering "ETAON," (a contraction of ETAONIRS) which has the most frequent letters in English in order, but it needs to be actual words. I think it was at this time that I started looking up the [best words to start Quordle](https://thesmartlocal.com/read/best-wordle-words/).

I like the idea of using "Trace" and "Audio." "adieu" is another popular word since it has 4 vowels. I considered it a good outcome if I could solve 1-2 words out of the four that day. I then looked up [best three words to start Wordle](https://puzzlesbay.com/best-3-starting-words-for-wordle/
). There's an overlap between "Trace" and "Audio," so that's a bit inefficient. I wanted to include "Trace" as a starting word, and I found "Trace," "Plant," and "Humid" on this website. I modified them slightly to "Trace," "Plonk," and "Humid" so that I get an "O." 

Using those three words to start seems to have improved my success rate considerably, and I was solving about 3/4 per day. So I will consider that good. There were some suboptimal plays by me where I guessed words using letters that were already marked as not existing in the word. My weakness was also assuming that letters weren't repeated in the word. This assumption is false, and there's no guarantee when a letter turns green that it won't appear in the word again.

I mused about a quordle rules where you're allowed to guess rude or lewd words. More on that later in #Lewdle Another variation could be using [bad starting words](https://github.com/adorosario/wordle-starting-words) like ayaya, exeme, oxbow, and xylyl and try to guess the words with remaining 2-3 guesses.

During late in the game, and still not many letters are highlighted, you look at the keyboard to see what letters have not been tested. It's often "fgny," so sometimes I might test out "fanny," although "foggy" might be better words. "oxbow" might also be helpful.

I tried my opening 3 words on the official NYT Wordle, and the answer for that day was "laugh." It wasn't a very lucky start, and there were a lot of grays and yellows, but I finally did manage to get the answer "laugh" in six tries. There is also a helpful word analysis bot on the NYT website that analyzes your play, and it seems that most people were luckier and got the answer in fewer tries than I did. Most of them used "ADIEU" as an opener. Maybe I was slightly unlucky, or I'm not analyzing the information that I have thoroughly enough, but maybe my strategy of using those three words to open quordle isn't ideal for Wordle.

On 17/04/25, I tried my opening 3 words on the official NYT Wordle again, and I got it on the 4th guess. The average was 4.3, so I performed better than average.
On 17/04/25, I tried my opening 3 words on the official NYT Wordle again, and I got it on the 5th guess. The average was 5.6, so I performed better than average.


My strategy of using 3 opening guesses to cover the keyboard might minimize the worst case? https://graphallthethings.com/posts/wordle/



### Best Opening Words for Wordle 


Many people use ADIEU or AUDIO as opening words, but that is actually a [handicap](https://old.reddit.com/r/wordle/comments/1k5dfvd/do_you_use_adieu_as_an_opening_guess_or_do_you/mohi0ds/), and you're "[cheating yourself out of a good starter](https://old.reddit.com/r/wordle/comments/1k5dfvd/do_you_use_adieu_as_an_opening_guess_or_do_you/moh3opp/)". The best-performing ones are partial anagrams of ETAONIRS or whatever string has the most common letters in the English alphabet. Consonants are [slightly more important](https://old.reddit.com/r/wordle/comments/1k5dfvd/do_you_use_adieu_as_an_opening_guess_or_do_you/mohk6sv/) than vowels because you can fill in the vowels yourself, but consonants provide disambiguation when you have a situation with multiple possibilities. So the best opening one-word strategy would have three consonants and two vowels. Of course, if your opening strategy has multiple words, then the first word is less important.

alex1770 wrote [a program](https://github.com/alex1770/wordle/tree/main) to evaluate the best opening word for a 1-word opening strategy, and found that SALET was the best opening word [in 2022](https://sonorouschocolate.com/notes/index.php?title=The_best_strategies_for_Wordle) . With the July 2023 update, [he found](https://sonorouschocolate.com/notes/index.php/The_best_strategies_for_Wordle,_part_3_\(July_2023\)) it's now TARSE .

They [also said](https://sonorouschocolate.com/notes/index.php/The_best_strategies_for_Wordle,_part_2) "You can relax about trying to choose the right answer on the second guess as it requires a large dose of luck to get it in two. You are usually still discovering letters on this guess, so you can choose a completely new set of five letters, or you can include some Yellow/Green-scoring letters from the first go (obviously try a new location for a Yellow-scoring letter to try to narrow down its location). It turns out that either of these two methods, a new set of letters or a compatible word, lead to approximately similar performance in terms of the average number of guesses required, provided no letter is wasted."

"the best pair is PARSE CLINT, which if best moves are played subsequently would require an average of 3.5955 guesses using the NYT (2022-03-16) word lists. This compares with the 3.4201 from SALET, which means that ignoring the first score costs you about 0.18 guesses on average."

Here are the [best opening words ranked](https://raw.githubusercontent.com/alex1770/wordle/refs/heads/main/results_easy_nyt20220830) (also includes worst opening words at the bottom).


### Best Lewd Opening Words for Wordle 

It was out of curiosity to find if you can use only lewd words to start Wordle and achieve similar performance as conventional words. AI coding would be a necessity. I can program in Python, but it would probably take a few weeks, and I wouldn't be bothered. But with AI coding, you can get something working very quickly. GPT 4o mini is pretty good.

How I made the word dictionary: I manually came up with a list of words that I considered lewd or can be used in a lewd context. I asked AI for some five-letter lewd words and manually selected some of those words to go in the dictionary. I thought it would be a good idea to expand the scope so that we get more words, so I asked AI for some romantic words. There were some Japanese words in the word list, so I thought I could also make an anime-related words list. So I went through the anime that I watched and added some words based on the anime that I'd watched. I also added some words from AI that are anime-related.

So in the first version of my script, I described my program, but it output only one combination, and each word included letters from the previous word, which is very inefficient. With additional prompting, it output multiple words with no shared letters, but they were sorted in an arbitrary order with no score.

In version 2, I significantly revised my prompts, and so it outputs words sorted by score. I also prompted AI to write a small program so I can score previous combinations and words together for estimated performance indications. Testing those words, it seemed to have a similar or better performance than my trance plonk humid. It's a good party trick, but it would turn out to be handy later.


## How to play

After about a month of playing, you will start to  get  better and quicker at forming words and build up those little rules, although sometimes it might take a few minutes to unscreable a word based on clues. For example, Y is likely to come at the end of a word, and there are certain pairs of letters that are frequently found together like TH, CH, SH, TR. Also certain rules for English words, like after two consonants there is likely to be a vowel, and after a vowel there is likely to be a consonant.

If you run into a situation where all the letters are right except for one, do not chase the word - you may run out of guesses. Instead, insert a  disambiguation word. Here's an example.

Suppose the solution is known to be "?lash" with multiple possibilities for the first letter. A good disambiguation word would be "scarf." "S" is the first letter and it covers the case where it could be "slash." Having a disambiguation word with the first letter not being "S" would not give you that information. The word "scarf" also includes "C," and it also covers "clash" and "flash." If the 1st letter is still gray, then it's obviously something else.



I found that you need a minimum amount of information before you can start making guesses that could be the solution. If you have this and that, then you will likely get it wrong. If you assign 20 points to green and 15 points to yellow, the threshold would be about 50 points, so this could mean two greens and one yellow, or four yellows in different positions.



## Quordle

[Quordle](https://www.merriam-webster.com/games/quordle/#/) is an extension of Wordle where you try to guess four words in nine tries. There are bigger ones like [Octordle](https://www.britannica.com/games/octordle/) and [Duotrigordle](https://duotrigordle.com/) where you solve 8 & 32 words simultaneously but I think 4 is a good size. A crucial difference with Quordle is that there is feedback on whether it's a valid word or not. Valid words stay black, but invalid words will turn red.

I wasn't that interested in Wordle or Quordle initially. Wordle has come up in current affairs programs showing the impressive feat of solving Wordle in 2 tries. Sometimes I look up words online, and it links to the Merriam-Webster website, which has an internal ad promoting you to play Quordle. I was curious enough to try a few times.

For the quordle default of 9 guesses (the "Classic" variant), I have a three-word opening. There are four words to guess, so that leaves two guesses that can be incorrect.

I often find Quordle Extreme easier than Quordle Classic, since although classic has easier words, but there are more possibilities, so you might run out of guesses trying to figure out which one. But with Extreme, there are usually fewer possibilities on harder words, but those might be harder to guess since they may include uncommon letters like W, X, Y, and Z.

## Canuckle

Canuckle I found via twitter. [Canuckle](https://www.canucklegame.ca/) is Canadian-themed wordle variant. Loading the JS is a bit slow thought. One improvement NYT Wordle is that you can enter subsequent guesses before the previous feedback has completed. Often, they have obscure words as the solution like navvy , pekan, latke, so you'll need to use the feedback to guide you to towards their correct solution.

## Lewdle

So I came across [Lewdle](https://www.lewdlegame.com/App) from Tim Berberich's [ALL-THE-DLES](http://www.all-the-dles.com/) site. In this game, the aim is to only input lewd words as guesses. You can turn off the lewd guess restriction, but will incur a penalty.

In the first Lewdle game that I played, I got stuck because their lewd dictionary didn't include words in my lewd dictionary, since mine also includes romantic words. In the second Lewdle game I played a few days later. Excluding excluding ADORE since it's not in the dictionary, I started with CLITS and NYMPH. The game accepted FUDGE (IDK why), which is one of my late-game discovery words. With those three guesses, it got me pretty close, and I was able to complete it in four with BULGE as the answer.

## Kotobade Asobou
## Kotobade Asobou Introduction

There's a Japanese version of Wordle called "Kotobade Asobou," which means "Let's play with words" according to GTL. The aim of the game is to guess a four-character word in 12 guesses. Because written Japanese is more complex, extra hints are provided by default. It's pretty easy with extra hints, and you should be able to guess the word within six tries if you're competent.


### Japanese and Hints

Written Japanese uses 3 scripts: Hiragana, Katakana, and Kanji. Here, Hiragana is used for the game because it's simple, and the other 2 scripts can be represented in it. There's about 80 characters, including variants. But unlike English, there are relationships between the characters, so they can be arranged into a grid or chart. Since the number of characters is higher, the game has extra hints (on by default) to guide you toward the correct characters, but can be turned off for a challenge.

The hints are similar to Wordle: grey for wrong character, yellow for right character in the wrong position, and green for right character in the right position. The extra hints are grey with horizontal arrows for wrong character but the right character is in the same row, vertical arrows for wrong character but the right character is in the same column, and a green circle for the right character but a different variant. It could be a different voicing or size. *It's recommended to have the hints on if you're not proficient in Japanese dictionary, as you'll come into a situation with a few greens and don't know the right kanas out of 50 options to make up valid words.*

Many words in Japanese are three kanas like "Midori" and "Yahari," so you will need to know a dictionary of some four-kana words to play the game. Randomly mashing the keyboard, like with English, will not work. It's good that the game automatically converts roomaji (roman letters) into hiragana (japanese scipt) when you press enter. One inconsistency that I found is that the word goes from left to right, but the character chart goes from right to left.

I was pretty inefficient with my first game of "Kotobade." I guessed the word within 11 tries but didn't make the most use of hints. If you have both horizontal and vertical arrows in the same position, then you can intersect those arrows to get the right character. Finding four-kana words was also another challenge as I didn't have this handy reverse lookup in my brain. I resorted to using names of ships from Kantai Collection. As with Wordle, there is some strategy to choosing your opening words to cover the most characters with fewest guesses.


## Accessiblity and Mobile experience

Most wordle websites should be pretty good on mobile since you only need to display 6 rows of 5 big letters across the screen. Quordle on mobile isn't that great. The letters are small. Kotobade on mobile is actually better than Quordle .

I was concerned that because the feedback colors green and yellow, colorblind people would be disadvantaged because they would see both of them as the same color. However, this has been addressed in quordle by a "colorblind mode" where orange is fully correct and blue is partially correct. Due to common connotations, I'd say that those colors should be reversed, but otherwise, they behave fine. On the official NYT Wordle game, this is called "high contrast mode".

## Games analysis

The first quordle game I completed, the words were "broth," "shout," "brute," and "cabin." With my "Trace" and "Audio" opener, it was well played that I guessed "brute." The rest were, I would say, mostly easy words, so it was possible to guess them.

On the 11th quordle, both easy and hard, I was not able to get all the words. On the 12th, I solved the easy difficulty within nine guesses. In practice mode, the words were "cloud," "snipe," "twist," and "doing." I had solved three of them except "twist." For my last guess was twigs, it was probably going to be close, but I might not get it. It turns out it was "twist," and it had two repeated letters, which I wasn't expecting.

On the 13th, for medium difficulty, I had guessed "whale" for my fourth guess. It was slightly unlucky as the answer was "shale." For the sequence game, the last word was "alike." With my previous guess of "dowel," I was trying to put in words like "flige" and "blige," but they were not accepted by the game.

On the 13th, I solved my first extreme or hard game. With the standard opener, I guessed "niche" for the last word. I was uncertain of the next step, so I pulled out my standard "foggy" word to cover the keyboard. With that, I would basically need to solve the rest in one try. This gave me some more clues to solve "dogma." I attempted to solve the next word; it could have some repeated letters, and it was indeed "needy." It was not a lucky guess; the third word was "cannny."
