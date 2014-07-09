---
layout: page
title: README Driven Development
permalink: /strategies/readme-driven-development/
---
## <a name="stage-1"></a> Stage 1: Inception
This is the ideation stage. You might have an idea or someone else has one that they decide to delegate to you. Either way, it's your problem now, and you need to brainstorm how you are going to solve it.

Remain spontaneous and never disregard any ideas at this stage. For more interesting thoughts on how to be more creative, listen to [John Cleese's lecture on the topic][cleese].

### Deliverables

1. Produce anything written to avoid staring at a blank sheet.

### Tips

* Resist the temptation to start coding.
* Write, sketch, white board, flowchart etc.
* Let yourself be disorganized.


## <a name="stage-2"></a> Stage 2: Planning
This is the planning (aka. *documentation*) stage. This is where the ideas laid out in [README Driven Development][readme-driven] (RDD) come into play.

To avoid doing things in vain, try to boil your initial ideas down to the logical [Minimum viable product][mvp].

Another powerful approach is to break down the overall process into discrete components (first level). For example "branding" (name, logo, etc.) would be one (very) discrete component. Noting possible overlap and possible areas for reuses might help you later.

### Goal
Fix/harden your ideas from [Stage 1](#stage-1) and move towards a more organized project.

### Deliverables

1. A flowchart to describe the process overview (no details)
2. A README-file describing the scope and goal of the project

### Tips

* Still no coding.


## Stage 3: API design
This stage is repeated for each of the components from [Stage 2](#stage-2). Try to work on each component separately but it's OK to jump between them.

Another important part of this stage is to build up your test suit. I don't fully subscribe to Test Driven Development but you can push yourself to always include at least one test with each new feature/merge.

When a component grows out of it's intended scope it might be nessesary to go back to [Stage 2](#stage-2) and split the current component into smaller, more managable, components.

### Deliverables

1. A breif section for the central documentation
2. A detailed flowchart (mentioning each function)
2. A test sub-suit
3. An inline documented API for the component
4. Implemented functions and/or classes


## Stage 4: Putting things together
This stage is where you would start putting individual components together into larger constructs. Continue to explore how components in the most intuative way go together. This could lead to the development of a CLI.

If any one component starts to take over, it's worth considering if you might be able to fork it out into it's own project.



[cleese]: http://www.brainpickings.org/index.php/2012/04/12/john-cleese-on-creativity-1991/
[mvp]: http://en.wikipedia.org/wiki/Minimum_viable_product
[readme-driven]: http://tom.preston-werner.com/2010/08/23/readme-driven-development.html
