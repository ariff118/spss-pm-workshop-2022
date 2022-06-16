---
date: "2022-06-25"
draft: false
excerpt: You can share information about yourself with the community on GitHub by
  creating a profile README. GitHub shows your profile README at the top of your profile
  page.
links:
- icon: door-open
  icon_pack: fas
  name: website
  # url: https://bakeoff.netlify.com/
- icon: github
  icon_pack: fab
  name: code
  # url: https://github.com/apreshill/bakeoff
subtitle: Model 1a - One Moderator (Basic Moderation) - Continuous Moderator
title: Module 1
weight: 1
---

## Introduction  

- Example Variables: 1 predictor *X*, 1 moderator *W*, 1 outcome *Y*  

- *Preliminary Notes:*  

    - Model 1 assumes that:  
      1. The primary IV (variable *X*) is continuous or dichotomous.  
      2. Any moderators (variables *W, V, Q, Z*) are continuous, though the dichotomous moderators can be handled.  

## How to run in SPSS Process Macro?  

1. Insert model framework image here.  

2. Analyze > Regression > PROCESS v4.0 by Andrew fF. Hayes  
    Insert image here...  

3. Insert variables (*Y*, *X*, and *W*) and choose `Model 1`  
    Insert image here...  

4. Click Options button:  
    - check on `Generate code for visualizing interactions`  
    - Mean center - choose `All variables that define product`.  
    - Conditioning values - choose `-1SD, Mean, +1SD`  
    - check on `Johnson-Newman output  
    - click `Continue`
    insert image here ...  

5. click `OK` to run analysis  

## Reading the output  

- Description of Model along with the different variables where *Y* is Dependent Variable, *X* is Independent Variable, and *W* is the Moderating Variable.  

- Model Summary, provides summary of the model with *R*, $R^2$, *F* statistic, and p value for the overall model.  

- Next, is the coefficients, with impact of DV (OP),IV (Culture), and the interaction effect to assess if there is moderation (RA) or not.  

- Inthis example, since the interaction effect is significant, the Role Ambiguity moderates the relationship between Culture and OP.  
- Test of unconditional interraction, this shows the change in $R^2$ due to interaction _(x*w)_, this is also significant.  

...insert output image here.  

### Johnson-Newman intervals and simple slope analysis  

- Johnson-Newman intervals tells you the range of values of the moderator in which the slope of the predictor is significant vs. nonsignificant at a specified alpha level.  

- In simple terms Johnson-Newman identifies regions in the range of the moderators variable where the effect of the focal predictor on the outcome is statistically significant and non significant.  

### Data Visualization  

There are two ways to draw the interaction path in order to give you a clearer visulization on the effects of moderator on the relationship between the predictor and the outcome variable.  

1. Using the SPSS syntax  
    - copy the script from the process macro output.  
    - in SPSS, open a new syntax file  
    - paste the script into your syntax file  
    - click `Run` button to create your interaction graph  
    ...insert image here.  

2. Using the StatsTool package created by James Gaskin  
    - link to download the STatTools Package ->  

> 1. The study assessed the moderating role of Role Ambiguity (RA) on the relationship between Collaborative Culture (CC) and Organizational Performance (OP). The results revealed a negative and significant moderating impact of RA on the relationship between CC and OP (b = -0.095, t = -2.767, p = .006), supporting H1. Moderation analysis summary is presented in Table 1.  

> 2. Results of simple slope analysis conducted to better understand the nature of the moderating effects are shown in Figure 1. As can be seen in Figure 1, the line is much steeper for Low RA. This shows that at Low RA, the impact of CC on OP is much stronger in comparison to High RA. As shown in Figure 2, as the level of RA increased, the strength of the relationship between CC and OP decreased. This is due to the negative slope coeeficient obtained.
