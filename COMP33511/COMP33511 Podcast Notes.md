[[COMP33511]]

# 0 - Overview and Logistics

# Preamble
- ==toms diner was important because it could initially **break** mp3 encoding==
- [[UX.pdf]] as a whole describes UX as an empirical science, which allows products to be built with the user in mind, in a range of manners (some of which may be tangential)

# 1 - Be Curious, Be Critical
- ==UX is about making very few assumptions, and always trying to break any propositions==
- UXers are a bridge, but also help users themselves to define what they want/need, and ultimately evaluate whether this is the case
- jacob nielsen 5 people quote - misinterpreted and 'carried away' with
- 'time to task' becomes more or less irrelevant outside of a work context - as computers became more recreational, mere quantitative measures became less effective hence the shift from traditional HCI to UX

# 2 - What is UX?
- we can't really talk about UX without talking about HCI, since UX's roots exist within HCI
- HCI, conceived around the 60s but really gaining traction around the 70s, sort of existed as a way to emphasise the importance of computers being made for people, rather than just the other way round
- HCI as it developed, became much more quantity based rather than quality based (as a means to be comparable to perhaps mathematics or more 'traditional' sciences), taking leads from psychology and social sciences, anthropology, etc.
- UX is essentially bordering both fields, trying to take aspects from the quantitative HCI while introducing many more qualitative aspects
- quantitative measures are typically more generalised but provide more accurate views as to a population, while qualitative views provide a much more 'deeper' view, but with smaller population sizes resulting in less representative outcomes
- HCI typically concerned with the tangible, chose to ignore intangible aspects for the most part - meanwhile, UX says yes to both the tangible and intangible
- ==there is no definite definition for UX even to today==
- UX can exist across multiple timespans i.e. anticipated UX, momentary UX, episodic UX (a single experience), cumulative UX
- UX in short, can be seen as an umbrella term which includes some traditional HCI, but extends upon what could be considered as its intangible shortcomings

# 3 - UXD and Visual Design
- [[UXD vs UX]] - UXD is more focused on graphic design, and what things visually look like - ==UX engineering can be considered a separate field to such==
- we are not designing/creating so much of the physical interface, but more acting as a ==bridge between [users, user requirements and user evaluation] and [software developers, development processes, other specialists]==
- [[design systems]] + [[design languages]] - these are also created by UXD'ers typically, its just your job to abide by them the majority of the time
- [[interaction design]] concerns UX engineers more as less of a visual aspect is involved with the general concept of the 'flow' of some application
- [[zero ui and conversational interfaces]] involve less interaction design (think of alexa)
- ==don't confuse your ability to build user experiences with the ability to build GUIs== - you don't create the design systems/languages, but it can very much be your place to encourage such practices to those with the capability to do so

# 4 - People are Complicated
- UX is everywhere, and the situations people may find themselves in could be almost anything, which you may have to consider
- we shouldnt create systems which are any more complicated than they need to be
- Jef Raskin, author of 'The Humane Interface' quote on p35 of [[UX.pdf]]
- [[auditory channel + visual channel]] + somatic, olfactory
- thinking and learning - whether things are learnable/familiar. ==we still do not have definitive models of human cognitive systems==, we can just make best guesses as to what works best for humans
- [[explicit vs implicit communication]]
- [[types of input]]

# 5 - Practical Ethics
- ==everything you do with users should be done with an ethical framework in mind==
- ethics are also good for science, in terms of discussing with others how you're going to collect specific data and what you'll do with it
- the need for ethics became very obvious after WW2 (after the nazi regime) - protection was needed for subjects
- veranda anthropology essentially insensitive ?
- we should refer to them as 'participants' rather than subjects
- [[key ethics principles]]:
	- competency: know your limitations
	- integrity: the outcome shouldn't bother you (i.e. you should have no bias)
	- science: follow the scientific method (double/blind trials)
	- respect: treating participants fairly and respecting their autonomy
	- benefits: maximise benefits and minimise harm
	- justice: undertake research with participants who benefit from the results
	- trust: maintain trust, anonymity, confidentiality
	- responsibility: you have a duty of care for your participants
- in short ==ethics allow you to stop screwing up== - being part of a community allows you to build better software for them

# 6 - Gathering User Requirements
- also known as requirements elicitation/analysis - we want to get requirements from knowledgeable users, rather than just from the head of some department or people already involved in the process
- ==collecting requirements is key for ensuring you build the right thing for users==
- [[digital phenotyping]] vaguely related
- [[user centred design]] - the whole point of these processes are to be ==iterative== in nature
- post it notes are primary
- levels of time available:
	- 6 months: [[task analysis]]
	- 6 weeks: group interviews, social events
	- shorter // other constraints e.g. lack of users - archival methods, old systems

# 7 - Modelling Requirements
- at this point we've 'gathered' requirements, but need an appropriate way to represent them such that they can be presented to software engineers and other specialists
- ==we are trying to make gathered information consistent to know what exactly people want==
- [[informal modelling methods]] + [[formal modelling methods]]
- use cases are super important for providing specific requirements / expectations
- personas + scenarios (good for describing flow) - post it storyboards (low fidelity but semi-formalish, easy to be modified by users)
- beware of issues such as groupthink
# 8 - Developing for UX
- agile is common touchpoint in UX - we are building agile systems, though in some cases perhaps waterfall may be applicable (critical systems, for instance)
- [[development methodologies]] - agile vs cowboy coding
- cowboy coding more for experimental works where you don't know exactly what you're doing
- [[developing for UX]]
- [[separation of concerns]] and different methodologies to go about doing such
- continue to conform to [[design languages]] // [[design systems]], to create holistic interfaces
- ==in short, for typical projects use agile, for more research oriented use cowboy coding==

# 9 - Prototyping + Rapid Application Development (RAD)
- at this point, we've elicited requirements and have modelled them into a more structured format, in order to be presented to SWEs and users ([[user centred design]])
- we're now trying to translate these requirements into low->high fidelity prototypes and mockups ([[prototyping and fidelity]])
- at high fidelity, you've had a lot of input from the user, and are expecting not as much change request from the user
- at low fidelity, you can expect users to be able to easily contribute and suggest changes
- commissioners, developers and users may all have different requirements
- [[rapid application development (RAD)]] - conceived and perhaps most important around the 90s - essentially go from high fidelity prototype -> working model
- wizard of oz system: no real implementation, just present expected outcomes as the user interacts - think mechanical turk


# 10 - Effective Experience (Accessibility)
- accessibility aka a11y - we don't only look at people with accessibility issues, but consider the wider population
- [[barriers of effectual use]]:
	- visual impairment
	- cognitive impairment
	- hearing impairment
	- physical impairment
	- situational impairment - non disabled users in situations which affect how they can use an app
	- combinatorial impairment - i.e. ageing users who suffer from 1+ impairments above
	- illiteracy
	- developing regions
	- exclusion
- [[MSAA + UIA]] + interface bridges, which 'translate' accessibility requirements from one interface to another
- [[potted principles of effective experience (POUR + foot-stool)]]:
	- perceive ==P==erceivability
	- perceive ==O==penness
	- perceive ==U==nderstandability
	- perceive ope==R==atability
	- perceive flexibility (skins, adjustable hotkeys)
- in short, accessibility is not just limited to those with 'traditional' accessible needs - it extends as far as to making software usable by those in developing regions, and those who within certain situations in which the software may be used are experiencing some sort of impairment
- 'nothing about us, without us' - be sure to include those with accessibility issues within the UX process, for full understanding

# 11 - Efficient Experience (Usability)
- this differs from 'traditional' usability which purely focuses on task completion time, and aims to include aspects such as ==accessibility and learnability==
- created in the early days of HCI with the star user interface - the computer becomes more familiar to people through adopting real world analogies (the desktop, files, folders, trash bin)
- 'dogfooding' - testing and using products by their own developers (xerox star)
- [[usability model]]s - modelling how long tasks should take
- [[potted principles of efficient user experience (SSSADD FLCR)]]:

# 12 - Affective Experience (Emotion)
- affective experience and engagement are the 2 of 4 development principles which lean much more to the UX side of HCI, where principles are much more intangible, and 'cutting edge'
- [[affective experience]] + [[levels of emotional response design]]: visceral, behavioural and reflective
- [[visual attention]] - faces provide a source of involuntary visual attraction for humans
- [[affective computing]] - the development of technologies which understand, detect, and ultimately may 'have' human emotions (via GSR, facial expression, etc.)
- [[potted principles of affective experience]]:
	- facilitate quality
	- facilitate aesthetics
	- facilitate flow - the optimality of tasks
	- facilitate pleasantness
	- facilitate satisfaction
	- ==facilitate personality - highest precedence==
- overall, the subjects of emotion are difficult to isolate due to their subjectivity, intangibility, making them difficult to present to people/companies in general

# 13 - Engagement
- the idea of [[group dynamics]] is hugely important for engagement today - adding it when appropriate can provide significant benefits
- [[gamification]] + [[funology]] when appropriate are also beneficial (funology more specifically is 'softening the blow' of lengthy software processes etc)
- bolt-on gamification can be more problematic - some companies will just try to include it when not necessary - also consider ethical implications of gamification
- [[potted principles of engagement]]:
	- facilitate social dynamics
	- facilitate progression
	- facilitate play
- ==consider what it means to gamify your app, and whether it is really appropriate==

# 14 - User Evaluation
- evaluation is very much similar to requirements collection, in the sense that the users become the main source of info once again (we can use a lot of the same techniques)
- the goal is to make sure what has been requested/required is what has been delivered
- [[expert evaluation (walk-throughs + heuristic evaluation)]]
- [[qualitative evaluation methods]] - 'free living settings' are most ecologically valid
- [[quantitative + hybrid methods]] - aim for hybrid methods in most situations, since no one method will collect all the info you need (triangulation = 3 methods)
- think-aloud methods can be useful, but can be biased ('guinea pig effect'?)
- participatory design allows for evaluation throughout the process
- [[3 properties of a good questionnaire]]
- [[common evaluation tools]]
- double and triple blind trials to prevent bias
- pre-testing can compare the deliverable to an already existing implementation certain users might already be familiar with

# 15 - HITL + digital phenotyping
- [[digital phenotyping]] + [[digital phenotypes]] 
- HITL systems really came around during NASA's Apollo mission - a stronger version of [[user centred design]], making users an integral/indivisible part of the process
- another common example is including humans within AI systems
- JCR licklider - man computer symbiosis

# 16 - Evaluation Analysis
- evaluation analysis is essentially the scientific bedrock for determining whether the things we've built fit the user requirements
- typically we have hypotheses ==which must be refutable== - we want YES/NO answers, rather than anything in the middle/ a maybe
- [[variable types + measuring variables]] - things like interval variables may be more trusted than categorical variables, which are more open to interpretation
- data driven approaches can involve altering a hypothesis over time through conducting interviews and finding recurring themes between interviewees
- probabilistic sampling is much less common in UX
- [[UX analysis statistics aside i]] ==is not of huge concern== - we typically care about non-parametric tests since we probably wont have big enough of a sample to represent a normal distribution

# 17 - IRL
- up until now, everything has been described in a 'streamline' like process, where everyone is happy, everything goes as it is supposed to, without a hitch, and resources are as required
- ==this is not how things happen in the real world==
- various [[common UX evaluation constraints]] exist
- methods of [[information elicitation]] - note that laboratory elicitation removes the most confounding variables, but wont give ecologically valid conclusions
- participants, resources (in terms of specialists), and the skills available are all constraints too
- some bits about brooks - ==look a bit more into ?== i.e. throwaway projects (agile esque)
- second system effect
- parallelising your system can be very important in giving everybody something to do

# 18 - Final Thoughts
- overall, UX is still something not fully defined at this point of time
- originally UX mightve been thought as something completely quantitative, but over time has expanded into the qualitative field, with 'romantic' aspects to it
- we've covered
	- how to elicit and model requirements
	- designing the information space, interactions of user experience - ==emphasis is NOT on physical, visual aspects==
	- agile when you know what youre going to build - cowboy coding when you dont
	- various architectures for separating concerns, parallelising tasks
	- design process - potted principles
	- testing + validation (ab testing)
	- the constraints of real life (resources, optimism)
- encyclopedia of human computer interaction is a good resource if you are to carry on