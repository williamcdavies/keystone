## Thursday Part 1.

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
	- simplified particle behaviour: treats pyrometeors as passive (extinguished) and excludes smoldering/combustion effects that can alter buoyancy and residence time.
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
- we are in good shape for modeling small particles. large particles just aren't being measured. we need more lab studies looking into how we model particles $> 10 \mu$m. how do we measure the flux of these particles.
	- the best way to do this is to combine radar sensing and in situ sampling
- we need more in situ measurements. when we use a radar to remotely sense, we don't know exactly what we need to be looking at.
	- its difficult to identify particles amongst water vapor
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
