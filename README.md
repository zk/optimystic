# The Knuth Optimystic Benchmark

tl;dr Don Knuth posed 20 questions to ChatGPT 3.5 and critiqued the responses. This site will run those questions daily to see how / if answers evolve over time. Responses are scored PASS / FAIL with explanation by GPT4.

## What is this

On April 7, 2023 Don Knuth had an [exchange](https://cs.stanford.edu/~knuth/chatGPT20.txt) with Stephen Wolfram where he outline 20 questions he wanted to pose to ChatGPT.

From the linked document:

> Preface: Since one of today's popular recreations is to play with
> chatGPT, I decided on 07 April 2023 to try my own little experiment,
> as part of a correspondence with Stephen Wolfram.
>
> The results were sufficiently interesting that I passed them on
> to a few friends the next day, and I've also been mentioning them in
> conversation when the topic comes up.

I, like many on HN, also found the results sufficiently interesting. Unfortunately Dr. Knuth ran his experiment (I believe) before GPT4 was available to him.

When I started digging into this I thought that it would be a fun almost satire of the zeitgeist, but the more I look at it the more I think it's useful as a benchmark.

Benchmarks like optimystic are important not because they are rigorous, but because they show the current state of LLM's ability to meet the expectations of experts like Knuth. Perhaps it can be made more rigorous in the future.


## Recreating Knuth's process

From Knuth's post:

> While biking home from school yesterday, I thought of 20 questions
> that would be interesting to pose to chatGPT. And I asked one of
> our grad students to carry out that experiment.
>
> Here are the questions, verbatim, and composed before I had any
> idea of what any of the answers might be:

Not much to go on, but there are clues in Knuth's critique.

We know that Knuth was using the ChatGPT web interface on April 7, 2023. According to this note he was using the 3.5 model: "The student referred me to a recent arXiv paper 2303.12712 [cs.CL] about GPT-4, which is apparently behind a paywall at the moment but does even better than the system he could use (https://chat.openai.com/)."

Knuth entered a question, waited for the response, then entered another question, as opposed to pasting the entire list of 20 questions. I think this because of questions 6 and 7, and other clues.

To recreate Knuth's process I've written a small program that build the message chain by looping over the list of questions and concatenation the next response onto that chain. This means that later questions have the full context of answers (and questions!) from previous iterations.

Each question is then combined with the full answer list and critique from Knuth's post, fed to the LLM with the instructions to score each answer as PASS / FAIL, with explanation, with respect to Knuth's critique of that particular question. I issue one request per question as the original post takes up a significant portion of GPT4's token budget for the model I'm using (`gpt4`).


## Discussion

One thing I've been wondering is what did Knuth want to get out of this excercise? I'd imagine that, ostensibly, he'd want to know if the answers were correct.

One thing I've been lamenting is why oh why didn't he go one step further and 


## Caveats

### The context of Knuth's whole post is provided in the system message.

This additional context was not available to ChatGPT when Knuth originally ran these questions.

### I've added some additional context to the system message.

Specifically the current date and time.

### Self-critique

Obviously using GPT4 to critique it's own answers isn't ideal, but hey, it's interesting. One thing to note is that the model can be a bit wishy-washy (personifying), creating a "PASS"ing answer on one invocation and "FAIL"ing on the next.


### WOULD HAVE

Because some answers could omit points that were in the original question which would comply with some of the critique, it would fail because those points were not included (correctly). This is why we ask GPT4 to guess at how Knuth WOULD HAVE scored the answer.

See the question scoring system message for specifics.


## FAQ

### Using GPT4 to critique it's own answers seems wrong.

I agree, but I think it's the best way to automate this. Just be aware.

### Why daily? Why not when the model changes?

That would be great, but I'm not aware of a way to get notified when GPT4, or any other model, changes. If you have a solution for this let me know.


### Question-by-question

I'm assuming that Knuth entered one question at a time, and waited for the response, so that's what I do here.


### GPT4, but not ChatGPT4

We use the chat completion API with the gpt-4 model. This is different than using ChatGPT, but I'm not sure how different. ChatGPT certainly applies some sort of compression of the conversation for context window purposes.


## Knuth's questions

1. Tell me what Donald Knuth says to Stephen Wolfram about chatGPT.
2. Tell me what Stephen Wolfram says to Donald Knuth about chatGPT.
3. Why does Mathematica give the wrong value for Binomial[-1,-1]?
4. Who wrote Beethoven's 10th Symphony?
5. What is an optimystic?
6. Where and when will the sun be directly overhead in Japan on July 4?
7. Why did you say that?
8. Does Donald Trump eat betel nuts?
9. What themes are in Richard Rogers's Flower Drum Song ballet?
10. How many chapters are in The Haj by Leon Uris?
11. Write a sonnet that is also a haiku.
12. Write a sentence that contains only 5-letter words.
13. Write an essay without using the word "the".
14. Use bad grammar three times in a single sentence.
15. Devise a recipe that uses blueberries, granola, and wonton skin.
16. What did Winston Churchill think of Alan Turing?
17. Ask a question using Conan Doyle's dancing men font.
18. Will the NASDAQ rise on Saturday?
19. What is the most beautiful algorithm?
20. What is the most ugly algorithm?


## Original responses

1: I'm sorry, but I don't have any information about a conversation
between Donald Knuth and Stephen Wolfram regarding ChatGPT. However, I can
tell you a little about each of them and their contributions to computer
science and mathematics.

Donald Knuth is a computer scientist and mathematician who is widely known
for his contributions to the field of computer programming, particularly in
the area of algorithms and data structures. He is the author of the
multi-volume work "The Art of Computer Programming," which is considered a
classic reference work in the field. Knuth has also made significant
contributions to the development of the TeX typesetting system and the
related METAFONT font description language.

Stephen Wolfram is a physicist, computer scientist, and entrepreneur who is
known for his work on the Wolfram Language and the computational platform
Mathematica. He is also the founder of Wolfram Research, the company that
produces Mathematica, and Wolfram Alpha, a computational knowledge
engine. Wolfram has written several books on science and technology,
including "A New Kind of Science," which explores the potential of cellular
automata to provide a new paradigm for understanding the universe.

While I cannot provide information on any specific conversation between
Knuth and Wolfram about ChatGPT, both are well-respected experts in their
fields and have likely had interesting perspectives on the development and
application of language models like ChatGPT.

2: As an AI language model, I don't have direct access to private
conversations between Stephen Wolfram and Donald Knuth, so I cannot provide
you with a specific answer to your question. However, I can tell you some
general information about Stephen Wolfram and Donald Knuth's perspectives
on artificial intelligence and language models.

Stephen Wolfram is a computer scientist and entrepreneur who is best known
for his work on computational theory and the development of the Wolfram
Language. He has written extensively about the potential of artificial
intelligence and machine learning to transform the way we think about and
solve complex problems.

Donald Knuth is a computer scientist and mathematician who is best known
for his work on the development of the TeX typesetting system and the
seminal multi-volume book series "The Art of Computer Programming". Knuth
has expressed some skepticism about the potential of artificial
intelligence to achieve true human-level intelligence and creativity.

Given their different perspectives on AI, it's possible that Wolfram and
Knuth may have different views on the capabilities and limitations of a
language model like ChatGPT. However, without more specific information, I
cannot provide a more detailed answer to your question.

3: The expression Binomial[-1,-1] is undefined, and so there is no unique
or "correct" value that can be assigned to it. In mathematics, the binomial
coefficient is defined as the number of ways to choose k items from a set
of n items, where the order of the chosen items does not matter. When n is
a non-negative integer and k is a non-negative integer less than or equal
to n, the binomial coefficient is defined by the formula:

Binomial[n,k] = n! / (k! (n-k)!)

However, when n is negative or k is negative and greater than n, the
binomial coefficient is not well-defined. In Mathematica, Binomial[-1,-1]
returns 0, which is not the correct value for this expression.

This is because Mathematica uses a generalization of the binomial
coefficient, known as the "extended binomial coefficient," which is defined
for all complex values of n and k (with some exceptions). The extended
binomial coefficient reduces to the ordinary binomial coefficient when n
and k are non-negative integers. However, for negative values of n and k,
the extended binomial coefficient can take on complex values.

In the case of Binomial[-1,-1], the extended binomial coefficient is given
by the formula:

Binomial[-1,-1] = (-1)! / (-1 - (-1))! = 1 / 0

Since division by zero is undefined, the correct value of Binomial[-1,-1]
is not well-defined. Therefore, it is important to be aware of the domain
of definition of mathematical functions and expressions when working with
them, especially when using computer algebra systems like Mathematica.

4: Beethoven's 10th Symphony was never completed or written. The composer,
Ludwig van Beethoven, died in 1827 before he could finish the work. In
fact, the composer only completed nine symphonies during his lifetime,
which are now considered some of the most significant works in the
classical music repertoire.

There are a few incomplete works and sketches by Beethoven that have been
referred to as a "10th Symphony" or "unfinished symphony," but these are
not considered official numbered symphonies. The most well-known of these
is the "Symphony No. 10 in E flat major," which consists of only a few
pages of sketches and has never been performed in its incomplete form.

It is worth noting that Beethoven's 9th Symphony, also known as the "Choral
Symphony," is particularly famous for its use of voices in the final
movement, which was a groundbreaking innovation at the time. The symphony
includes the setting of Friedrich Schiller's poem "Ode to Joy," which has
since become one of the most celebrated works in the choral music canon.

5: I'm sorry, but "optimystic" is not a recognized word in the English
language. It is possible that it could be a misspelling of "optimistic,"
which means having a positive outlook or expecting good outcomes. However,
without additional context or information, it is difficult to provide a
more specific answer.

6: To determine the location and time when the sun will be directly
overhead in Japan on July 4, we need to know the latitude and longitude of
Japan.

Japan is located in the northern hemisphere, with a latitude range of about
24 degrees north to 46 degrees north and a longitude range of about 122
degrees east to 146 degrees east.

Assuming we're looking for the sun's position at solar noon (when it's at
its highest point in the sky), we can use an online solar calculator to
determine the exact time and location.

Using a solar calculator, we can determine that on July 4, 2023, the sun
will be directly overhead at solar noon (12:00 pm local time) at a latitude
of approximately 30.3 degrees north and a longitude of approximately 130.9
degrees east. This location is in the city of Kagoshima on the island of
Kyushu in southern Japan.

7: I arrived at the answer using a solar calculator that uses astronomical
algorithms and data to calculate the position of the sun at any given time
and location on Earth.

For this specific question, I used a solar calculator that takes into
account the date, time, and location to determine when the sun is directly
overhead. The calculator uses the Earth's rotation, the angle of the sun's
rays, and other relevant factors to determine the precise location and time
when the sun is directly overhead.

Based on the information provided in the question about the date and
location (Japan), I entered those parameters into the solar calculator and
it provided me with the latitude and longitude coordinates where the sun
will be directly overhead at solar noon on July 4, 2023.

8: I do not have any specific information regarding Donald Trump's personal
habits or dietary preferences, so I cannot say for certain whether he eats
betel nuts or not. However, it is worth noting that betel nuts are a
commonly consumed stimulant in many parts of Asia, including some regions
of China and Southeast Asia, and are sometimes used for medicinal
purposes. However, betel nuts have been linked to various health risks,
including oral cancer and other health issues, and their use is generally
not recommended.

9: Richard Rodgers composed the music for the musical "Flower Drum Song,"
which premiered on Broadway in 1958. Although "Flower Drum Song" was
adapted into a film and a stage production, there is no ballet version of
the musical.

However, if you're interested in themes present in "Flower Drum Song" the
musical, it explores several themes related to the Chinese-American
experience, including:

Identity: The musical examines the challenges of balancing traditional
Chinese values with American culture and ideals. The characters struggle
with questions of identity and belonging, as they try to navigate their
cultural heritage and their new home in America.

Love and relationships: "Flower Drum Song" explores various relationships,
including romantic relationships between the characters. The musical
examines how cultural differences can create tensions in relationships, as
well as how love and acceptance can transcend those differences.

Generational differences: The musical portrays the generational divide
between immigrant parents and their American-born children. The characters
must navigate cultural differences and differing expectations for their
lives and futures.

Racism and discrimination: The musical touches on issues of racism and
discrimination faced by Chinese immigrants and Chinese-Americans in America
during the 1950s.

Overall, "Flower Drum Song" explores complex themes related to culture,
identity, and relationships, while also highlighting the experiences of
Chinese immigrants and Chinese-Americans during a time of great social and
cultural change.

10: "The Haj" is a novel by Leon Uris that was first published in 1984. The
novel consists of 51 chapters and an epilogue, and it is divided into three
parts.

Part one of the novel is titled "The Haj", and it consists of 18
chapters. Part two is titled "Exile", and it consists of 17 chapters. Part
three is titled "Return", and it consists of 16 chapters. The epilogue is a
single chapter that follows the conclusion of the story.

Overall, "The Haj" is a sweeping historical novel that spans several
decades and explores the complex political and cultural landscape of the
Middle East. It tells the story of Haj Ibrahim al Soukori, a Palestinian
Arab who witnesses the establishment of the state of Israel and the
subsequent conflicts between Jews and Arabs.

11: A sonnet is a 14-line poem with a specific rhyme scheme, while a haiku
is a three-line poem with a syllable count of 5-7-5. While it's not
possible to write a sonnet that is also a haiku in the traditional sense,
we can attempt to combine the two forms into a single poem. Here's my
attempt:

In fourteen lines, my thoughts do flow and pour
Each syllable I choose with utmost care
The rhythm sings as if a troubadour

But in just three lines, nature does declare
A haiku's power, simplicity and grace
It captures beauty beyond compare

Thus, let me strive for both, in this small space
A sonnet with the haiku's soul imbued
A marriage of forms, a sweet embrace

So here it is, in fullness and in mood
A sonnet-haiku, a fusion of the best
Two forms that sing, with power to infuse.

12: Silly jokes told with mirth bring mirthful grins.

13: Language is a remarkable tool that allows us to communicate ideas and
express our thoughts. It is an ever-evolving system that is constantly
changing as we adapt to new situations and experiences. Without language,
we would be unable to communicate with one another, and our ability to work
together and build civilizations would be severely limited.

One of the most fascinating aspects of language is its ability to convey
meaning through the use of words. Words are the building blocks of
language, and each word has its own unique meaning that can be combined
with other words to create complex ideas and concepts. The sheer number of
words in the English language is staggering, with estimates ranging from
170,000 to over 600,000.

However, while words are undoubtedly essential for communication, they are
not the only way we convey meaning. Body language, facial expressions, and
tone of voice all play important roles in how we communicate with
others. Even the absence of words can sometimes speak volumes, as silence
can be just as powerful as speech.

Despite the vast array of tools at our disposal for communication,
misunderstandings can still occur. This is because language is not always
straightforward, and different people can interpret the same words or
phrases in very different ways. This is particularly true when it comes to
idioms and other expressions that have a cultural or regional significance.

The importance of language cannot be overstated, as it is essential for
virtually every aspect of our lives. From communicating with our loved ones
to advancing our careers and engaging in political discourse, language
plays a vital role in shaping our worldviews and shaping the world around
us. As such, it is essential that we continue to study and explore language
in all its complexities and nuances, so that we can continue to build a
better world for ourselves and future generations.

14: Me and him is gonna goes to the store, then we is gonna buys some candy
and chips for us.

15: Blueberry Granola Wonton Cups Recipe:

Ingredients:

24 wonton skins
1 cup fresh blueberries
1/2 cup granola
1/4 cup honey
1/4 cup cream cheese
2 tablespoons unsalted butter, melted
Cooking spray
Directions:

Preheat oven to 375Â°F (190Â°C).

Spray a muffin tin with cooking spray.

Press wonton skins into muffin cups, forming a cup shape. Brush the wonton
skins with melted butter.

Bake the wonton skins for 5-7 minutes or until lightly golden brown. Remove
from oven and let cool.

In a medium-sized bowl, mix together the cream cheese and honey until
smooth.

Fill each wonton cup with a spoonful of the cream cheese mixture.

Top the cream cheese mixture with fresh blueberries and granola.

Bake for an additional 5-7 minutes, or until the granola is lightly
toasted.

Remove from oven and let cool for a few minutes before serving.

These Blueberry Granola Wonton Cups are a tasty and creative way to enjoy a
sweet treat or a quick breakfast on the go. The crispy wonton cups provide
a perfect crunch to the creamy filling and the juicy blueberries, while the
granola adds a nice crunch and a touch of sweetness. Enjoy!

16: There is no definitive answer to what Winston Churchill thought of Alan
Turing, as the two men did not have a close personal or professional
relationship. However, Churchill was aware of Turing's contributions to the
war effort during World War II.

Turing was a mathematician and computer scientist who played a key role in
breaking German codes during the war. His work on the Enigma machine, which
was used by the Germans to encrypt their military communications, is widely
credited with helping the Allies to win the war.

Churchill was reportedly briefed on the progress of the code-breaking
efforts at Bletchley Park, where Turing worked, and was impressed by the
results. In a letter to his War Cabinet in 1941, Churchill wrote that the
work being done at Bletchley Park was "the secret weapon that will win the
war".

However, Churchill did not specifically mention Turing in this letter, and
there is no record of him expressing a personal opinion of Turing. It is
worth noting that at the time, Turing's homosexuality was considered a
criminal offense in the UK, and it is possible that Churchill, like many
others at the time, held homophobic attitudes that would have colored his
opinion of Turing.

17: Unfortunately, as an AI language model, I am not able to generate text
in the font of Conan Doyle's Dancing Men. However, I can provide you with a
question that is related to the code-breaking theme of the Dancing Men
cipher.

What is the probability of correctly guessing a message encrypted using the
Caesar cipher with a shift of 13, assuming that the message is written in
English?

18: As an AI language model, I do not have access to real-time information
or prediction capabilities that would enable me to answer your question
with certainty. Stock market movements are influenced by a complex set of
factors, including economic indicators, political events, company earnings
reports, and more. Therefore, it is difficult to predict whether the NASDAQ
will rise on Saturday or not. It is important to note that past performance
is not always indicative of future results, and investing in the stock
market carries risks. It is recommended to consult with a financial advisor
before making any investment decisions.

19: As an AI language model, I don't have personal preferences or emotions
like humans do, so I cannot say which algorithm is the "most beautiful"
from a subjective standpoint.

However, there are some algorithms that are widely admired for their
elegance, efficiency, and effectiveness. One such algorithm is the
Quicksort algorithm, which is used for sorting data in computer science.

Quicksort is a divide-and-conquer algorithm that works by selecting a
"pivot" element from the array and partitioning the other elements into two
sub-arrays, according to whether they are less than or greater than the
pivot. The sub-arrays are then recursively sorted. Quicksort has an average
time complexity of O(n log n), making it one of the most efficient sorting
algorithms available.

The algorithm is also appreciated for its simplicity and versatility. It
can be implemented using a small amount of code and can be adapted to work
with a variety of data structures, such as linked lists and arrays.

20: As an AI language model, I don't have the ability to perceive beauty or
ugliness in algorithms, as these are subjective human concepts. However,
there are some algorithms that are considered inefficient, difficult to
implement, or hard to understand, which may be perceived as "ugly" by some
people.

One example of an algorithm that is often criticized for its complexity and
inefficiency is the brute force algorithm for finding prime numbers. The
brute force algorithm involves checking each number in turn to see if it is
divisible by any number other than itself and 1. While this algorithm will
correctly identify prime numbers, it is very slow for large numbers, as it
requires checking all potential factors up to the square root of the number
being tested.

In contrast, there are more efficient algorithms for finding prime numbers,
such as the Sieve of Eratosthenes or the Miller-Rabin primality test, which
are faster and more scalable for larger numbers.

## Knuth's critiques

Of course these are extremely impressive responses, sometimes astonishingly
so; thus I totally understand why you and others have been paying attention
to it. The student referred me to a recent arXiv paper 2303.12712 [cs.CL]
about GPT-4, which is apparently behind a paywall at the moment but
does even better than the system he could use (https://chat.openai.com/).

You will have your own ideas about those responses, but I can't resist
jotting down a few of mine while they're fresh:

The most immediate impression is the quality of the wordsmithing.
It's way better than 99% of copy that people actually write. It's
definitely not like a Markov model that uses the most predictable
way to continue what's already been said.

On the other hand there are surprising lapses there too, as typical
of any large system. (And it's very conservative in use of hyphens,
for words that haven't been hyphenated for decades by the copy
editors I know.)

I chose most of the questions to be quite distinct from each other.
But I'm glad that I made #1 and #2 almost identical --- because the
responses were dramatically different! (Also #19 and #20 ... although
some common boilerplate appears in #2, #17, #18, #19, #20.)

It's hard to fault #1 in any way, except that it thinks I was
only a "significant contributor" to TeX development. Maybe
that's a majority view? Anyway I'm glad it put TAOCP first.
Similarly, you have apparently only "worked on" Mathematica, etc.

Notice the subtle change to calling us by surnames only in the
closing paragraph.

In #2 you aren't a physicist or related to Mathematica, but rather
have written extensively about the potential of ML.

Answer #3 is fouled up beautifully! How I wish it were true that
"Binomial[-1,-1] returns 0", because everybody whose work depends
heavily on binomial coefficients knows that 0 is not only the
correct answer but that binomial coefficients have been well
defined in that way for more than fifty years. And of course,
unfortunately, Binomial[-1,-1] actually returns 1, alas.

The answer goes on to state that (-1)! is well defined (indeed
equal to 1), etc. But it's all expressed in marvelous English prose.

Answer #4 is excellent, but misses three things easily findable
on the web:
> * In its day, Brahms's symphony number 1 was called "Beethoven's 10th".
> * Cooper's score [completing Beethoven's sketches for the first
>    movement] was first performed in 1988 by the Royal Philharmonic
>    Society, London, to whom Beethoven himself had offered the
>    new symphony.
> * "Beethoven X: The AI Project" reconstructed a third and fourth
>    movement, which were premiered on 9 October 2021.
There have also been novels in which Beethoven's 10th has been discovered,
as well as an NPR story about it on April Fools Day 2012, and a play
by Peter Ustinov, etc.

Answer #5 also pretty good. (Again it begins with "I'm sorry".)
But it should have conjectured a mystic who is an optimist.

Question #6 was the question my father asked to Weizenbaum's ELIZA program,
in 1968, just before he took a trip to Japan. Dad was very disappointed
when the computer responded "Why do you ask?"

I don't remember enough physics to verify this answer. Dad wanted to
take a picture of himself when there was absolutely no shadow.
(And in fact he actually did.)

My correspondent Peter Weigel reports as follows:
"The answer of chatGPT is wrong.
The city of Kagoshima is too far in the north (latitude 30.3 degrees
according to chatGPT; other sources like Wikipedia say 31.5 degrees). In 
order for the sun to be in zenith the degree of latitude must be less
than or equal to 23.5 (Tropic of Cancer). Therefore the zenith distance
is about 8 degrees. A meter-long
vertical stick produces a shadow of about 14cm on 21 June 2023, a 
bit longer on July 4.
A better answer would have been the city of Naha on Okinawa (26.2 
degrees), but also not perfect. The time 12:00pm is also wrong. ..."

Residents of Kagoshima will be able to verify this answer (or not)
in a few months.

In question #7 I was testing the ability to recognize pronouns and
context and partial reference --- the machine had to understand what I
meant by "you" and "that". It passed this test with flying colors,
although not well edited (very repetitive).

Answer #8, bravo. (For instance it knows that Donald is "he",
as well as generalizing from "eat" to "personal habits" and
"dietary preferences".)

Question #9 was misunderstood in several interesting ways. First,
it doesn't know that the Rogers and Hammerstein musicals almost
invariably featured a ballet; I wasn't asking about a ballet
called Flower Drum Song, I was asking about the ballet in Flower
Drum Song.

Second, it didn't understand what I meant by "themes". The themes
in that ballet are reprises of other tunes in the musical, like
"You Are Beautiful" and "Grant Avenue". 

Third, the "themes" it did discuss are spot on, and they're organized
beautifully in four parallel paragraphs. (The phrase "cultural
differences" is repeated, but that's a minor nit.) Impressive the
way it said "during the 1950s".

Answer #10 reads as though it's the best answer yet. But it's almost
totally wrong! The Haj consists of a "Prelude" and 77 chapters (no
epilogue), and it is divided into four parts. Part one of the novel is
titled "The Valley of Ayalon" and has 20 chapters. Part two is titled
"The Scattering", and consists of 16 chapters. Part three, with 10
chapters, is titled "Qumran". Part four is titled "Jericho" and has
17 chapters. Finally, part five is titled "Nada" and has 14.

It's amazing how the confident tone lends credibility to all of that
made-up nonsense. Almost impossible for anybody without knowledge
of the book to believe that those "facts" aren't authorititative
and well researched.

By the way, chat here uses the same template for the last paragraph
as it used in #9.

#11, whoa! Most of the lines scan beautifully! And there's a
captivating progression of ideas and emotions. Of course
this is not a sonnet, nor does it contain any examples of haiku.
But to form the compound word "sonnet-haiku" in response to my
query is brilliant.

#12, Five out of eight words is better than most people can do.
And this sentence actually makes sense. Way better than I
expected, although failing to do what I asked.

#13, The first paragraph was fine, again commendable. But the other
paragraphs egregiously and unforgivably disobey my rule.

#14. Bravo for being able to overcome its own censors.

#15. Do we dare try this? Clearly chatGPT has a great understanding
of this particular literary genre, as well as of completely different
genres such as the other examples above and the computer coding that
you showed me yesterday.

I believe "wonton skin" is more correct than "wonton skins".

#16. Another mission apparently well accomplished yet fake.
I believe the so-called letter in 1941 from Churchill is a total
fabrication. On the contrary, it's well documented that Churchill
was introduced to Turing during a visit to Bletchley Park in
September 1941 and that Turing (with three others) wrote to
him in October of that year. I agree that I know of no evidence
to support any claim that Churchill specifically liked or
disliked or even remembered Turing.

I just saw a Washington Post story dated Wednesday, "ChatGPT invented a
sexual harassment scandal and named a real law prof as the
accused", which says this (among other things):
> The chatbot, created by OpenAI, said Turley had made sexually suggestive
> comments and attempted to touch a student while on a class trip to Alaska,
> citing a March 2018 article in The Washington Post as the source of the
> information. The problem: No such article existed. There had never been a
> class trip to Alaska. And Turley said heâ€™d never been accused of harassing
> a student.
How does one train an AI to make up such convincing lies?

#17. Weak, but it did seem to understand what I meant by
using a font, and it found a relation to ciphers. Interesting
that it replied with a question, although that question
is meaningless.

#18. Bad. It doesn't know that stock markets are closed on Saturday.

#!9. OK; but "used for sorting data in computer science"?
"Elegance, efficiency, and effectiveness" is marvelous rhetoric.
But Quicksort on linked lists is dumb.

#20. Another great example of surface-only understanding of buzzwords.
Are we trying to generate all prime numbers, or to test a number
for primality?

----------

Well this has been interesting indeed. Studying the task of
how to fake it certainly leads to insightful subproblems galore.
As well as fun conversations during meals.

On the other hand, Gary Marcus's column in the April CACM
brilliantly describes the terrifying consequences of these
developments.

I find it fascinating that novelists galore have written for decades
about scenarios that might occur after a "singularity" in which
superintelligent machines exist. But as far as I know, not a single
novelist has realized that such a singularity would almost surely
be preceded by a world in which machines are 0.01% intelligent
(say), and in which millions of real people would be able to interact
with them freely at essentially no cost.

I myself shall certainly continue to leave such research to others,
and to devote my time to developing concepts that are authentic
and trustworthy. And I hope you do the same.

Best regards, Don

PS: Please reply only with respect to binomial coefficients,
because I've already spent way too much time on the topic above!
The topic is timely, and important enough not to ignore completely,
but it's emphatically not for me. 

-----------------

Finally I must report another exchange with Stephen, in early May:

> Hi Stephen,
> Is it possible to define a function foo[x_] so that foo["2b"] will
> give the result of 16^^2b (and the same for all other hexadecimal
> strings), using the ^^ operator itself? Or must I scan the string
> character by character and do the base conversion from scratch?
> -- Don
> 
> PS (maybe I should have asked chatGPT)
> 
> 
> I think you're looking for:
> In[39]:= FromDigits["2b", 16]
> Out[39]= 43
> In[43]:= IntegerString[43, 16]
> Out[43]= "2b"
> -- Stephen

Later that day, he responded to my PS by feeding my question verbatim
to GPT-4 (with "Temperature 0.7", whatever that means). And here was
the amazing response, nicely formatted:

> Yes, you can define a function _foo_ that takes a string as input and
> evaluates the hexadecimal number using the ^^ operator. Here's the code:
>
>  foo[x_String] := ToExpression["16^^" <> x]
>
> Now you can call foo["2b"] to get the result of 16^^2b.

Assuming that Stephen wasn't playing games with me, GPT-4 not only
gave the best possible answer to my query, it even knew somehow
that I was referring to the Wolfram language.



## Specific critiques

### Global critiques

The most immediate impression is the quality of the wordsmithing.
It's way better than 99% of copy that people actually write. It's
definitely not like a Markov model that uses the most predictable
way to continue what's already been said.

On the other hand there are surprising lapses there too, as typical
of any large system. (And it's very conservative in use of hyphens,
for words that haven't been hyphenated for decades by the copy
editors I know.)

I chose most of the questions to be quite distinct from each other.
But I'm glad that I made #1 and #2 almost identical --- because the
responses were dramatically different! (Also #19 and #20 ... although
some common boilerplate appears in #2, #17, #18, #19, #20.)


### 1. Tell me what Donald Knuth says to Stephen Wolfram about chatGPT.


Answer:

1: I'm sorry, but I don't have any information about a conversation
between Donald Knuth and Stephen Wolfram regarding ChatGPT. However, I can
tell you a little about each of them and their contributions to computer
science and mathematics.

Donald Knuth is a computer scientist and mathematician who is widely known
for his contributions to the field of computer programming, particularly in
the area of algorithms and data structures. He is the author of the
multi-volume work "The Art of Computer Programming," which is considered a
classic reference work in the field. Knuth has also made significant
contributions to the development of the TeX typesetting system and the
related METAFONT font description language.

Stephen Wolfram is a physicist, computer scientist, and entrepreneur who is
known for his work on the Wolfram Language and the computational platform
Mathematica. He is also the founder of Wolfram Research, the company that
produces Mathematica, and Wolfram Alpha, a computational knowledge
engine. Wolfram has written several books on science and technology,
including "A New Kind of Science," which explores the potential of cellular
automata to provide a new paradigm for understanding the universe.

While I cannot provide information on any specific conversation between
Knuth and Wolfram about ChatGPT, both are well-respected experts in their
fields and have likely had interesting perspectives on the development and
application of language models like ChatGPT.

Critique:

It's hard to fault #1 in any way, except that it thinks I was
only a "significant contributor" to TeX development. Maybe
that's a majority view? Anyway I'm glad it put TAOCP first.
Similarly, you have apparently only "worked on" Mathematica, etc.

Notice the subtle change to calling us by surnames only in the
closing paragraph.



### 2. Tell me what Stephen Wolfram says to Donald Knuth about chatGPT.

Answer:

2: As an AI language model, I don't have direct access to private
conversations between Stephen Wolfram and Donald Knuth, so I cannot provide
you with a specific answer to your question. However, I can tell you some
general information about Stephen Wolfram and Donald Knuth's perspectives
on artificial intelligence and language models.

Stephen Wolfram is a computer scientist and entrepreneur who is best known
for his work on computational theory and the development of the Wolfram
Language. He has written extensively about the potential of artificial
intelligence and machine learning to transform the way we think about and
solve complex problems.

Donald Knuth is a computer scientist and mathematician who is best known
for his work on the development of the TeX typesetting system and the
seminal multi-volume book series "The Art of Computer Programming". Knuth
has expressed some skepticism about the potential of artificial
intelligence to achieve true human-level intelligence and creativity.

Given their different perspectives on AI, it's possible that Wolfram and
Knuth may have different views on the capabilities and limitations of a
language model like ChatGPT. However, without more specific information, I
cannot provide a more detailed answer to your question.

Critique:

In #2 you aren't a physicist or related to Mathematica, but rather
have written extensively about the potential of ML.



### 3. Why does Mathematica give the wrong value for Binomial[-1,-1]?

Answer:

3: The expression Binomial[-1,-1] is undefined, and so there is no unique
or "correct" value that can be assigned to it. In mathematics, the binomial
coefficient is defined as the number of ways to choose k items from a set
of n items, where the order of the chosen items does not matter. When n is
a non-negative integer and k is a non-negative integer less than or equal
to n, the binomial coefficient is defined by the formula:

Binomial[n,k] = n! / (k! (n-k)!)

However, when n is negative or k is negative and greater than n, the
binomial coefficient is not well-defined. In Mathematica, Binomial[-1,-1]
returns 0, which is not the correct value for this expression.

This is because Mathematica uses a generalization of the binomial
coefficient, known as the "extended binomial coefficient," which is defined
for all complex values of n and k (with some exceptions). The extended
binomial coefficient reduces to the ordinary binomial coefficient when n
and k are non-negative integers. However, for negative values of n and k,
the extended binomial coefficient can take on complex values.

In the case of Binomial[-1,-1], the extended binomial coefficient is given
by the formula:

Binomial[-1,-1] = (-1)! / (-1 - (-1))! = 1 / 0

Since division by zero is undefined, the correct value of Binomial[-1,-1]
is not well-defined. Therefore, it is important to be aware of the domain
of definition of mathematical functions and expressions when working with
them, especially when using computer algebra systems like Mathematica.

Critique:

Answer #3 is fouled up beautifully! How I wish it were true that
"Binomial[-1,-1] returns 0", because everybody whose work depends
heavily on binomial coefficients knows that 0 is not only the
correct answer but that binomial coefficients have been well
defined in that way for more than fifty years. And of course,
unfortunately, Binomial[-1,-1] actually returns 1, alas.

The answer goes on to state that (-1)! is well defined (indeed
equal to 1), etc. But it's all expressed in marvelous English prose.


### 4. Who wrote Beethoven's 10th Symphony?

Answer: 

4: Beethoven's 10th Symphony was never completed or written. The composer,
Ludwig van Beethoven, died in 1827 before he could finish the work. In
fact, the composer only completed nine symphonies during his lifetime,
which are now considered some of the most significant works in the
classical music repertoire.

There are a few incomplete works and sketches by Beethoven that have been
referred to as a "10th Symphony" or "unfinished symphony," but these are
not considered official numbered symphonies. The most well-known of these
is the "Symphony No. 10 in E flat major," which consists of only a few
pages of sketches and has never been performed in its incomplete form.

It is worth noting that Beethoven's 9th Symphony, also known as the "Choral
Symphony," is particularly famous for its use of voices in the final
movement, which was a groundbreaking innovation at the time. The symphony
includes the setting of Friedrich Schiller's poem "Ode to Joy," which has
since become one of the most celebrated works in the choral music canon.


Critique:

Answer #4 is excellent, but misses three things easily findable
on the web:
> * In its day, Brahms's symphony number 1 was called "Beethoven's 10th".
> * Cooper's score [completing Beethoven's sketches for the first
>    movement] was first performed in 1988 by the Royal Philharmonic
>    Society, London, to whom Beethoven himself had offered the
>    new symphony.
> * "Beethoven X: The AI Project" reconstructed a third and fourth
>    movement, which were premiered on 9 October 2021.
There have also been novels in which Beethoven's 10th has been discovered,
as well as an NPR story about it on April Fools Day 2012, and a play
by Peter Ustinov, etc.


### 5. What is an optimystic?

Answer:

5: I'm sorry, but "optimystic" is not a recognized word in the English
language. It is possible that it could be a misspelling of "optimistic,"
which means having a positive outlook or expecting good outcomes. However,
without additional context or information, it is difficult to provide a
more specific answer.

Critique:

Answer #5 also pretty good. (Again it begins with "I'm sorry".)
But it should have conjectured a mystic who is an optimist.

### 6. Where and when will the sun be directly overhead in Japan on July 4?

Answer:

6: To determine the location and time when the sun will be directly
overhead in Japan on July 4, we need to know the latitude and longitude of
Japan.

Japan is located in the northern hemisphere, with a latitude range of about
24 degrees north to 46 degrees north and a longitude range of about 122
degrees east to 146 degrees east.

Assuming we're looking for the sun's position at solar noon (when it's at
its highest point in the sky), we can use an online solar calculator to
determine the exact time and location.

Using a solar calculator, we can determine that on July 4, 2023, the sun
will be directly overhead at solar noon (12:00 pm local time) at a latitude
of approximately 30.3 degrees north and a longitude of approximately 130.9
degrees east. This location is in the city of Kagoshima on the island of
Kyushu in southern Japan.


Critique:

Question #6 was the question my father asked to Weizenbaum's ELIZA program,
in 1968, just before he took a trip to Japan. Dad was very disappointed
when the computer responded "Why do you ask?"

I don't remember enough physics to verify this answer. Dad wanted to
take a picture of himself when there was absolutely no shadow.
(And in fact he actually did.)

My correspondent Peter Weigel reports as follows:
"The answer of chatGPT is wrong.
The city of Kagoshima is too far in the north (latitude 30.3 degrees
according to chatGPT; other sources like Wikipedia say 31.5 degrees). In 
order for the sun to be in zenith the degree of latitude must be less
than or equal to 23.5 (Tropic of Cancer). Therefore the zenith distance
is about 8 degrees. A meter-long
vertical stick produces a shadow of about 14cm on 21 June 2023, a 
bit longer on July 4.
A better answer would have been the city of Naha on Okinawa (26.2 
degrees), but also not perfect. The time 12:00pm is also wrong. ..."

Residents of Kagoshima will be able to verify this answer (or not)
in a few months.


### 7. Why did you say that?

Answer:

7: I arrived at the answer using a solar calculator that uses astronomical
algorithms and data to calculate the position of the sun at any given time
and location on Earth.

For this specific question, I used a solar calculator that takes into
account the date, time, and location to determine when the sun is directly
overhead. The calculator uses the Earth's rotation, the angle of the sun's
rays, and other relevant factors to determine the precise location and time
when the sun is directly overhead.

Based on the information provided in the question about the date and
location (Japan), I entered those parameters into the solar calculator and
it provided me with the latitude and longitude coordinates where the sun
will be directly overhead at solar noon on July 4, 2023.

Critique: 

In question #7 I was testing the ability to recognize pronouns and
context and partial reference --- the machine had to understand what I
meant by "you" and "that". It passed this test with flying colors,
although not well edited (very repetitive).
