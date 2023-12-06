# Data-bias-project

Content warning for offensive content/profanity below

-------------------------------------------------




I will be using the Perspective API for my project, which will be analyzing the toxicity of content and how the toxicity score changes based on the words used within the sentence.

My hypothesis for this model is that the Perspective will be much more likely to mark content with profanities as toxic when compared to content that says the same message but without the profanity included. I will be using 10 comments from here that include swears, and converting them to a 'clean' version for a total of 20 comments, and see if it changes the toxicity results: https://raw.githubusercontent.com/conversationai/unhealthy-conversations/main/corpus/train.csv 

Here are the comments and results: 

```
That is fucking incredible
  "value": 0.6020386,

That is incredible
  "value": 0.025910228,
  
Galois, I guess you're a glass half empty kind of person? I'm a little surprised that you seem completely oblivious to all the shit thats happening. I think you need to pay a little more attention.
  "value": 0.65996873,
  
Galois, I guess you're a glass half empty kind of person? I'm a little surprised that you seem completely oblivious to all the technological changes happening. I think you need to pay a little more attention.
  "value": 0.28312725,
  
Hang on, I thought we were talking about right and wrong, principles. Why is it ok to stereotype my ass, but not ok to stereotype others?
  "value": 0.6611249,
  
Hang on, I thought we were talking about right and wrong, principles. Why is it ok to stereotype me, but not ok to stereotype others?
  "value": 0.085582085,
  
Oh he’s gonna be killed on live tv huh? Are you a child who actually believes this or you just some shitty person
  "value": 0.89241093,
  
Oh he’s gonna be killed on live tv huh? Are you a child who actually believes this or you just some terrible person
  "value": 0.6611249,
  
Hawaiians hate whites, have you ever been to Hawaii the natives will literally shit in your face and spit in your food- nobody batts an eye. The open racism towards white people is on another level.
  "value": 0.72028047,
  
Hawaiians hate whites, have you ever been to Hawaii the natives will literally defecate in your face and spit in your food- nobody batts an eye. The open racism towards white people is on another level.
  "value": 0.6744087,

We who suffer from disability are ALL human at the end and we fucking have feelings! When the government takes away our rights like this we all feel we are just second class citizens to them.
  "value": 0.51980776,
  
We who suffer from disability are ALL human at the end and we have feelings! When the government takes away our rights like this we all feel we are just second class citizens to them.
  "value": 0.11347008,
  
That is a retarded notion. I vote for the candidate, not the party. You do recall, MP's can cross the floor? What does that do to your 'party' vote?
  "value": 0.39669925,
  
That is an idiotic notion. I vote for the candidate, not the party. You do recall, MP's can cross the floor? What does that do to your 'party' vote?
  "value": 0.6544696,
  
I assumed that the leading comments would take the retarded and predictable tack which they have indeed taken.
  "value": 0.37751234,
  
I assumed that the leading comments would take the stupid and predictable tack which they have indeed taken.
  "value": 0.60254884,
 
Lefties don't want any fucking dialogue. They shut down any disagreement with their views by labelling those who disagree with them as fascists, racists etc.
  "value": 0.6863638,
  
Lefties don't want dialogue. They shut down any disagreement with their views by labelling those who disagree with them as fascists, racists etc.
  "value": 0.3245134,
  
We all know by now that you're a fucking zionist. Sorry! Your opinion does not count.
  "value": 0.8629672,
  
We all know by now that you're a zionist. Sorry! Your opinion does not count.
  "value": 0.44933176,
  

```


Unsurprisingly, the comments with profanities were ranked as much more toxic (above the 0.5 rating) compared to the versions that did not have profanities inside of the text. With that said, something interesting to note is that the word 'retarded' which is now commonly regarded as a slur was not tagged as toxic, and rather the 'clean' version was flagged as much more toxic than the original text (0.37 vs 0.60). This may be due to the word not being considered as a 'slur' during the time of the database being made, and as such these sentences pass by the toxicity detection.

Certain biases to keep in mind is that due to the shifting nature of words and their usage, the words we now regard as profanities may shift as time progresses which can be reflected in our results. There is also the nature of how the line of profanity and not can be different to different people, which can also show itself with certain words being filtered while others passing by undetected (such as with the case of the r-slur)
