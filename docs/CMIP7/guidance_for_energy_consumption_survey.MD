---
Layout: default 
title: Metrics to quantify performance, energy use and carbon footprint of CMIP7 simulations 
---

# Guidance for Modelling Centres 

## 1. Background 
Climate simulations are becoming increasingly complex, with each CMIP phase introducing more sophisticated models, a greater number of experiments, and larger ensembles, leading to a continuous rise in computational requirements. Efforts to systematically quantify the computational cost, energy use, and environmental impact of CMIP activities have been limited. The [Energy Consumtion and Carbon Footprint Task Team](https://wcrp-cmip.org/cmip7-task-teams/energy-consumption/) was established to address this gap by measuring and reporting these aspects for the upcoming CMIP7 phase.

[The Computational Performance for Model Intercomparison Project (CPMIP)](https://gmd.copernicus.org/articles/10/19/2017/) defines a standardised set of metrics for evaluating ESMs and their execution on HPC platforms. CPMIP metrics relate to runtime performance (e.g., throughput, computational cost, coupling, I/O) for a given model configuration (e.g., resolution, complexity, parallelisation). 

All modelling centres participating in CMIP7 are asked to provide these metrics for the experiments they are running for the CMIP7 Assessment Fast Track and community MIPs, and the energy consumption to help assess the carbon footprint. These metrics are divided into Tiers reflecting collection effort and analytical value: 

-	**Tier 1** metrics are mandatory and contain the minimum information required to assess the energy consumption, computational cost, and carbon footprint of the experiments.

-	**Tier 2** metrics are strongly recommended and provide additional information to analyse and interpret Tier 1 results, including basic model configuration and performance indicators.

-	**Tier 3** metrics are optional but encouraged, offering a deeper understanding of model and system behaviour through more detailed   performance indicators which help to identify bottlenecks and improve cross-platform comparability.



### 1.1 Targeted CMIP7 simulatons 
The aim is to collect metrics across three categories of simulations:

- **Production simulations** Runs that generated datasets for scientific analysis, directly linked to one CMIP7 experiment, whether they were published or not on ESGF. 

- **Tuning simulations** Runs performed during the calibration and development of the model, not meant for publication.

- **Discarded simulations** Runs that were interrupted, failed, or ultimately not used due to bugs.


## 2. Collection, Timeline and Dissemintation of the metrics

### 2.1 Collection 
Access to an online spreadsheet will be provided to all modelling institutes. The spreadsheet will request the values of the metrics defined in the current document. The information collected will be maintained by Barcelona Supercomputing Centre and—depending on the agreed data-sharing policy—made available to participating modelling institutes. This shared dataset will serve as the foundation for subsequent analysis, intercomparison and reporting activities. **Complete guidelines are available on [zenodo](https://zenodo.org/records/17464967)**. 

### 2.2 Timeline 
Initial collection phase covering CMIP7 AFT simulations. Confirmation by the modelling centres that they can access the spreadsheet and understand the information provided, by January 2026.

First round of data collection by September 2026, aiming to support downstream activities for the IPCC AR7 process targeting historical and scenario (MIP) data.

Second phase extends to the broader CMIP7 MIPs, with timelines to be defined once experiments are scheduled. We expect the involvement of modelling institutes to be a continuous process, throughout the full CMIP7 life cycle.

### 2.3 Dissemination 
The results derived from this activity will be disseminated through a peer-reviewed publication and public visualisations and summaries of key statistics, similar to ESGF Data Statistics (to be decided). 


## 3. The metrics 

### 3.1 General Information (Mandatory). 
- Modelling group name or contact name.
- Location (city and country).
- HPC platform name.
- [Power Usage Effectiveness](https://edgebuildings.com/wp-content/uploads/2024/03/240313-EDGE-Certification-for-Data-Centers-V4.pdf?lang=es) (PUE) metric describing the HPC's energy efficiency 
- Emission Factor for the energy used by the computing centre, the carbon dioxide emissions produced per unit of a specific energy source (kgCO2/MWh).

**Encouraged metric**
- Energy Mix of the HPC. Site-specific energy mix, expressed as the percentage share of primary energy sources (e.g., coal, natural gas, nuclear, hydro, wind, solar). Recommend using averaged values over the most recent full-calendar year 

### 3.2 Tier 1 (Mandatory) 
- Experiment Type (production, tuning or discarded run)
- For producton runs indicate the accpeted experiment name from the [CMIP7 Data Request](https://airtable.com/appOcSa4gXyzHThmm/shrkayKObes58Zu45/tbloQs9ZQUxX1Mj2y/viwgifLeWmoLJJ59m).
- Number of simulated years. 
- Number of core-hours consumed by the experiment, i.e. the number of cores used to run the model multiplied by the elapsed time of the run. 
- Data output in GB. Volume of data stored to HPC disk even if temporary and not stored afterwards. 
- Energy consumed by the experiment job in megajoules. Recommend using hardware counters (e.g., Intel RAPL or IPMI via Baseboard Management Controller (BMC) for CPUs, NVIDIA’s NVML library or ROCm-SMI for GPUs). Report dynamic energy (energy consumed solely by the application workload) and total energy (energy consumed by the application plus idle energy). 

### 3.3 Tier 2 (Encouraged) 
- SYPD (Simulated Years Per Day). 
- QSYPD (Queue SYPD) Simulated years per day including both queue time and run time. 
- RSYPD (Real SYPD) Simulated years per day including queue time, run time, system interruptions and workflow errors. 
- Parrallelisation, Number of CPU cores used for the simulation (unit: cores). Include the number of GPUs when applicable (e.g., 1000 cores + 20 GPUs).
- Data Output Intensity, the data volume produced per compute hour (GB/core-hour), including all output generated during the simulation e.g. scientifically valuable data, restarts, logs, temporary files, etc. 

        *Data Output Intensity = Output Volume (GB) / Core Hours*

- Number of 3D grid points used in the model integrations. 

### 3.4 Tier 3 (Optional) 
- Complexity, the number of prognostic variables. For multi-component models complexity is the sum of the prognostic variables across all components, and if the value is not directly known for a component or model, it can be approximated using the restart file size and resolution: 

       *Complexity = Sc / Gc / 8* 

       Where *Sc* = restart file size (bytes), *Gc* = number of grid points and *8* = bytes per variable assuming double precision. 

- Data Output Cost, a ratio of the performance overhead due to the I/O. The measurement approach will depend on whether synchronous I/O or asynchronous I/O is used. 

      For synchronous I/O:  *Data Output Cost = 1 - (CHSY_without_IO / CHSY)* 

       Where CHSY = Core Hours per Simulated Year 

      For asynchronous I/O: *Data Output Cost = P~io~ / P 

       Where *P* = parrallelisation of I/O servers and *P~io~* = number of I/O processes
              
- 
- 
- 

