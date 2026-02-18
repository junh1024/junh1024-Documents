# Wordle and related games

## Introduction

Wordle is a word game usually played online. This document will cover Wordle and its variants, including Quordle and Kotobade Asobu.

## Wordle

[Wordle](https://www.nytimes.com/games/wordle/index.html) is a game that's usually played on a computer where you try to guess a five-letter word within six tries. Feedback is provided to you via colored tiles. Yellow for correct letter in wrong position, and green for correct letter in correct position. The guesses must be actual words, as the game will reject answers that are not words. Overall, it has taken the world by storm because it's quick, simple, and more accessible than previous games, which I will list.

Games like Scrabble or the daily cryptic crossword in newspapers require a large dictionary in your head, so they're best suited for people of English ethnicity with a suitable socio-economic background who have had exposure to a wide variety of words over their lifetime. People of non-English ethnicity and/or with English as a second language would find it hard because there have been reduced opportunities throughout their lifetime to learn those obscure words. You have games like Sudoku or chess, which are purely logic games, and you have a lot of people of non-English descent playing them. Those require a lot of brainpower, logic, and time. Wordle has fulfilled a niche in that it's a combination of dictionary and logic that is quick to play and accessible. That's why it's become a popular game.

[This person's experiments](https://graphallthethings.com/posts/wordle/) have shown that longer words are easier to guess, so it could be concluded that the design of Wordle with its 5 letter words is a balance of not being too easy or hard.

Your success in Wordle is measured in fewest tries, so time is usually not an issue. I've made the folly of trying to make guesses quickly and wasting guesses that cannot be correct because they use letters that are known not to be in the answer. Wordle has sometimes used words that are uncommon, and this has prompted discussion about how obscure those words are online.

Because Wordle solutions aren't entirely random (they're curated and tested), there's a certain element of game theory involved. Lately, there's been a trend of choosing words that people know but are difficult to guess based on common starting words such as INBOX.

According to the [Wordle history on Wikipedia](https://en.wikipedia.org/wiki/Wordle), the game was originally British. But since being sold to the New York Times, the vocabulary has turned American. Also, some words have been removed due to the current socio political climate, and words have been chosen to reflect current events. I have mixed feelings about this.

In November 2022, NYT [appointed](https://en.wikipedia.org/wiki/Wordle#Editor) Tracy Bennett as Wordle's editor. This would turn out to have a big effect, as the words for the following week starting Monday would show, with explanations from Reddit.

1. BEGIN (1st day as editor)
1. SPELL (spelling is a major component of NYT games)
1. RAINY (benefit of the doubt that rainy weather occured/predicted where she was?)
1. UNITE (2 days post-election)
1. MEDAL (Veteran's Day)


Reddit
Many people were [unhappy](https://old.reddit.com/r/wordle/comments/ysccyo/im_hating_the_new_editorial_decisions_from_wordle/) for the new editorial direction of Wordle, especially on [Thanksgiving day](https://old.reddit.com/r/wordle/comments/z2m7yq/daily_wordle_523_thursday_24_nov_2022/) when the solution was FEAST, including [Lizzie O'Leary](https://web.archive.org/web/20230228175935/https://slate.com/technology/2022/11/wordle-editor-ruining-wordle.html) from Slate.

Trackvol [said](https://old.reddit.com/r/wordle/comments/1qpco0t/wordle_to_start_reusing_words_february_2/o28liol/) "Tracy has a background in crosswords. Crossword makers love to build themes into their CW puzzles. She brought those ideas with her to Wordle. She learned pretty quickly that Wordle players do NOT like this, but not until the criticism and backlash of DRIVE & FEAST on back-to-back days the day before Thanksgiving and on Thanksgiving day.
She still sneaks them in from time-to-time."

Having themed words tied to US events & holidays defeats the original purpose of Wordle, which was to remain challenging & unpredictable. You could argue this also makes the game unfair as those that got the US-centric context for the day will have a much easier game.

After a period of time, Wordle reverted to being unthemed. Although CACTI and TULIP were solutions early Dec 2025. The solutions are still reviewed and edited, although this is mainly to ensure two difficult words don't occur back to back.

If you forgot to take a screenshot of  yesterday's game, but  have not yet played today's game, there is a way to recover your game. Simply set your system time or timezone backwards enough so that yesterday's game is shown, take your screenshot, then restore the current time.

I was also wondering whether a board game would be possible, since there is a feedback system with transparent tiles that someone would need to operate. It turns out there's an official [Wordle The Party Game](https://www.amazon.com/dp/B0B5B9CP17) that can be played by multiple people. One person is the host and they run the game. It includes reusable cards and whiteboard markers. It doesn't seem to include a word list though, which is disappointing.


### Wordle Quirks

Wordle has a specific dictionary. You can look this up online, but I've played games on Quordle where it has included some foreign words like "Spiel," which means "games" in German, and "Ramen," a particular type of Asian noodle, and it has thrown me off sometimes.

The handling of repeated letters in Wordle is intuitive, but not obvious. Let's say for example the word was stash but you made two other guesses. Here's what it might look like

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


Many people use ADIEU or AUDIO as opening words, but that is actually a [handicap](https://old.reddit.com/r/wordle/comments/1k5dfvd/do_you_use_adieu_as_an_opening_guess_or_do_you/mohi0ds/), and you're "[cheating yourself out of a good starter](https://old.reddit.com/r/wordle/comments/1k5dfvd/do_you_use_adieu_as_an_opening_guess_or_do_you/moh3opp/)". On occasion though, those 2 words are helpful if the solution contains a U. The best-performing ones are partial anagrams of ETAONIRS or whatever string has the most common letters in the English alphabet. Consonants are [slightly more important](https://old.reddit.com/r/wordle/comments/1k5dfvd/do_you_use_adieu_as_an_opening_guess_or_do_you/mohk6sv/) than vowels because you can fill in the vowels yourself, but consonants provide disambiguation when you have a situation with multiple possibilities. So the best opening one-word strategy would have three consonants and two vowels. Of course, if your opening strategy has multiple words, then the first word is less important.



alex1770 wrote [a program](https://github.com/alex1770/wordle/tree/main) to evaluate the best opening word for a 1-word opening strategy, and found that SALET was the best opening word [in 2022](https://sonorouschocolate.com/notes/index.php?title=The_best_strategies_for_Wordle) . With the July 2023 update, [he found](https://sonorouschocolate.com/notes/index.php/The_best_strategies_for_Wordle,_part_3_\(July_2023\)) it's now TARSE .

They [also said](https://sonorouschocolate.com/notes/index.php/The_best_strategies_for_Wordle,_part_2) "You can relax about trying to choose the right answer on the second guess as it requires a large dose of luck to get it in two. You are usually still discovering letters on this guess, so you can choose a completely new set of five letters, or you can include some Yellow/Green-scoring letters from the first go (obviously try a new location for a Yellow-scoring letter to try to narrow down its location). It turns out that either of these two methods, a new set of letters or a compatible word, lead to approximately similar performance in terms of the average number of guesses required, provided no letter is wasted."

"the best pair is PARSE CLINT, which if best moves are played subsequently would require an average of 3.5955 guesses using the NYT (2022-03-16) word lists. This compares with the 3.4201 from SALET, which means that ignoring the first score costs you about 0.18 guesses on average."


[This](https://old.reddit.com/r/wordle/comments/10glvtw/i_discovered_a_trick_to_help_solve_it_with_mostly/j54h2wq/) suggests if you need a 3rd word after CLINT PARSE , is DOUGH "to cover the remaining vowels and some common letters"

Here are the [best opening words ranked](https://raw.githubusercontent.com/alex1770/wordle/refs/heads/main/results_easy_nyt20220830) (also includes worst opening words at the bottom).

Wordlebot used to use CRANE SLOTH, which is also not bad. Also note the elegant animal theme.



### Best Lewd Opening Words for Wordle 

It was out of curiosity to find if you can use only lewd words to start Wordle and achieve similar performance as conventional words. AI coding would be a necessity. I can program in Python, but it would probably take a few weeks, and I wouldn't be bothered. But with AI coding, you can get something working very quickly. GPT 4o mini is pretty good.

How I made the word dictionary: I manually came up with a list of words that I considered lewd or can be used in a lewd context. I asked AI for some five-letter lewd words and manually selected some of those words to go in the dictionary. I thought it would be a good idea to expand the scope so that we get more words, so I asked AI for some romantic words. There were some Japanese words in the word list, so I thought I could also make an anime-related words list. So I went through the anime that I watched and added some words based on the anime that I'd watched. I also added some words from AI that are anime-related.

So in the first version of my script, I described my program, but it output only one combination, and each word included letters from the previous word, which is very inefficient. With additional prompting, it output multiple words with no shared letters, but they were sorted in an arbitrary order with no score.

In version 2, I significantly revised my prompts, and so it outputs words sorted by score. I also prompted AI to write a small program so I can score previous combinations and words together for estimated performance indications. Testing those words, it seemed to have a similar or better performance than my trance plonk humid. It's a good party trick, but it would turn out to be handy later.


## How to play

After about a month of playing, you will start to get better and quicker at forming words and build up those little rules, although sometimes it might take a few minutes to unscramble a word based on clues. For example, Y is likely to come at the end of a word, and there are certain pairs of letters that are frequently found together like TH, CH, SH, TR. Also certain rules for English words, like after two consonants there is likely to be a vowel, and after a vowel there is likely to be a consonant.

If you run into a situation where all the letters are right except for one, do not chase the word - you may run out of guesses. Instead, insert a disambiguation word. Here's an example.

Suppose the solution is known to be "?lash" with multiple possibilities for the first letter. A good disambiguation word would be "scarf." "S" is the first letter and it covers the case where it could be "slash." Having a disambiguation word with the first letter not being "S" would not give you that information. The word "scarf" also includes "C," and it also covers "clash" and "flash." If the 1st letter is still gray, then it's obviously something else.



I found that you need a minimum amount of information before you can start making guesses that could be the solution. If you have this and that, then you will likely get it wrong. If you assign 20 points to green and 15 points to yellow, the threshold would be about 50 points, so this could mean two greens and one yellow, or four yellows in different positions.

Also, if there's a E and R, the word could end in ER. There's a lot of words which end in ER and some famous words that had a high rate of being unsolved (PARER and EAGER at 50% and 36% respectively) ended in ER.

Also, the solution will not be a plural [made by adding a trailing "s". So "books" is off, but "geese" isn't.](https://old.reddit.com/r/wordle/comments/1oegxd2/does_this_mean_the_first_word_i_guessed_will/)

Also, names of people or places are generally not solutions, unless they have another meaning.

https://old.reddit.com/r/wordle/comments/1oeswb1/what_extremely_difficult_word_are_you_waiting_to/

hard mode words https://old.reddit.com/r/wordle/comments/1okdran/wordle_replay/nmbeobo/
3-consonant and 4-consonant words are generally much better starting words and are also generally more likely to be more forgiving in Hard Mode.
CARLE TARSE SALET REAST LEAST CRATE SLART CLAST CLART etc..

https://old.reddit.com/r/wordle/comments/1p2ah5b/1615_you_live_and_you_dont_learn/

" there was a pattern for which GLOBE could not survive. I just didn't know which pattern. And now I know it's the GRA_E pattern."

With you can play previous games, and with 


https://old.reddit.com/r/wordle/comments/12hkn3i/any_tips_on_scoring_more_3s_and_4s_rather_than_5s/ Crafting better starting words.

https://wordlearchive.com/


Wordlebot is part of NY Times which shows you a whole bevy of information, you can see your skill & luck scores (how well you eliminated words), and steps against other NYT users. You then get a step-by-step breakdown of each guess against other users, along with comments and suggested words. You also get a statistical breakdown of what words NYT users used at each step, and what words Wordlebot would've chosen. An important number is the "words left" stat as it shows if you could've solved the word faster. Another important number is "Everyone's Guesses on Turn 6" as it shows the solve rate, which in turn is another estimation of the difficulty.

If the skill & luck scores are still confusing to you, the [Wordlebot FAQ](https://www.nytimes.com/interactive/2024/02/16/upshot/wordlebot-faq.html) can explain how this works.

https://scoredle.com/

is an alternative which shows you how many possibilities are left after each guess.


Many people use ADIEU, followed by STONY/STORY. This is a mediocre strategy since the vowels are in the wrong place for a quick solve. Here are some [alternatives](https://old.reddit.com/r/wordle/comments/xr5aou/ootl_why_again_doesnt_everyone_use_adieu_for_1st/)

https://old.reddit.com/r/wordle/comments/1q2a6gg/mental_math_or_systems_how_do_you_reduce_wordle/

Wordle past answers

https://stuckonwordle.com/all-wordle-answers.html

## Harder wordle
Deliberately making poor guesses while in hard mode, using only lewd/rude guesses, or https://old.reddit.com/r/wordle/comments/1q9y58i/challenge_generate_five_random_words_and_try_to/

https://old.reddit.com/r/wordle/comments/1qulf3k/suggestions_for_a_mediocre_starting_word/


## Quordle

[Quordle](https://www.merriam-webster.com/games/quordle/#/) is an extension of Wordle where you try to guess four words in nine tries. There are bigger ones like [Octordle](https://www.britannica.com/games/octordle/) and [Duotrigordle](https://duotrigordle.com/) where you solve 8 & 32 words simultaneously but I think 4 is a good size. A crucial difference with Quordle is that there is feedback on whether it's a valid word or not. Valid words stay black, but invalid words will turn red.

I wasn't that interested in Wordle or Quordle initially. Wordle has come up in current affairs programs showing the impressive feat of solving Wordle in 2 tries. Sometimes I look up words online, and it links to the Merriam-Webster website, which has an internal ad promoting you to play Quordle. I was curious enough to try a few times.

For the quordle default of 9 guesses (the "Classic" variant), I have a three-word opening. There are four words to guess, so that leaves two guesses that can be incorrect.

I often find Quordle Extreme easier than Quordle Classic, since although classic has easier words, but there are more possibilities, so you might run out of guesses trying to figure out which one. But with Extreme, there are usually fewer possibilities on harder words, but those might be harder to guess since they may include uncommon letters like W, X, Y, and Z.

## Canuckle

Canuckle I found via twitter. [Canuckle](https://www.canucklegame.ca/) is Canadian-themed wordle variant. Loading the JS is a bit slow though. One improvement NYT Wordle is that you can enter subsequent guesses before the previous feedback has completed. Often, they have obscure words like navvy, pekan, latke, so you'll need to use the feedback to guide you to towards the correct solution. Also, most solutions of the day are themed.

## Lewdle

So I came across [Lewdle](https://www.lewdlegame.com/App) from Tim Berberich's [ALL-THE-DLES](http://www.all-the-dles.com/) site. In this game, the aim is to only input lewd words as guesses. You can turn off the lewd guess restriction, but will incur a penalty.

In the first Lewdle game that I played, I got stuck because their lewd dictionary didn't include words in my lewd dictionary, since mine also includes romantic words. In the second Lewdle game I played a few days later. Excluding ADORE since it's not in the dictionary, I started with CLITS and NYMPH. The game accepted FUDGE (IDK why), which is one of my late-game discovery words. With those three guesses, it got me pretty close, and I was able to complete it in four with BULGE as the answer.

## Kotobade Asobou
## Kotobade Asobou Introduction

There's a Japanese version of Wordle called "Kotobade Asobou," which means "Let's play with words" according to GTL. The aim of the game is to guess a four-character word in 12 guesses. Because written Japanese is more complex, extra hints are provided by default. It's pretty easy with extra hints, and you should be able to guess the word within six tries if you're competent.


### Japanese and Hints

Written Japanese uses 3 scripts: Hiragana, Katakana, and Kanji. Here, Hiragana is used for the game because it's simple, and the other 2 scripts can be represented in it. There's about 80 characters, including variants. But unlike English, there are relationships between the characters, so they can be arranged into a grid or chart. Since the number of characters is higher, the game has extra hints (on by default) to guide you toward the correct characters, but can be turned off for a challenge.

The hints are similar to Wordle: grey for wrong character, yellow for right character in the wrong position, and green for right character in the right position. The extra hints are grey with horizontal arrows for wrong character but the right character is in the same row, vertical arrows for wrong character but the right character is in the same column, and a green circle for the right character but a different variant. It could be a different voicing or size. *It's recommended to have the hints on if you're not proficient in Japanese dictionary, as you'll come into a situation with a few greens and don't know the right kanas out of 50 options to make up valid words.*

Many words in Japanese are three kanas like "Midori" and "Yahari," so you will need to know a dictionary of some four-kana words to play the game. Randomly mashing the keyboard, like with English, will not work. It's good that the game automatically converts roomaji (roman letters) into hiragana (japanese scipt) when you press enter. One inconsistency that I found is that the word goes from left to right, but the character chart goes from right to left.

I was pretty inefficient with my first game of "Kotobade." I guessed the word within 11 tries but didn't make the most use of hints. If you have both horizontal and vertical arrows in the same position, then you can intersect those arrows to get the right character. Finding four-kana words was also another challenge as I didn't have this handy reverse lookup in my brain. I resorted to using names of ships from Kantai Collection. As with Wordle, there is some strategy to choosing your opening words to cover the most characters with fewest guesses.

## Hard mode

Wordle and most Wordle derivatives have a "hard mode". The wording on Wordle says "Any revealed hints must be used in subsequent guesses". The implementation on wordle is:

- Green tiles must be used in the same position
- Yellow tiles must be used anywhere (same position allowed)
- Grey tiles can still be used

This seemingly allows you to solve the puzzle faster by preventing you from making guesses that the word is not. But it can put you into situations where you run out of guesses because restrictions are being enforced. These are known as "traps". Examples: _IGHT , _OUND, _ASTE. When you guess a word that follows a pattern, but isn't the solution, following guesses must also follow the pattern. You cannot simply insert a disambiguation word to narrow the possibilities.

Hard mode is hard not only because your guesses must follow the hint rules, but also to predict and avoid traps. given what letters light up green or yellow, You need to think a few steps ahead, deduce what trap may lie ahead, and when to enter the trap. This also implies your starting word should allow you to survive (some) traps in 6 turns.

Alex has made a list of hard mode approved words - starters in which a computer can solve all words in 6 turns with hard mode. But will not give you the path - that is for you to figure out. In this document , results_hard_nyt20230701.txt , words which have a numerical score are approved, and words which have a score of Infinity can't survive all traps. Having a score of Infinity doesn't mean the word is a bad starter, in fact, many good starters (for default mode) have a score of Infinity (like CARLE, CRATE, CRANE) because they have letters in common positions. It means more skill and luck is involved for you to solve it in time for some solutions.

https://old.reddit.com/r/wordle/comments/1pzn6sf/the_optimal_strategy_isnt_about_solving_fast_but/

## Accessiblity and Mobile experience

Most wordle websites should be pretty good on mobile since you only need to display 6 rows of 5 big letters across the screen. Quordle on mobile isn't that great. The letters are small. Kotobade on mobile is actually better than Quordle .

I was concerned that because the feedback colors green and yellow, colorblind people would be disadvantaged because they would see both of them as the same color. However, this has been addressed in quordle by a "colorblind mode" where orange is fully correct and blue is partially correct. Due to common connotations, I'd say that those colors should be reversed, but otherwise, they behave fine. On the official NYT Wordle game, this is called "high contrast mode".

## Games analysis

The first quordle game I completed, the words were "broth," "shout," "brute," and "cabin." With my "Trace" and "Audio" opener, it was well played that I guessed "brute." The rest were, I would say, mostly easy words, so it was possible to guess them.

On the 11th quordle, both easy and hard, I was not able to get all the words. On the 12th, I solved the easy difficulty within nine guesses. In practice mode, the words were "cloud," "snipe," "twist," and "doing." I had solved three of them except "twist." For my last guess was twigs, it was probably going to be close, but I might not get it. It turns out it was "twist," and it had two repeated letters, which I wasn't expecting.

On the 13th, for medium difficulty, I had guessed "whale" for my fourth guess. It was slightly unlucky as the answer was "shale." For the sequence game, the last word was "alike." With my previous guess of "dowel," I was trying to put in words like "flige" and "blige," but they were not accepted by the game.

On the 13th, I solved my first extreme or hard game. With the standard opener, I guessed "niche" for the last word. I was uncertain of the next step, so I pulled out my standard "foggy" word to cover the keyboard. With that, I would basically need to solve the rest in one try. This gave me some more clues to solve "dogma." I attempted to solve the next word; it could have some repeated letters, and it was indeed "needy." It was not a lucky guess; the third word was "canny."

https://old.reddit.com/r/wordle/comments/1ozp03c/259_does_anyone_else_play_dirty_wordle/

https://old.reddit.com/r/wordle/comments/1nm3t5i/is_this_a_good_strategy/ (5 openers)


https://old.reddit.com/r/wordle/comments/1p9pp2x/will_slate_ever_be_the_opening_word/nre1gad/ AROSE-UNITY

CRANE SLOTH
PARSE CLINT
SLATE CRONY

"The top-10 ranked letters in Wordle Solutions are EAROT LISNC. In that specific order"

EAROT LISNC

https://old.reddit.com/r/wordle/comments/1pk6ls2/two_word_start/


https://old.reddit.com/r/wordle/comments/1pmlpdz/another_starting_words_for_wordle_analysis/


https://old.reddit.com/r/wordle/comments/1prjlts/are_people_really_this_good_at_wordle/nv529zd/?context=3

## Cheating
The definition of cheating in wordle varies, but many people define it to consulting [external resources](https://old.reddit.com/r/wordle/comments/1j92kam/is_my_friend_cheating_at_wordle/mhaea3z/) (such as using solvers, past answers lists, or even the current answer) to improve your score. You can memorize past solutions of games you play yourself beforehand, but when you play, it should be you against the game. Nothing else.

Wordlebot can do 3.2. 3.4 is on the [verge of beleivability](https://old.reddit.com/r/wordle/comments/1o4lv4y/1234_is_my_friend_a_cheater_or_not/) for human and you'd need to be very good to achieve that score on the long run (or consult previous solutions). Thus, if someone has a long-term average lower than that, they're likely cheating.

Although, some people are of the view that you can do as you please, and the [the only person you'd be cheating is yourself](https://old.reddit.com/r/wordle/comments/1nhplci/1549_is_it_cheating_to_look_at_the_word_list_im/) . You're [cheating yourself out of a proper sit-down think](https://old.reddit.com/r/wordle/comments/1nvwzle/is_this_cheating/nhbynrz/) 

### Running out of words
Since the Wordle solution set is small (about 3K words) it would eventually run out of unique solutions. People have suggested that Wordle may move to 6-letter words, or add more obscure words. I thought that they would allow plurals ending in s, or allowing proper nouns (names of places or people). But in January 2026, NYT [announced in an email](https://old.reddit.com/r/wordle/comments/1qpco0t/wordle_to_start_reusing_words_february_2/) that would reuse words - the simplest of solutions. Note that Feb 02 is Groundhog Day, apt timing to implement such a move. The solution for [that day](https://old.reddit.com/r/wordle/comments/1qsvl9w/daily_wordle_1689_monday_2_feb_2026/) was CIGAR, also apt since that was wordle solution #0.



## NYT spelling bee
[Spelling bee]() can be thought of as a companion to wordle and is an older word game. Similar to Word Wheel games as found in newspapers, players must make words given limited letters, with these changes:

- every word must use the center letter (this makes the game harder)
- letters can be repeated (allows for more words)

The word list is smaller than wordle and people often complain that spelling bee doesn't have x valid word.

https://old.reddit.com/r/NYTSpellingBee/comments/1qx1ft7/what_is_the_actual_worst_pangram_ever/

[Spelling Bee Buddy](https://www.nytimes.com/interactive/2023/upshot/spelling-bee-buddy.html) includes hints for the daily game. Reddit also has [daily hints]() too.


## NYT Connections
NYT Connections is another word game from NYT. You try to sort 16 words into 4 categories. You select 4 items as a possible group and press submit. If your guess is correct, the category name and difficulty is revealed. If it's incorrect, but 1 off, the game will show "one away". If more items are incorrect, the game will show no hints. You are allowed 4 incorrect guesses before the game ends and the answers are revealed. It's harder than wordle since the solve rate [averages about 70%](https://old.reddit.com/r/NYTConnections/comments/1pq918v/did_someone_else_take_over_the_connections/nuteuhj/) but for wordle it's typically 95%. Wynia Liu is the editor of Connections.

The categories are typically arranged from easiest to hardest:

- Yelllow: Synonyms
- Green: Synonyms/associated items
- Blue: associated items
- Purple: Wordplay

The wordplay category is usually the hardest since it's often things like homonyms for X, beginning/ending with X (Compound words are usually wordplay), ___X, X + letter added/removed. Thus, you'll need to solve 3 categories before you can solve the board.

People have [mixed opinions](https://old.reddit.com/r/NYTConnections/comments/1pukp25/is_this_cheating/) on whether looking up a word is cheating, but most will agree it's often necessary as Wynia often uses obscure meanings of words. But it will absolutely not help for wordplay. 

[Practice makes perfect](https://old.reddit.com/r/NYTConnections/comments/1o6ajje/why_am_i_so_abysmal_at_this_game/njfx9ww/), or at least more solves. Don't expect to have a 95% solve rate for wordle from the get-go. Also, [Knowing too much can send you in the wrong direction](https://www.nytimes.com/2023/11/06/crosswords/connections-tips-and-tricks.html) . Things that belong in one category, but really belong in another. These are called Herrings, or if they span all 4 colors, a Rainbow Herring. Past (Rainbow) Herrings include Album Titles, Batman-related Entities, and Comic superheroes.

The most skillful way of solving a puzzle is called a reverse rainbow, which often requires pre solving. Purple, Blue, Green, then Yellow. Although often it's hard to get exactly a given order since the difficulty of each category is very subjective. Apparently Wynia [loves](https://old.reddit.com/r/NYTConnections/comments/1r66e30/solve_rate_trends/o5oqxxi/) the solfege do re mi system, and it's used in wordplay categories. I'd also say she also likes Monopoly as it's [turned up]() from time to time too.


Connections Plus has boards made by other people. These are posted on [Reddit](https://old.reddit.com/r/NYTConnections/) , but boards are typically the equivalent of 4x Wynia blue in difficulty. Connections Plus also has an [archive of previous NYT boards](https://connectionsplus.io/nyt-archive?sortBy=newest&page=1) , except for special ones like [07/02/2026](https://old.reddit.com/r/NYTConnections/comments/1qxdmkr/saturday_february_7_2026/) for which you'll need to [see to beleive](https://old.reddit.com/r/NYTConnections/comments/1r0k2a8/did_anyone_else_immediately_start_looking_for_loss/)



### Connections Tips
- Pre-solving is a commmon technique which means you group the words into categories, use a highlighter, etc before you press submit. This can reduce (but not completely eliminate) the chance of a herring compared to live-solving or finding categories one by one.
- It may be helpful to say the words out loud or visualize the objects in case of categories like "things with a stem" or "Y-shaped things" (real categories).
- Grouping things via word types like physical objects vs intangibles can help if you don't know the categories.
- Personally, I use [Wiktionary](https://en.wiktionary.org/) as it's the most comprehensive free dictionary. It includes slang and colloquialisms which Wynia so frequently uses. It also includes derived terms, useful for the blue category. Again, using the dictionary like this could be considered cheating, but it's almost a must for a complete solve. Note the print dictionaries often include this as well.
- [Connections Companion](https://www.nytimes.com/spotlight/connections-companion) includes a picture for the daily board (which is sometimes a spoiler), and also category hints


https://old.reddit.com/r/NYTConnections/comments/1bdai1o/list_of_reused_categories/


### How hard is too hard?
A puzzle is meant to be challenging, but how far should it go? 
Puzzles which are [built around a rainbow herring]() with obscure categories, you could argue is bad design.

But With a solve rate of around 37%, [Monday February 16th](https://old.reddit.com/r/NYTConnections/comments/1r5axwo/monday_february_16_2026/) was one of the hardest recent games, but by being a little blasphemous.

Flight, Flight, Freeze, Fawn was one of the categories, but Fawn is a uncommon addition to the group since it's basically the sole idea of one author which has then since spread due to Wikipedia, and is [unlikely to get broad academic acceptance](https://old.reddit.com/r/NYTConnections/comments/1r5axwo/monday_february_16_2026/o5ne4jk/) . So Wynia probably uses Wikipedia (and probably Wiktionary as well) to make categories.

Overlap makes a board hard, as mentioned in the [official strategies article](https://www.nytimes.com/2023/11/06/crosswords/connections-tips-and-tricks.html) , but with a high about of overlap between Humourous things and Chicken Sounds categories, words were hard to separate between the two.


# NYT Strands
[Strands]() is a word find with a twist - literally. A list of words is not given, only a vague hint of the theme. But most importantly, the words snake and twist all across the board, so it's very hard to find any particular word at a glance. If you find 3 non-theme words (of minimum length 4), you get a hint which highlights letters of a theme word.

# Chain Link
[Chain Link](https://thechnlnk.com/) is a game that would appeal to Wordle or Connections players. You guess letters of linked words. Ex: Gold Standard, Standard Fare, Fare Card, etc. It has its own set of rules & mechanics to make the game fair, and You can play past games for free.
