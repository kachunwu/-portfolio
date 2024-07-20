---
layout: page
title: Neural Correlate of Loss Aversion
description: A fMRI study trying to capture the neural correlate of loss aversion
img: assets/project/3_LossAversion/project3_preview.jpg
importance: 3
category: Cognitive-Neuroscience
related_publications: true
---
During my MPhil study, I used the fMRI data of our lab to practice the analyses of fMRI data. Eventually I did a online poster presentation at CNS*2020 (Since that was during COVID-19), titled "<i>Loss aversion and outcome-value encoding: a negative association between posterior insula activity and loss aversion coefficient</i>". If you want to see my poster, you can find it in my [Publications](/publications) page.

## Loss Aversion
> Losses loom larger than gains
> — Kahneman & Tversky (1979)

People hate to lose things, and this hatred is stronger than our love to gain something. The loss doesn't even need to be a actual loss from what we have already got, but could just be the opportunity cost of what could be gained from a safer option. Daniel Kahneman (1979) suggested that the potential losses possess twice as strong of psychological value than potential gain. They used the term "loss aversion" to describe people's elevated sensitivity to losses than to gain. 

<div class="row">
    <div class="col-sm-8 mt-3 mt-md-0">
        In cumulative prospect theory, they defined a loss aversion index, Lambda (𝜆), in the utility function. When the bigger a person^′ s 𝜆 is, the more a person scale up the utility of a loss (i.e. more negative value). As seen by the value function on the left, although the gain or loss were both $1, theey did not possess the same magnitude in terms of psychological value: the loss were perceived as much larger than the gain. How much is the inflation is depended on lambda: the bigger a person′ s 𝜆 is, the more that person scale up the utility of a loss
        <br> <br>
        The aim of this study was to find BOLD activations/deactivation correlated with individuals' lamda.
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/project/3_LossAversion/utility_function.jpg" title="utility_function" class="img-fluid rounded z-depth-1" %}
    </div>
 </div>  

<br>

## Behavioral Task

<div class="row justify-content-sm-center">
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid path="assets/project/3_LossAversion/LAT_design.jpg" title="utility_function" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-2 mt-md-0">
        The loss aversion task was very simple. Participants were presented with two options: <br>
        1. Gamble: which has a 50/50 chance of winning or losing certain amount of money <br>
        2. Don't gamble: gives a guaranteed outcome. <br> <br>
        We presented nine different scenarios to the participants, as shown in the figure on the left, and used these behavioral data to caculate their lambda by fitting a logistic function. <br>
        $$ P(Gamble) = \frac{1}{1 + e^{- z}} $$
        $$ z = \beta_0 + \beta_{gain}(Gain) + \beta_{loss}(Loss) $$
    </div>
 </div>  

Then, we can use the fitted $$\beta_{gain}$$ and $$\beta_{loss}$$ to calculate the Lambda (𝜆): 

$$ 
\lambda  = \frac{ - \beta_{loss}}{\beta_{gain}} 
$$

<br>
## BOLD signal after feedback

We fitted a general linear model (GLM) consisting five regressors (gamble, no gamble, win, loss, guaranteed outcome) to the BOLD signal and contrast the win and loss feedback images with the guarantee outcome image. Specifically, we are interested in how individual reacted to the gambling outcome, and how it related to people's loss aversion.

<div class="row align-items-center">
    <div class="col-sm mt-2 mt-md-0">
        When the person receive a win feedback, we see activation at right nucleus accumbens (NAcc) and left NAcc (the region in orange). We also see a deactivation at left posterior insula (the region in the blue).
    </div>
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid path="assets/project/3_LossAversion/win_feedback.jpg" title="utility_function" class="img-fluid rounded z-depth-1" %}
    </div>
 </div>  

<div class="row align-items-center">
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid path="assets/project/3_LossAversion/loss_feedback.jpg" title="utility_function" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-2 mt-md-0">
        On the other hand, when the person receive a loss feedback, we see activation at right nucleus accumbens (NAcc) and left NAcc (the region in orange). In contrast, the deactivation at left and right posterior insula were much stronger than that of win feedback.
    </div>
 </div>

<br>
## ROI signal correlate with Lambda

We also inputted lambda to the GLM as second-level covariate and found it negatively predict the activity at the left posterior insular clsuter. Here are the correlation between participants' lambda and the percentage signal change of the extracted cluster.

<div class="container">
    <div class="row">
        <div class="col-sm mt-2 mt-md-0">
            {% include figure.liquid path="assets/project/3_LossAversion/win_lambda.jpg" title="utility_function" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-2 mt-md-0">
            {% include figure.liquid path="assets/project/3_LossAversion/loss_lambda.jpg" title="utility_function" class="img-fluid rounded z-depth-1" %}
        </div>
     </div>
    <div class="row"> 
        <div class="col-sm mt-2 mt-md-0 caption">
            Win feedback
        </div>
        <div class="col-sm mt-2 mt-md-0 caption">
            Loss feedback
        </div>
    </div>
</div>  

It appeared participants who had a strong loss aversion also had reduced left posterior insular activity when they receive feedback from their decision. 

Our results indicated:
1. The left posterior insular had reduced activity when receiving feedback, especially when the person lose the bet.
2. The reduction in left posterior insular activity was even bigger for those who had a strong loss aversion. 

Some researcher proposed insular activity could represent the "interoceptive tuning mechanism" of outcome value that helps to optimize people's decision making in the future, and studies reported reduced insular cortex activity for addicts in stimuli evaluation tasks (see [this paper](https://doi.org/10.1016/j.tics.2015.05.005) for details). Although the relationship between loss aversion and addiction is still inconclusive, our results indicates the two may shared some underlying neural processes.

> The biggest risk is not taking any risk... In a world that is changing really quickly, the only strategy that is guaranteed to fail is not taking risks.
> — Mark Zuckerberg
