# The Knuth Optimystic Benchmark

tl;dr Don Knuth posed 20 questions to ChatGPT 3.5 and critiqued the responses. This site will run those questions daily against the latest model(s) to see how answers evolve over time. Responses are scored by GPT4 as PASS / FAIL with explanation.

## What is this?

Around April 7, 2023 Don Knuth posed 20 questions to ChatGPT and subsequently [had an exchange](https://cs.stanford.edu/~knuth/chatGPT20.txt) with Stephen Wolfram about his experience.

From the linked document:

> Preface: Since one of today's popular recreations is to play with
> chatGPT, I decided on 07 April 2023 to try my own little experiment,
> as part of a correspondence with Stephen Wolfram.
>
> The results were sufficiently interesting that I passed them on
> to a few friends the next day, and I've also been mentioning them in
> conversation when the topic comes up.

I, like many others on HN, also found the results [sufficiently interesting](https://news.ycombinator.com/item?id=36012360)! 

My initial reaction was that he should have used GPT4 (interestingly, in working on this project I've come to realize we have the important bits: his questions and reaction to the generated answers).

The Knuth Optimystic Benchmark aims to observe how well models satisfy the specific critiques Knuth made about the quality of answers he got for his questions over time. Once a day (week?) Knuth's 20 questions will be run against the latest model and resulting updated answers will be posted at [https://optimystic.ai/knuth](https://optimystic.ai/knuth).

Benchmarks like optimystic, while not particularly rigorous, could still be valuable as they show LLMs' ability to meet the expectations of experts like Knuth. Perhaps it can be made more rigorous in the future. I'd love to hear your ideas.


## Recreating Knuth's process

From Knuth's post:

> While biking home from school yesterday, I thought of 20 questions
> that would be interesting to pose to chatGPT. And I asked one of
> our grad students to carry out that experiment.
>
> Here are the questions, verbatim, and composed before I had any
> idea of what any of the answers might be:

Not much to go on, but there are clues in Knuth's critique.

I'm assuming that Knuth's grad student was using the ChatGPT web interface with the 3.5 model ("The student referred me to a recent arXiv paper 2303.12712 [cs.CL] about GPT-4, which is apparently behind a paywall at the moment but does even better than the system he could use (https://chat.openai.com/).") and entered questions one-by-one waiting for each response as opposed to entering the list of 20 questions all at once..

To recreate Knuth's process I've written a small program that builds the message chain by looping over the list of questions. Note that later questions have the full context of answers (and questions!) from previous iterations. The system message is blank.

Each question is then combined with the full answer list and critique from Knuth's post, fed to the LLM with the instructions to score each answer as PASS / FAIL, with explanation, based on Knuth's critique of that particular question. I issue one request per question as the original post takes up a significant portion of the GPT4 8k model's token budget.


## How to help

Love this? Hate this? Did I miss anything? Let me know over on [twitter](https://twitter.com/heyzk) or in the GH issues. Specifically I'm interested in how to make this useful for the larger LLM / AI community.

Second, I think it would be interesting to open this up to other experts, not just those in Computer Science. I'd love to hear who you'd find interesting so I can ask them which twenty (or ten, or five) questions they'd ask the AI. The only requirement is they're considered an expert in their field.


## Caveats / FAQ

### Self-critique

Obviously using GPT4 to critique it's own answers isn't ideal, but hey, it's interesting (and scalable). Note that the model can be a bit wishy-washy (personifying), creating a "PASS"ing answer on one invocation and "FAIL"ing on the next.


### Why daily? Why not when the model changes?

That would be great, but I'm not aware of a way to get notified when GPT4, or any other model, changes. If you have a solution for this let me know.


### Question-by-question

I'm assuming that Knuth entered one question at a time, and waited for the response, so that's what I do here.


### GPT4, but not ChatGPT4

We use the chat completion API with the gpt-4 model. This is different than using ChatGPT, but I'm not sure how different. ChatGPT certainly has directives in its system message, and compresses longer conversations for context window purposes.


## TODO

* Move code over from internal repo to this repo
* Add scoring prompt to repo
* Add alternative models, anthropic etc.
* Experiment with prompting techniques (chain-of-thought, tree-of-thoughts) to show possible improvement alongside input-output prompting.


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
