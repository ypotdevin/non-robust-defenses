On this page I collect neural network defenses against adversarial examples, which have been proven to be at most as robust as a simple baseline (the corresponding undefended model or a random guessing), or not robust at all.
Many defenses listed here were proposed, when there was not yet consent regarding how to thoroughly evaluate neural network defenses.
By publishing [On Evaluating Adversarial Robustness](http://arxiv.org/abs/1902.06705) and [On Adaptive Attacks to Adversarial Example Defenses](https://arxiv.org/abs/2002.08347), Carlini et al. and Tramèr et al. gave suggestions on how to properly claim robustness of a newly developed neural network defense mechanism.
A key suggestion was to adaptively attack the considered defense.

An attacker model, which assumes the attacker to be oblivious to the protection mechanism in place, is merely enough to perform sanity checks, but not enough to make reliable claims regarding robustness.
Therefore, when faced with an adaptive attacker, many proposed defenses turned out to be quite less robust than previously claimed.

My goal by curating this collection is not at all to blame the authors of the listed defenses.
As mentioned above, the methodology of how to properly evaluate a defense had to develop over the past few years.
Instead, my goals are to

  1) urge practitioners not aware of the state of the art in the machine learning robustness research, to not blindly use the collected defense mechanism in their applications
  2) gather in a single place ideas, which (in the way they were implemented) do not enhance robustness of neural networks
