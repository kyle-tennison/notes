# General Adversarial Networks

You have two neural networks, a **Generator** and a **Discriminator**. 

First, you train your *discriminator*:
- It's goal is to guess if something (e.g. an image) was generated or from the training data
- You can initially train this *classification neural network* with training data. For example, if the generator is generating cat pictures, you can train it to pick out cat pictures against pictures of anything else.

Then, you start training the generator
1. Have the generator output something into the discriminator.
2. The discriminator will guess if the output was generated or not
	- If it *correctly guesses*, the generator will be updated in punishment for not producing a believable result
	- If it *incorrectly guesses*, the discriminator will be updated in punishment for not guessing correctly
3. Repeat this process, occasionally incorporating training data into the discriminator input.
4. Stop once the discriminator is no longer able to tell the difference between training data and generated data.


### References

```vid
https://www.youtube.com/watch?v=TpMIssRdhco
Title: What are GANs (Generative Adversarial Networks)?
Author: IBM Technology
Thumbnail: https://i.ytimg.com/vi/TpMIssRdhco/mqdefault.jpg
AuthorUrl: https://www.youtube.com/@IBMTechnology
```