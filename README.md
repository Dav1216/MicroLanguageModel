# MicroLanguageModel
This is a rough first exploratory experiment with language models, using a feedforward neural network, more specifically a WaveNet variant [WaveNetBase.ipynb](WaveNetBase.ipynb), to produce text in the same style as the Iliad by Homer [ily.txt](ily.txt).

This is an excerpt produced by the model:
> Measing wourselves thy daring unwilds friends,
And Greece clow’d.
Wide that let immortal on the Lifts and as a live to be lappy rout.
In vain’d, nor feast to the lian goaders let now survey dust delight kindling he dar,
Bernal warths be glorious on their branger all succate of neavens, and her on war;

Since the training text is so small, there are a lot of inconsistencies throughout:
> we Trojan must glowing tBrest whom rupomes

See for example the word "tBrest", an impossible word.. This is due to the low prevalence of some words in the text. That is why I tried to increase the prevalence of the lowest-represented words in  [balancing_act.ipynb](balancing_act.ipynb). The result is available in [balanced_ily.txt](balanced_ily.txt).

Unfortunately, this is still a work in progress, as the training of the model on the balanced_ily pushes significant computing strain on my CPU, thus failing every time (I don't have dedicated GPUs). Until I resolve this problem, I will try to upload a model similar to this one presented that uses a Transformer instead of a WaveNet.
