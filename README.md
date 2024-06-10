## Brief intro to Renaissance Technologies

Renaissance Technologies ("RenTech") is one of the pioneers of quantitative investing. Founded by Jim Simons, a brilliant mathematician, it was one of the first companies in the world to use Machine Learning (ML). To this day, it remains one of the most advanced hedge funds in the world, while also being incredibly secretive. They only hire extremely intelligent people, usually from maths, physics, and statistics departments, who can leverage their quantitative skills to improve their models. 

They are so good at what they do that their best-performing fund - the Medallion fund - is completely closed to the public. They don't even find it necessary to include outside investments. Though they don't publicise their returns, it has been estimated that the fund increases in value by an average of 30 to 40 per cent every year, an absolutely astounding performance. 

RenTech is a fascinating company. If you're interested in learning more, please listen to the Acquired podcast and their episode on them: https://www.acquired.fm/episodes/renaissance-technologies.

Thank you also to the Acquired team for making this wonderful episode, which served as inspiration for this project.

## What is this project?

After reading "Fooled by Randomness" by Nassim Nicholas Taleb for a second time, I wanted to create a Monte Carlo simulation for myself. From his description, it seemed like a wonder tool to examine probabilities, markets, and build counterfactuals. I decided to practise it and, as I had also become interested in RenTech, I picked their case study to try to model. 

According to Acquired, RenTech has only a very slight edge on any one of their trades, at something like 50.5% or 50.75%. They also learnt early on that more trades were better for them, and I wanted to see why. So this Monte Carlo simulator allows you to see possible investment paths over a set number of years and periods (weeks, by default). Every period, a set number of trades is performed; the returns on these trades are instantaneous and modelled by a normal distribution parametrised by a mean very close to zero (0.005, by default) and standard deviation such that the upper limit of the 95% confidence interval sits at 10% (again, by default). The capital for the next period is then just the sum of the resulting capital after all trades have been completed.

All of these parameters can be changed and investigated in the simulation, and I give two examples of how I did that in the notebook.

#### Assumptions and weaknesses
Several simplifying assumptions were made:
 - No shorting or leveraged trades; maximum loss is original investment amount.
- No transaction costs.
- No financial crises or market turbulence.
- Capital is always invested.

These assumptions bring some weaknesses into the simulation. Transaction costs, for example, are a big concern for hedge funds and, although RenTech is not a high-frequency fund, it does still have a relatively short window of owning stocks. Without transaction costs, there is no punishment for having more trades, which could skew the results of simulations, making high-trade scenarios seem more lucrative than they really are. This assumption was made mostly because I am not sure under what fee structure these big hedge funds operate. They could be flat flees or as a percentage of the money in the transaction. In future versions, this could be built into the model.

There are more weaknesses in this model that I could talk about, but this was a small project just focussing on learning to create a Monte Carlo simulation. If you have any comments please feel free to share them.

