# Context

This repo was created to participate in the HuBMAP - Hacking the kidney competition that can be found [here](https://www.kaggle.com/c/hubmap-kidney-segmentation/overview).

# Framing the problem

Our best estimates show there are over 7 billion people on the planet and 300 billion stars in the Milky Way galaxy. By comparison, the adult human body contains 37 trillion cells. To determine the function and relationship among these cells is a monumental undertaking. Many areas of human health would be impacted if we better understand cellular activity. A problem with this much data is a great match for the Kaggle community.

Just as the Human Genome Project mapped the entirety of human DNA, the Human BioMolecular Atlas Program (HuBMAP) is a major endeavor. Sponsored by the National Institutes of Health (NIH), HuBMAP is working to catalyze the development of a framework for mapping the human body at a level of glomeruli functional tissue units for the first time in history. Hoping to become one of the world’s largest collaborative biological projects, HuBMAP aims to be an open map of the human body at the cellular level.

This competition, “Hacking the Kidney," starts by mapping the human kidney at single cell resolution.

Your challenge is to detect functional tissue units (FTUs) across different tissue preparation pipelines. An FTU is defined as a “three-dimensional block of cells centered around a capillary, such that each cell in this block is within diffusion distance from any other cell in the same block” (de Bono, 2013). The goal of this competition is the implementation of a successful and robust glomeruli FTU detector.

You will also have the opportunity to present your findings to a panel of judges for additional consideration. Successful submissions will construct the tools, resources, and cell atlases needed to determine how the relationships between cells can affect the health of an individual.

Advancements in HuBMAP will accelerate the world’s understanding of the relationships between cell and tissue organization and function and human health. These datasets and insights can be used by researchers in cell and tissue anatomy, pharmaceutical companies to develop therapies, or even parents to show their children the magnitude of the human body.

## Supervised evaluation

This competition is evaluated on the mean <strong> Dice coefficient</strong>. The Dice coefficient can be used to compare the pixel-wise agreement between a predicted segmentation and its corresponding ground truth. The formula is given by:

$$\frac{2* | {X}\bigcap{Y} | }{ |X| + |Y|}$$


where X is the predicted set of pixels and Y is the ground truth. The Dice coefficient is defined to be 1 when both X and Y are empty. The leaderboard score is the mean of the Dice coefficients for each image in the test set.

Submission File
In order to reduce the submission file size, our metric uses run-length encoding on the pixel values.  Instead of submitting an exhaustive list of indices for your segmentation, you will submit pairs of values that contain a start position and a run length. E.g. '1 3' implies starting at pixel 1 and running a total of 3 pixels .

Note that, at the time of encoding, the mask should be binary, meaning the masks for all objects in an image are joined into a single large mask. A value of 0 should indicate pixels that are not masked, and a value of 1 will indicate pixels that are masked.

The competition format requires a space delimited list of pairs. For example, '1 3 10 5' implies pixels 1,2,3,10,11,12,13,14 are to be included in the mask. The metric checks that the pairs are sorted, positive, and the decoded pixel values are not duplicated. The pixels are numbered from top to bottom, then left to right: 1 is pixel , 2 is pixel , etc.

## Desired presentation form note

Participants in this challenge will also have the opportunity to win prize money through the presentation of their submission. After entering the competition, participants can also elect to submit a presentation of their results for review by judges drawn from industry, academia, and government. Top selected submissions will have the opportunity to make a presentation to the judges panel to be evaluated on the below criteria.

### Methodology (50 points) [Scientific Prize]

Are the statistical and modeling methods used to identify glomeruli in the PAS stained microscopy data appropriate for the task?
Are confidence scores and other metrics provided that help interpret the results achieved by the modeling methods?
Did the team validate their methods and algorithm implementations and provide information on algorithm performance and limitations?
Did the team provide any evidence that their method generalizes beyond this immediate task, for example to other FTUs such as alveoli in lungs or crypts in colon?
Did the team document their method and code appropriately?

### Innovation and Applications (30 points) [Innovation Prize]

Did the team develop a creative or novel method to segment glomeruli?
Is the presented characterization of glomeruli useful for understanding individual differences, e.g., the impact of donor sex, age, or weight on the size, shape, or spatial distribution of glomeruli?
Did the team provide insights that would be useful for generating reference glomeruli for inclusion into a Human Reference Atlas?

### Diversity and Presentation (30 points) [Diversity Prize]

Does the team embrace diversity and equity, welcoming team members of different ages, genders, ethnicities, and with multiple backgrounds and perspectives?
Did the authors effectively communicate the details of their method for segmenting glomeruli, and the quality and limitations of their results? For example, did they use data visualizations to present algorithm setup, run, results and/or to provide insight into the comparative performance of different methods? Were these visualizations effective at communicating insights about their approach and results?
Are the important results easily understood by the average person?
Submission Instructions
You can make as many submissions as you like, but we will only consider your latest submission before the deadline of February 1.

All team members must be listed as collaborators on the submitted Notebook, and all team members must accept the competition rules before the submission deadline.

A valid submission will include:

Notebook Analysis: At least one notebook containing the analysis to support your proposal. All notebooks submitted must be made public on or before the submission deadline to be eligible. If submitting as a team, all team members must be listed as collaborators on all notebooks submitted.