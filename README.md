# MicroLanguageModel
This is an experiment of mine with language models, using a feedforward neural network, more specifically a WaveNet variant [WaveNetBase.ipynb](WaveNetBase.ipynb), to produce text in the same style as the Iliad by Homer [ily.txt](ily.txt).

This is an excerpt produced by the model:
> Measing wourselves thy daring unwilds friends,
And Greece clow’d.
Wide that let immortal on the Lifts and as a live to be lappy rout.
In vain’d, nor feast to the lian goaders let now survey dust delight kindling he dar,
Bernal warths be glorious on their branger all succate of neavens, and her on war;

Since the training text is so small, there are a lot of inconsistencies throughout:
> we Trojan must glowing tBrest whom rupomes

You might just say "most words don't even exist". This is exactly what is intersting in this approach: the character level generation of words. If the generation of full coherent words was the focus, I would have tokenized each word instead of each character. This is similar to taking all the words in the training text and randomly positioning one word after another mostly. Since the training set is not that large, the model would not be able to produce coherent sentences. But, the model learnt just enough to figure out words. Generating one character after another, the model actually generates its own vision of what words look like, how do they start and when do they end and, on first glance, they looks real.

I used [balancing_act.ipynb](balancing_act.ipynb) to increase the prevalence of the lowest-represented words. The result is available in [balanced_ily.txt](balanced_ily.txt).

You can run the jupyter notebook and train on whichever training data you want by replacing "/Users/david/condaProjects/ily.txt" in 
> rows = open('/Users/david/condaProjects/ily.txt', 'r').read()

with the path to the training file you have. If the model does not finish training, it might be due to lack of computing resources. Try reducing batch size.
