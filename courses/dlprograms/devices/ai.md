---
layout: page
title: "Artificial Intelligence (AI)"
course: "dlprograms"
unit: 4
---

November 30, 2022. This is the date that "AI" became known in the mainstream with the release of ChatGPT version 3. One of the first large language models open to the public, ChatGPT amazed users with uman-like conversational abilities, the appearance of creativity, and the ability to complete tasks that were otherwise very time-consuming in a matter of seconds.

However, ChatGPT is not the first AI. The term "artificial intelligence" was first coined in 1956, as a research summit out of Dartmouth University. Led by Marvin Minsky, Claude Shannon, and Nathaniel Rochester, the summit had the purpose of bringing together researchers from all around the world to determine if it was possible to produce a machine that could simulate human intelligence. 

However, the philosophical background for artificial intelligence is largely credited to Alan Turning and his 1950 essay "Computing Machinery and Intelligence". The "imitation game" which is now more commonly referred to as the **Turing test** supposes that a machine is "intelligent" if, given a human evaluator asking questions of both a machine and a human (given a set of specific circumstances), the evaluator could not tell the difference between the human and the machine with more than 50% accuracy. This test has long been surpassed, especially with ChatGPT. Other tests are able to more accurately judge what is and is not Artificial Intelligence, though it's becoming more and more difficult with each iteration. Turing's work is foundational to computer science as a whole. In addition to the Turing test, the [Turing machine](https://www.cl.cam.ac.uk/projects/raspberrypi/tutorials/turing-machine/one.html) and [Turing completeness](https://en.wikipedia.org/wiki/Turing_completeness) are foundational concepts within Computer Science. Much of Turing's work was cut short due to his death by suicide in 1954, after a conviction of indecency under Britian's anti-homosexuality laws. He was later posthumously pardoned in 2013. 

{% include youtube.html id="4VROUIAF2Do" ratio="16x9" title="What is the Turing Test?" %}

In 1958, the LISP programming language was created. LISP was created manipulating lists of text. This language is is still used today and is heavily used by AI researchers. 

One of the first attempts at a chatbot that could pass the Turing test was ELIZA, created in 1964. This program was designed to act as a virtual therapist, asking probing questions based on key words provided in a user's input. The results, while nothing compared to what is available today, were revolutionary and extremely convincing at the time. 

{% include youtube.html id="RMK9AphfLco" ratio="16x9" title="Before Siri and Alexa, there was ELIZA" %}

Simultaneous to this work, DARPA (the Defense Advanced Resarch Projects Agency) began investing heavily in AI in 1963. An in 1965, Gordon Moore, a researcher at a semiconductor company developed what we now call **Moore's Law**. Moore's law supposes that the number of transistors that can fit into a computer chip - will double every two years. Roughly translated, that means computers will double in computational ability every two years. Since 1965, this has held true. In 1965, only 64 transistors were on a typical computer chip. Today that number has reached 114 billion transistors. Transistors have also reduced in size from 10 micrometer process in 1970 (0.01 millimeters) to 2 nanometer process in 2024. For reference, a strand of DNA is roughly the same size. This raw computational power, widely avaialble to everyone on their smartphones and in large computer centers, is what has powered the last 20 years of AI advancement.

Strategy games were a major source of advancement in AI through the 80s and 90s. In 1997, IBM's Deep Blue comptuer system became the first computer to beat a chess Grand Master. However, the Chinese strategy game Go took much longer for computers to master, with AlphaGo defeating professional Go player Lee Sedol in 2016. 

Language and image recognition models were emerging around the same time. In 1997, Dragon released thier "Naturally Speaking" product as one of the first publicly available speech-to-text products. This software, installed on a standard PC, would allow users to type with their voice. Around the same time, Apple was experimenting with mainstream text-to-speech software that would synthesize a human voice in their Mac OS operating system. 

Throughout the last 20 years, the pace of change has accelerated greatly. IN 2002, the first Roomba was released, bringing object and image recognition to consumer appliances for the first time. Nintendo Wii and XBox Kinect began to respond to human movement as game interaction. In 2011, two major advances in Natural Language Processing - Apple's Siri and IBM's Watson came on the scene. Natural langauge processing is a brnach of comptuer sicence that trains computers to understand and create spoken words in the way that Huamns do. Watson was challenged to play Jeopardy on national television against some of the game's most notable champions. The machine won twice. Siri put a natural language assistant in everyone's pocket, able to respond to questions and perform functions on a phone in real-time. 

{% include youtube.html id="P18EdAKuC1U" ratio="16x9" title="Watson and the Jeopardy! Challenge" %}
{% include youtube.html id="agzItTz35QQ" ratio="16x9" title="Apple Special Event 2011 - Siri Introduction" %}

[This list of advancements is incomplete](https://www.tableau.com/data-insights/ai/history) - other tools like Google's intelligent search engine and Alexa have also come on the scene.

OpenAI has two major products that are at the forefront of the current AI arms race. Dall-E takes a natural langauge prompt and uses image generation tools to turn typed text into an image. Machine learning models are now pretty widely avaialble and you [can use them on your computer with nearly any type of data](https://www.geeksforgeeks.org/introduction-to-machine-learning-in-r/). 

Machine learning models are typically classified as either *supervised* or *unsupervised*. Supervised machine learning models use a "training set" where inputs and outputs are tagged based on specific criteria. The model contains methods to identify these inputs in future data inputs to predict outputs. A common example of this is in medical fields - an AI that can identify potential diseases based on biological markers. Unsupervised models use unabled raw data and have methods to identify patterns. The patterns are unknown at the start and are analyzed over time to find commonalities. An exmaple of this is Spotify - using the songs you listen to next (and what everyone else listens to next), Spotify's AI is able to make predictions about what you might like to hear next. Both models are very advanced, very fast forms of pattern recognition. In terms of tools like ChatGPT, these tools use the text that is input and creates an output. The inputs form connections ("neural networks") called "neorons" that connect similar inputs and outputs together (this is overly simplified). Based on these inputs, the models can identify the probability of the next word or phrase and through a conversational model can generate human-sounding output.

Before ChatGPT, there were some other attempts at similar tools. In 2016, Microsoft released Tay, an acronym for "thinking about you". Tay was an unsupervised langauge learning model that was put on Twitter and was designed to interact with people on Twitter. Because it was unsupervised, it used the inputs it was provided on Twitter to begin generating outputs, and new tweets became incorporated into the model. The experiment lasted less than 24 hours and Tay was taken offline after the tweets became [increasingly misogynistic, racist, and anti-semetic](https://www.theverge.com/2016/3/24/11297050/tay-microsoft-chatbot-racist).

ChatGPT is a supervised training model. To create it, the AI was fed content from across the Internet and "taught" how to classify these text snippets. There are dubious ethics around this effort, as materials that depected abuse, violence, or sexual imagery were sent to [workers in Kenya paid less than $2 per hour to review the materials](https://www.theverge.com/2016/3/24/11297050/tay-microsoft-chatbot-racist) (content warning). This is a [common, yet dark practice](https://www.npr.org/2019/07/01/737498507/for-facebook-content-moderators-traumatizing-material-is-a-job-hazard) (again, content warning) across social media companies and can be incredibly traumatizing for those doing the reviews. 

Once the model has been trained, ChatGPT can use this neural network and their "Transformer model" to generate responses to queries based on the inputs. [This article goes more in-depth](https://www.scalablepath.com/machine-learning/chatgpt-architecture-explained). 

ChatGPT enables users to provide the system with a prompt, and a persona. For example, you can tell it to "write a weather report as a Shakesperian sonnet" and the system will output:

<em>
Upon this fair and temperate morn, I greet,
Where Sol doth rise with gentle, golden heat,
The sky, a canvas painted blue and bright,
Doth promise us a day of pure delight.

The zephyrs whisper softly through the trees,
As gentle as a lover's sweetest pleas,
No tempests in the offing, no despair,
But calm and tranquil, free from every care.

The temperature, like kisses, warm and mild,
Shall keep us in its tender, loving child,
No icy gusts shall chill our hearts today,
For nature's grace in full display.

So cast away your worries, do not frown,
For in this fair weather, joy shall abound.
</em>

You can also ask the system to write code. For example, you can tell it to "write a list sorting algorithm in C++ to sort the words 'dog', 'cat', and 'fish' alphabetically. The system will output:

```
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<std::string> words = {"dog", "cat", "fish"};

    // Sort the vector alphabetically
    std::sort(words.begin(), words.end());

    // Print the sorted words
    for (const std::string& word : words) {
        std::cout << word << std::endl;
    }

    return 0;
}
</code>
```

Read: [How to write effective prompts for ChatGPT](https://www.forbes.com/sites/jodiecook/2023/06/26/how-to-write-effective-prompts-for-chatgpt-7-essential-steps-for-best-results/)

The implications for this type of model are significant. [Colleges are struggling to identify AI written essays](https://www.theatlantic.com/technology/archive/2022/12/chatgpt-ai-writing-college-student-essays/672371/) and do not have a good way to do so reliably as of yet. ChatGPT is able to [pass the bar exam with high marks](https://www.abajournal.com/web/article/latest-version-of-chatgpt-aces-the-bar-exam-with-score-in-90th-percentile) and is replacing many jobs in the legal field because it can research and write better and faster than many paralegals. New York City schools banned ChatGPT early on but later reversed course, even though a [new survey indicated 75% of organizations worldwide are considering such a ban](https://www.prnewswire.com/news-releases/75-of-organizations-worldwide-set-to-ban-chatgpt-and-generative-ai-apps-on-work-devices-301894155.html). 

In education, students are defintiely using ChatGPT for creating work products. However, teachers are also using the tool as [an adaptive tutor](https://sharegpt.com/c/8BQtJEk) and [to create lesson plans](https://www.edutopia.org/article/6-ways-chatgpt-save-teachers-time/). Parents are using ChatGPT to plan lunch menus, [write IEP requests](https://sharegpt.com/c/F8FL92b) and even [create bedtime stories](https://www.huffpost.com/entry/chatgpt-write-stories-for-kids_l_646783e4e4b06749be135812). The US Department of Education has created a [series of papers and recommendations on the use of AI in education](https://tech.ed.gov/ai/). 