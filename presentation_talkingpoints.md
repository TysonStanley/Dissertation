# Presentation Talking Points
##### Dissertation Proposal
##### Tyson S. Barrett
###### Aug 24, 2017

-------------

#### Intro Slides

Title:

  - This project is to develop a new framework for mediation
  - termed "Marginal Mediation"
  - I'll be going through the introduction quickly so stop me if you have any questions
  
Outline:

  - We'll briefly discuss the reproducibility "crisis" and ways to improve --- namely, Effect sizes
  - However, mediation analysis lacks effect sizes in many instances
  - Ultimately, average marginal effects can help, and when integrated with mediation, it is called "Marginal Mediation"

----------

#### Background Slides

Reproducibility:

  - Some helpful definitions regarding reproducibility
  - With these in mind, we have what some have termed a reproducibility "crisis"
  - USE EFFECT SIZES and CONFIDENCE INTERVALS
  - But note!

Repro and Mediation:

  - But this suggestion doesn't quite fly with mediation analysis in many situations
  - This hurts prevention science (mediation is commonly applied)
  - Limits its utility and raises questions about best practices
  
Mediation Analysis:

  - So what is mediation?
  - Series of regressions
  - Provides valuable information (when done properly)
  - Note the effects often sought after (indirect, direct, total)
  
But...

  - Mediation struggles with categorical/non-normal mediators/outcomes
  - For example, 
    - if X is continuous, M is binary, and Y is continuous the diagram shows how we would often model each path
    - So, how do you create a meaningful effect size when trying to combine logistic and linear regression?

Fuss?

  - Consider the *marginal effect* -- the thing you want in regression -- in two situations
    - Linear
    - Logistic
      - In logistic the marginal effect depends on the values of all the predictors 
      - and it is just plain ugly compared to linear regression

Current Approaches:

  - There are five common approaches
    1. Series of logistic regression -- narrow
    2. SEM -- probably best approach but only works with ordinal variables and only standardized effect sizes
    3. Standardize the coefficients -- only provides a p-value
    4. Interpret each path separately -- simplest proper modeling but ignores some information
    5. Pretend all variables are continuous -- horrible approach to the problem, generally used with p-values (which are wrong)
  - Ultimately, nothing great.

Average Marginal Effects:

  - In comes the AME
  - Simply, they are the average of the marginal effects
    - with the observed values in place (no crazy or impossible values)
    - without diving into the math here, both are taking the average effect of a one unit increase in the $kth$ variable
  - In a paper I'm working on right now, it shows the AME is a consistent estimator of the underlying latent effect (probability, count, etc.)

AME:

  - So, again, the AME provides 
    - Intuitive
    - Interpretable
    - Meaningful CI's
  - Let's combine them

Marginal Mediation:

  - Will take a three step approach
    1. Estimate the model
    2. Compute AME
    3. Estimate each effect (including bootstrapped CI's)
  - Nothing too intensive

Interpretation:

  - One of the main advantages
  - However, given the number of combination of variable types, it is best to consider some basic interpretation principles
  - Review principles and show meaning in figure
    1. So with M being binary, the AME is a Marginal Probability or Risk
      - A one unit increase in X is associated with a .23 increase in the risk of M.
    2. In other words, it is the effect of X on Y through M (it should be in the outcomes units)
      - A one unit increase in X is associated with a `0.23 * 1.5 = 0.345` increase in the count of Y.
    3. No big surprises here since these are essentially the regression.

Assumptions:

  - all same assumptions
  - Only additional one -- additively

------------

#### Proposed Methods Slides

Proposed Methods:
  
  - Development
  - Sim Study
  - Application Study

Method Development:
  
  - Mediation as built on OLS/GLM + AME
  - Two considerations that still need to be satisfied
    - Moderation: likely building on work by Edwards and Lambert (2007)
    - total = total: this has been a headache for some time

Software Development:

  - In `R`
  - Example of a diagram for the main function `marginal_med()`
  - Most important functions will be developed first
    - Disclosure: the main function is already developed

Monte Carlo:

  - The known population model consist of a binary M and continuous (approx normal) outcome
  - A path has a latent probability variable that maps onto a discrete mediator
  - B and C path is essentially a multiple linear regression

Monte Carlo Conditions:

  - The conditions tested will be broad for basic understanding of the method's behavior
  - Sample size: basic for what is needed for logistic
  - Effect sizes range from small to big
  - Next few (proportion and distribution) are because logistic is involved
  - Bootstrap size (hopefully 500 is sufficient)

Application Study:

  - To both demonstrate the method and to study biobehavioral phenomenom
  - Add Health
  - Two waves

Figure:

  - The diagram shows the theoretical models we will assess
  
Conclusions:

  - Ultimately, the project will produce:
    1. A new approach to mediation
    2. Guidelines for using the approach
    3. An example of the approach
    4. More evidence about the link between chronic physical conditions and poor behavioral outcomes





