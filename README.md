# README for the Model of the Paper

Fleidervish IA, Lasser-Ross N, Gutnick MJ, Ross WN (2010) Na+ imaging reveals little difference in action potential-evoked Na+ influx between axon and soma. *Nat Neurosci* 13:852-60

These NEURON model files were contributed by Ilya Fleidervish. The NEURON simulator is available for free from [http://www.neuron.yale.edu](http://www.neuron.yale.edu). The number of sections and dt has been somewhat reduced from the published ones to speed up the simulations. Use of variable time step has also been added since publication. Unclick variable time step for fixed if desired.

## To run the model:

Either autolaunch from ModelDB (after NEURON is installed) and skip to step 4 below or

### Under Windows

1. Run `mknrndll` and select `MechanismsVer7.1` folder to make the dll.
2. Run `nrngui`, then under File -> working dir: Move to the (working) `MechanismsVer7.1` directory to load `nrnmech.dll`.
3. Load one of the session files in the top-level folder.
4. Set [Na\+]i = 4 mmol/l, [Na\+]o = 151 mmol/l (e.g. go Tools-Distributed Mechanisms-Viewers-Mechanisms (global)-na_ion).
5. Set EK = -85 mV (e.g. go Tools-Distributed Mechanisms-Managers-Homogenous Spec and select MechType-k_ion).
6. Push Init & Run to start the simulation.

### Under Linux

1. Compile the mod files with  
   `nrnivmodl MechanismsVer7.1`
2. Load one of the session files either by choosing one after starting  
   `nrngui mosinit.hoc`  
   or starting with one of them directly, e.g.  
   `nrngui Fig3A.ses`
3. Follow the Windows instructions above from step 4.

### Under Mac OS X

1. Drag and drop the `MechanismsVer7.1` file onto the `mknrndll` icon.
2. Drag and drop the `mosinit.hoc` file onto the `nrngui` icon.
3. Follow the Windows instructions above from step 4.

---

## Notes about the figures:

### Fig. 3A

A simplified compartmental model that encompasses the fundamental morphological features of a layer 5 pyramidal neuron. In the model, the first 50 µm of the axonal length are assumed to be uncovered by the myelin sheath and to possess a uniform Na+ channel density about threefold higher than that of the soma. The subsequent, myelinated segment possesses no Na+ channels. In addition to Hodgkin-Huxley type Na+ and K+ conductances, the model incorporates longitudinal diffusion of Na+ ions between neighboring compartments with a diffusion coefficient of 0.6 µm²/ms; no mechanism for Na+ extrusion is included. Thus, the spatio-temporal patterns of the simulated [Na\+]i transients solely reflects transmembrane influx into the 'active' compartments that possess Na+ channels (soma and AIS) and Na+ diffusion into compartments that either possess no Na+ channels (myelinated segments) or are large sinks because they have a relatively small surface-to-volume ratio (soma). The model closely mimicks experimentally observed changes in SBFI fluorescence during a single action potential.

### Fig. 4B 10 APs and 100 APs

Na+ transients in models with different process-to-soma ratios of Na+ channel density. When Na+ channel density in the process is set equal to that in the soma (default value, 250 pS/µm²), during the AP trains [Na\+]i in the process rises more significantly because of its higher surface-to-volume ratio. If we will keep somatic Na+ channel density constant and vary Na+ channel density in the process (AIS hh_Cs_scaled in Biophysics menu of the CellBuilder), we can find out that the basal dendrite Na+ channel density has to be 0.1-0.3-fold larger than the somatic density and the AIS density has to be one- to threefold larger than the somatic density to match the experimentally determined signals.

### Fig. 6B

Simulated changes in [Na\+]i elicited by a single action potential plotted against distance from the axon hillock. Because the nodes are small, Na+ ions diffuse laterally almost as quickly as they enter across the nodal membrane. Simulation shows that diffusion-mediated [Na\+]i equilibration between the nodal and internodal volumes should be nearly complete in milliseconds and that more than 90% of Na+ ions that enter a 1-µm-long node were already in the internodal region within 10 ms of the peak of the action potential. In contrast, 10 ms after an action potential in the 48-µm-long AIS, dissipation of the Na+ gradient was minimal. Default values for Na+ channel density: AIS gnabar_hh_Cs_scaled = 800 pS/µm², node gnabar_hh_Cs_scaled = 1200 pS/µm². The latter value could be changed to 1600 pS/µm² and to 8000 pS/µm² to obtain the model of panel C, right.

---

2025-06-20: Converted README to Markdown.