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

### Breakout Session #1
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

### Group Discussion #1

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

### Lightning Talk #3: _ ()
- biological emissions -> smoke ecology -> transport -> deposition and dispersal
- methods:
1. fly, UAS, sample ambient air and smoke
2. remove filters, preserve under sterile conditions
3. lab: stain epifluorescence microscopy to count cells
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
- do we know if microbes are in the emissions depending upon burning material, the microbes are different? lacking the spatial range of effectiveness.

### Lightning Talk #4: _ ()
why do we need to study deposition of all particle sizes? the bulk of the mass in a dust plume is > 10 microns.

capture wet and dry deposition independent of each other. measure the full spectrum of dust composition.

2017 - 2025

what is atmospheric deposition made of?
- charcoal/ash (every sample)
- large particles being transported quite far
- potential long term affect of ash getting reemitted

how might topography influence ash deposition?
- as we increase elevation we see a larger fraction of nitrous, phosphorus, and carbon in the deposition

dust may be adding micronutrients 

brown ash > grey ash > ground ash in terms of bioavailable phosphorus
brown ash has stronger effect in terms of ClA than other types of ash

how much does ash in the atmosphere matter for rain composition?

data opportunities
- dry deposition data/samples 20217-2025
- wet deposition 2017-2019
- throughfall + rainfall

Dong et al. 2012 Mtn Sci
Wen et al. In review

### Lightning Talk #5: _ (Jeff Nielson)
can wildfire dust composition be predicted? 

### Breakout Session #2
assess the chemical and biological composition of wildland fire emissions

cannot imagine physically detaching a microbe from its community into the air. we need a conceptual image of how microorganisms become airborne. 

conductive forces pick up dust and soil material. expecting some relationship between the organism and _ would be a bit of a stretch. maybe the microbes are mobilised by the physical processes that the fire generate but connecting the microbe with certain particle size is a focus.

studies have shown that it takes about 90 days for ash (inorganic deposits that you get when forests burn) to be removed from the atmosphere.

categorically question the notion that individual cells are being updrafted. 

i wonder if in smoke we have a lot of that uv attenuation. does that allow them to stay viable longer and transfer in the atmosphere. are they proliferating because of their conditions

how much of the microbiome in the atmosphere is being scrubbed?

we need more data, more data from more fires to categorise chemical and biological composition. 

when microbes re-enter traditional environments, how do they affect existing microbiomes?

soil temperatures in a fire don't get hot enough to sterilise soil (some exceptions). in a fire, you have a changing composition, but not complete sterilisation. 

how does the amount of cells represent the amount of cells in the water? in waterbodies it could be 5 or 6 orders of magnitude less than soil/sediment. 

how does the density of microbes compare between ash and dust?

introduced microbes to lake ecosystems remain until the lake mixes? up to a 1.5 years in tahoe. 

cyanobacteria are populated surface of soils. they form the biocrust. the would be the first to be lifted off during updraft. 

we need to disaggregate samples by cyanobacteria species to understand of the deposition of cyanobacteria into lake ecosystems propagate.

if its not the same cyanobacteria then _ changes.

we saw bigger responses in Cla lakes that had an existing community of cyanobacteria

why do cyanobacteria respond so well to changes in lake parameters? 

urban fire particles -> does collection capture particle emissions sourced from urban fuels. yes, but only if the subject lake is in proximity to an urban fire. more heavy metals + plastics. we havn't seen an understanding a study on the chemical profile of ash at certain distances. 

we expect to see large quantities of heavy metals in smoke sourced from urban fires.

depending on the percentage burn, what is the output?

there is some relationship between the smoldering ability of a particle and maximum distance it can travel.

you get enrichment of inorganic ash 

it sounds like ecological work is characterising. can we fractionate the different materials to see what kind of surface functionality and reactivity they had? yes, 

we only have data from one fire that is highly characterized.

how much variability would there be from fire to fire in terms of micro nutrients? there was about 9-30% of the mass of the tree is inorganic.

do models need to account for the transport accounted for by the fire and also the transport accounted for by the default

"i think from our deposition data, looking at size distribution, we can get information about source information"

### Group Discussion #2
- what happens when particles hit the lake is a black box
- long plume duration measurements need to happen
- what can we predict about plume composition based upon behaviour of the source fire
- is there a threshold for certain chemical or biological impacts for source fires? (distance)

## Friday Part 1

### Lightning Talk #1: _ ()
- is there a way we can look at smoke at its position in the column? NOAA HMS disregards column position
- differences in ash, smoke, and lake size can alter the magnitude of ecological response
- does smoke over inland waters matter?
	- although depositions of as hand aerosols can provide nutrients for phytoplankton and algae, it affects heat fluxes and temperature dependent processes
- do responses to smoke vary across different types of lakes? yes, effects will be larger in nutrient-limited systems
- extent of smoke has increased linearly since 2006
- studied the affects of smoke on lakes/ponds experiencing the same smoke events at the same time
	- site are distributed within a single watershed
	- smoke in 2020 and 2021 covered sites for an average of 49 days between august and october
	- measured high frequency temp and dissolved O in 2 lakes and 4 ponds
	- sites span a size gradient (depth from 1m to 10m)
- immediate response in water temperature to smoke exposure
- smoke reduces daily heat gain
- same sites respond differently depending upon the type of smoke they experience
- high frequency temperature and dissolved O loggers inform metabolism estimates
- smoke changes ecosystem metabolic rates
- waterbody size may be an...

### Lightning Talk #2: _ (Facundo Scordo, Ph.D.)
- uv light has a bleaching affect in the first meter of the water column
- wildfire emissions introduce nutrients, reduce ultraviolet light and promote algal growth

### Lightning Talk #3: Caldor Fire Ecosystem Response ()
- why tahoe?
	- mega-fire (>200,000 acres)
- during the caldor fire there was a large increase in atmospheric deposition
- post-wildfire: greater quantiles of lepotlynbya were discovered 
- how do wildfire disturbances compare to other biological disturbances?
	- bray-kurtis similarity index?
	- it took ~1 year to return for the phytoplankton count to return to a pre-fire state
- we haven't looked into the affect of ash on zytoplankton
- we need higher resolution temporal data

### Lightning Talk #4: Smoke on the Water: Wildfire Impact on Cyanobacterial Bloom Proliferation (Teso Coker)
- when fire exposure is present in a spatial grid cell and year, the odds of observign a cyanoHAB increase by about 22%
- average trigger coincidence rate - areas where the fraction of wildfires that triggered cyanoHAB events divided by the number of cyanoHAB events was high

### Group Discussion #1 
- wildfires occur during anomalous atmospheric conditions
- are the increasing number of smoke days producing stronger warming trends?
- do we need to place additional emphasis on the thermal impact of wildfires?
- heat budget?
- huge open space for thermal modelling 
- statistical matching to find lakes that experience sharp temperature increases following smoke exposure
- how does smoke cover compare to cloud cover (impacts)?
- wavelength specific impacts of smoke vs clouds?
- is smoke having a unique impact on these lakes? 
- can we look at antomony in downwind samples?
- do heavy metals and toxicants fit into the...
- we want a distance vs magnitude + different pathways and see how they stack. multi-pathway disturbance
- are there other nutrient enrichment studies that look at the differential impacts on the delivery of nitrogen...
- in soil science->settling experiment: use that to say "we have this range of PM2.5 pyrometeor firebrand" this is how fast it settles. we can have a settling rate. might be easier to make connections
- we should highlight the particles. could testing ash vs ash.. measuring ambient nutrient concentration to see how microbes are extracting those beyond the water soluble stuff
- beyond the working idea that lakes are the endpoint. aquatic continuum. wildfire signal as it moves from lakes, streams, to the ocean. lakes as a scrubber? are lakes providing a service?