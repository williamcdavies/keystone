## Thursday Part 1

### Intro - Sudeep Chandra
- Emplace scientific information into the policy making process. 
- Build connections to indigenous populations and tribal governments over the next 3 years.
- Losing newspapers in rural areas. Solution: Broadcast stories via radio + podcast (KUNR)
- Tahoe Co-lab (semester-long experience collaborative research residency grounded int he Tahoe Basin and Lake Tahoe environment) (can i join this?)

### Agenda - Facundo Scordo
- we don't have a wide perspective on the impact of smoke emissions on lakes. only case studies. don't have a complete framework.

#### Questions
- how much particle mass remains suspended in the air over the lake as smoke?
- how much particle mass is deposited onto the lake as pyrometers?
- what are the size distribution, chemical composition, and microbial composition of these airborne and deposited particles?
- how do lake characteristics and seasonal dynamics influence the processing and impact of different types of wildfire emitted particles?

#### Tasks
1. define methods for quantifying how wildland fire emissions spread through the atmosphere and deposit on the landscape
2. assess the chemical and biological composition of wildland fire emissions
3. refine a conceptual framework linking wildland fire emissions and lake ecosystems
4. propose protocols to improve the monitoring of wildland fire emissions during active fires.

#### Outcome
One-hundred open questions to advance understanding of wildland fire emissions, and their impacts on lake ecosystems

### Lightning Talk #1: Modeling wildfire smoke transport and unresolved processes (Derel Mallia, Ph. D.)
- problem: satellite resolution
- wildfire plume rise (can be up to lower stratosphere)
- pyroconduction (cloud over fire)
- chemistry in the atmosphere depends upon what is burning (uncertainties within uncertainties)
- two types of deposition: 
	- 1. dry deposition (particles fall due to gravity)
	- 2. wet deposition (rain can remove particles from the atmosphere)
- large smoke plumes can alter the weather beneath the smoke plume
- a lot of unknowns regarding particles $> 10 \mu$m (most research regards particles $< 10 \mu$m)
- ejected pyrometeors and firebrands can be lofted ahead of the burn perimeter to start new fires or land in lakes
- pyrocumulonimbus clouds
- tools
	- lagrangian transport models
- we need new rules for modeling particles $> 10 \mu$m
- current gaps in smoke modeling
	- particles larger tan PM_10 are not accounted by most smoke modeling frameworks
	- computing hourly smoke emissions is especially difficult
	- smoke emissions factors can vary substantially by fuel type, fire temp, and are highly uncertain especially for volatile organic compounds
	- smoke transport can be very sensitive to the smoke injection height, and there are limited observations of plume top heights
	- smoke chemistry is a fundamentally messy problem due to complex chemical reactions, uncertain smoke emissions, secondary organic aerosol formation
	- near-source dynamics: rapid entrainment, strong turbulence, interaction between multiple smoke columns, subgrid plume structure

##### Questions
How do we distribute high resolution domains for two separate domains (fields) within the same working solution?

### Lightning Talk #2: _ (Facundo Scordo, Ph.D.)
- in addition to smoke and firebrands, wildfires emit vast amounts of pyrometearos (10-2000 $\mu$m) that can influence ecosystem processes
-  physics based model
	- predict where these particles were going to land
	- can be tested via in situ sampling 
	- we assume different sized particles will be updrafted at differing heights
- limitations
	- simplified particle geometry: assumes spherical particles, neglecting irregular shapes that influence drag, lofting, and deposition distances
	- simplified particle behaviour: treats pyrometeors as passive (extinguished) and excludes smolder/combustion effects that can alter buoyancy and residence time.
	- size distribution bias: particle size data are derived from high-altitude sampling (~5 km) likely underrepresenting larger particles that fial to reach those elevations. 
	- uncertain particle properties: fixed effective density does not capture variability in composition and combustion state affecting settling and transport
	- simplified fire energetics: assumes 100% fuel consumption and fixed energy partitioning, ignoring spatial/temporal variability in fire intensity and emissions
	- coarse atmospheric and plume representation: uses simplified wind scaling, capped plume height, and idealised deposition geometry, limiting realism of long-range transport and spatial deposition patterns.

### Breakout Session 1
- why are we unable to implement sophisticated models for cross-field procedures?
- what is needed to implement sophisticated models for wildfire analyses?
	- a. what is landing in the waterbody (size, chem, comp)?
	- b. how much mass remains as smoke? 
	- we would like a model (or two) for short-scale smoke deposition and long-scale smoke coverage
- how does turbulence affect firebrands?
- why do our models model particles as spheres and other simple shapes?
	- the more complex the shape, the computational complexity increases
- we are in good shape for modelling small particles. large particles just aren't being measured. we need more lab studies looking into how we model particles $> 10 \mu$m. how do we measure the flux of these particles.
	- the best way to do this is to combine radar sensing and in situ sampling
- we need more in situ measurements. when we use a radar to remotely sense, we don't know exactly what we need to be looking at.
	- its difficult to identify particles amongst water vapour
	- generalisations can be made
	- moisture absorption will completely change how radar detects particles
		- wetter particles will detect a smaller particle as a larger particle
	- where do we sample in the plume? do we care more about what is closer to the ground? how do we gather samples in the lower portion of a smoke plume? 
		- temperature, aggregation size, decomposition -> affect smoke particles. makes it difficult to receive the particle
- how do we exploit existing observation networks to gather new information.
	- NEON?
	- can we link particle samples to fires?
	- what are the observations we can use in the near term and how what do we need to build to get observations for the long term? time frames for different tools? 
- how do we present this problem in such a way that we can fund / innovate in this field? -> regulations. clear air act. 
- can we acquire filters from sampling sites? 
- can we establish requirements to store / analyse filters? 
- depending on the particle size, the type of light penetration will change the dynamic of the CA
- what happens to large particles that settle at lake beds? 
- how far can particles really travel? have we really tested what is being deposited relative to distance?
- can we use volunteers to form an impromptu sampling network?
- radar as a solution for sampling firebrands $> 10 \mu$m
- what are the pros and cons of particle modeling strategies?
	- ularian models: only care about densities, not particle numbers, so we can model bulk particle transportation
- how can we further classify pyrometeors? subsets of pyrometeors may fit different models?
- existing atmospheric models don't model the physicality of wildfire plumes. what changes need to be made to integrate this into existing atmospheric models? 
- can we run enough small scale studies for different vegetation to generate generalisations for updrafting particles of differing size and composition?
- what size of pyrometeor is most common? and which has the biggest impact? spatially? 
- solve many sub-problems at different pyrometeor sizes instead of a single classification
- why have we been ignoring this class of particles and heres why it is important.
- heterogeneous smoke modelling 
- how much of a fire particle is left by the time it is deposited? what is the lifetime of a particle? what does it look like at each stage of life? at what point does a particle become so diffused that it is no longer treated as a smoke particle?
- can we, knowing the isotopic signature, where those particles came from -> no, but we may be able to use microbes as bio-tracers because they are so distinct?
- can we categorise all of these problems using two variables: complexity, importance? need to prioritise our gaps. 
- sampling vs modelling vs monitoring.

### Group Discussion 1

#### Group 1
- we need particle distribution datasets
- we need to model pyrometeors microphysics
- how can we couple models?
- how do present the assumptions of smoke modeling and how do we disambiguate models for those who aren't familiar with their use
- maybe we need two different frameworks
	- pyrometeors
	- smaller particles
- to what extend are people willing to participate in scientific advancement? 

#### Group 2
- no model-er -> expansive questions
- list of what ideal models can provide
	- spatial resolution at lake and watershed scale. we could potential get greater spatial resolution closer to the file. can you downscale from larger scale models if we wanted to understand how topography can impact deposution
	- chemical composition specific to ash. how morphology and size can impact differing chemical reactions
- micronutrients and contaminants
- temporal resolution. how might deposition or atmospheric attenuation of light change throughout the lifetime of the fire. what are the long term affects? two different kinds of models. primary model and redistribution model
- detailed information on deposition characteristics under various conditions
- topographical affects. do we have smoke shadow affects and things like that?
- question: we want to model all the... we want to know how much was emitted and depending on the particle size... can a Lagrangian model accommodate the total mass of a wildfire? -> should be able to under many assumptions.
- question: particle shape. in the models we run now they are spheres. we need to model the microphysics for different shapes. is it worth doing? do we know enough to switch from a sphere or a disk to other shapes? 

#### Group 3
what processes do we think are important in terms of smoke emissions and lake impacts?
- big vs. small particles
	- structure
	- surface area
	- availability of nutrients based upon particle combustion completeness. what is the chemical makeup of these particles
	- particle can be hydrophobic. does this affect how long they break down in a water body
- proximity of the fire to the lake. hetero- vs homo-geneous plume types
- shapes
- lake properties
- connecting lake with atmosphere. how does the lake interact with a highly local plume vs a plume that are further downwind but exposed over a much longer period of time
- dose response function
- food web integration
- algae blooms
- emissions and plume rise
- surface energy budget
- time-space matrix
- many processes span across different spatial-temporal scales
- experiment design: 
	- what data is available? at what frequency?
	- how do we classify lakes?
	- do we have a better handle on lakes further from the fire since there are less uncertainties?
	- do we need a field experiment
	- do we need to forecast the plume to sample the lake before and after
- think about the lake ecosystem outcome we are interested in and accommodate temporal scales appropriately.
- how are lakes that are enclosed by geographic features impacted differently over time than lakes that are open to direct deposition?
- fire season is extending into the wet season? how does this change how we model particle diffusion?

## Thursday Part 2

### Lightning Talk 1 ()
- biological emissions -> smoke ecology -> transport -> deposition and dispersal
- methods:
1. fly, UAS, sample ambient air and smoke
2. remove filters, preserve under sterile conditions
3. lab: stain epifluorescence microscopy to countr cells
4. lab: dna extraction, pcr, rRNA...
- greater bacterial flux produced by fire
- can we trace microbes back the combustion zone?
- 70% of what we can trace in the smoke, we can trace back to a source (42% in ambient)
- air quality index reflects microbial diversity
- smoke contains biological ice-nucleating particles
- we don't know if microbes have interactivity or if we are just seeing a mix of what the plumes are producing. what are the functional roles of microbial ecosystems within smoke plumes?
- fungi in smoke retain virulence and can cause disease
- what is the difference between smoke and dust in regards to microbial transportation?
- are microbes attached to particles? we don't know. not a consistent correlation between PM2.5. some correlation between the larger particulates.
- temperature is not consistent across the combustion zone -> smoke is not sterile
- no one has yet to look at the long distance sustainability of microbial systems within smoke emissions
- active gene expression? 
- 