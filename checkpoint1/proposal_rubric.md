# Rubric for Project Proposal

Your project proposal will follow the format of a standard research proposal, and will be written in markdown format.  It will be saved in the same directory as this rubric, and simply named "proposal.md."  It should not be longer than 2-3 pages max, and may be shorter.  It will have the following sections.

### Title

A nice short title for your project, helping me to understand roughly what it is you are trying to do.

### Team

Each project will have a team of 3-5 people, and one person will serve as the point of contact (POC) for the team who will own the repository. The POC will be responsible for managing the repository, and I will only grade submissions in this repository. Everyone will be granted access to this repository.  This section should include the full names of each team member, **along with their github ids**, and indicate the POC for the group.

### Introduction

This section will introduce your project.  It will _briefly_ answer the following questions from [Heilmeier's catechism](https://www.darpa.mil/work-with-us/heilmeier-catechism).

- What are you trying to do? Articulate your objectives using absolutely no jargon.
- What is new in your approach and why do you think it will be successful?  (be brief here, you can expand more later!)
- Who cares? If you are successful, what difference will it make?

### Literature Review

This section will answer the second question from Heilmeier's catechism:

- How is it done today, and what are the limits of current practice?

Here, you will review methods that have been attempted (use [Google Scholar](https://scholar.google.com) to find out), or cite literature to provide evidence that your method is novel.  You should include citations to reviewed material.  Use [github's markdown syntax for footnotes](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#footnotes)[^1].

Also use this section to establish _stakeholder needs_.  That is, for stakeholders that have specific but perhaps non-obvious needs (e.g., a city traffic planner will need to know about temporal variation in pedestrian traffic and the density of office buildings in order to determine the best placement of traffic signals).  You should list each of your stakeholders here, explain why they are stakeholders, and the clarify needs. Recall from our lecture that I do not expect you to do your own stakeholder interviews, but I do expect you to do a little research online.

### Data and Methods

This section will introduce your data and specify your modeling approach.

#### Data

You will include a link to your data, along with summary information (e.g., how many columns, rows, and the types of features).  Also include some discussion about the data's provenance - how do you know the data is reliable?  Does it have meta data, and if not, what else do you know about it?  If you anticipate needing more than one dataset, please indicate each dataset you anticipate needing and provide evidence that those datasets are available.

#### Methods

Describe your modeling approach.  What sorts of transformations / preprocessing are going to be necessary?  What sorts of modeling techniques will you apply? How are you going to evaluate your models (note that your evaluation should be consistent with stakeholder needs)?

### Project Plan

Tell me what you are going to do and when.  We have roughly three months (the final report is due December 15).  What milestones do you hope to achieve?  You might organize this as a table.  For example:

Period|Activity|Milestone
|---|---|---|
|9/22 - 9/29|Stakeholder analysis </br> EDA </br> Initial exploration with a baseline model on a sample of the data|Completed stakeholder analysis and data exploration. Additional datasets identified as necessary.
|9/29 - 10/6|Preprocessing and modeling refinements. Comparing candidate modeling approaches| Initial pass with cleaned data. Candidate approaches for modeling finalized.

etc.

### Risks

This section will describe potential risks to the project. This should include both potential pitfalls and roadblocks, as well as any approaches to mitigation.  What will you do if some aspect of your plan fails?

# Presentations

For this checkpoint, your presentation will have 7 slides, as follows:

1. **Title** A title slide with the names of all team members.  Please introduce yourselves during the presentation.
2. **Problem** This slide will offer a succinct description of the domain problem. During the presentation, you will describe the problem in sufficient detail for us to understand why this is a machine learning problem (and not some other kind of problem, like statistical analysis).
3. **Stakeholders** This slide should list major and minor stakeholders. During the presentation, you will characterize the needs of the stakeholders with respect to he domain problem. Be specific! These needs will dictate what you will do.
4. **The Gap** This slide will 1) explain how the problem is currently addressed today, and 2) why this is inadequate or could otherwise be improved. You should reference specific methods - either from the research literature or industry solutions. This slide should demonstrate that you have done some preliminary research and have an understanding of how people have solved the problem. 
5. **Data** This slide will introduce the data you are going to use to address the problem.  You **must** have a set of data identified at this point, and you **must** explain why you think it is sufficient and of high quality. If your data is not sufficient, I will ask you to redo your proposal.
6. **Approach** Explain you approach.  How are you going to model your data?  Which techniques do you anticipate using?  Where do you think the most effort will be?  What resources will you require?
7. **Risks** What risks to the project do you foresee?  Be realistic, and explain what you will do if they come to pass.

# Grading

- Does your proposal include all of the above mentioned sections? [1 point]
- Have you clearly identifed your stakeholders and their needs [1 point]
- Have you answered the 5 Heilmeier questions mentioned effectively [1 point]
- Is you proposal plan feasible, and do you have sufficient detail to give me confidence that you will succeed? [1 point]
- Did your presentation address all required points and follow the structure provided above [1 point] 

> This rubric is scored out of 5 and **scaled to the 4 project points** allocated to the Proposal in the syllabus.

[^1]: Like this




