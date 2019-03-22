---
layout: page
title: MONICA
menu: state-estimation
hero: 
  image: /assets/img/research/monica/bgimg-monica.jpg
  description:
    Real-time control of the distribution grid.
  buttons:
    - title: Learn more
      url: "#top"
      highlight: true
downloads:
  - title: Whitepaper
    url: /downloads/monica-whitepaper.pdf
scrollspy:
  - name: State Estimation for Distribution Networks
    subspies:
    - id: the-new-generation-grid
      name: The New Generation Grid
    - id: state-estimation-vs-load-flow
      name: State Estimation vs Load Flow
  - name: MONICA Project
    subspies:
    - id: project-scope
      name: Project Scope
    - id: results-and-applications
      name: Results and Applications
  - name: PASTORA Project
    subspies:
    - id: summary
      name: Summary

---

# State Estimation for Distribution Networks
{:id="top"}

## The New Generation Grid

Nowadays the number of active elements connected to the distribution network, such as DG, energy storage, EVs or self-producing consumers, is increasing exponentially. Therefore, the use of monitoring and diagnosis tools is crucial in distribution networks. Until a few years ago, the possibility of implementing a state estimator (SE) in LV or MV networks was not considered technically or economically feasible. The deployment of smart grids, in particular the installation of smart-meters and remote controls associated with distribution automation systems, is providing the distribution network with new information sources.

<div class="text-center">
  <figure class="figure">
    <img src="/assets/img/research/monica/SE.png" class="figure-img img-fluid rounded">
    <figcaption class="figure-caption text-center">Figure 1. MONICA project structure </figcaption>
  </figure>
</div>

The main objective of MONICA (Spanish acronym of Advanced Monitoring and Control) project is to develop suitable monitoring and diagnostic tools specifically designed for distribution networks (MV and LV), similar to those that have traditionally existed at higher voltage levels. The core of the monitoring process included in MONICA is a SE tool. Even though the underlying philosophy and objectives are the same as that of transmission-level SE, an ad hoc development has been undertaken owing to the following distinguishing features of MV and LV grids:

* radial structure, 
* high R/X ratios, 
* reduced lengths of LV cables, 
* much lower measurement redundancy 
* need to incorporate more pseudo-measurements, 
* much lower scanning rates and 
* significant unbalance of LV feeders. 

Taking those peculiarities into account, the SE developed for Smartcity comprises two stages:

1. a three-phase, four-wire unbalanced SE is first run for each LV feeder; 
2. then, a single-phase balanced SE is performed on MV feeders. 

## State Estimation vs Load Flow

In an environment in which the number of measurements available increases (smart-meters at LV and MV consumers, sensors at primary and secondary substations), it is essential to use tools that take advantage of all this information. The State Estimation algorithm allows to obtain optimally the state of operation of the network using all the information supplied by the measuring instruments installed in the network. The following table shows the main differences between the SE and the traditional load flow method.

|  | State Estimation | Load Flow |
|:--------|:-------:|:--------:|
| Method   | Statistical   | Deterministic/probabilistic   |
| Number of measurements   | More measurements than states (redundancy)   | Same number of measurements than states   |
| Type and distribution of measurements   | Greater diversity   | Restricted   |
| Characterization of measurements uncertainty   | Possible   | Impossible   |
| Detection of errors in model or measurements   | Possible   | Impossible   |
{:class="table table-responsive table-sm"}

# MONICA Project

## Project Scope

The initial scope of the project covers two MV feeders, with a total of 57 secondary substations and the associated capillary system of LV feeders delivering electricity to over 5,000 customers, each equipped with a smart meter. As described earlier, a whole network of sensors, both at MV and LV levels, has been deployed in the Smartcity project. Figure 2 schematically shows the location and type of sensors for a generic MV feeder with several secondary substations and LV customers. For convenience, the MV/LV transformer is included in the MV SE model.

At the MV level the following measurements are available every 5 minutes:

* Voltage magnitude and active & reactive powers at both the input and output feeder sections of secondary substations.
* Voltage and current magnitudes and active & reactive powers on the MV side of the transformer.
* Voltage magnitude and active & reactive powers consumed by MV customers, if any.
* Voltage magnitude and active & reactive powers injected by DG at this level, if any.

For the LV level, with a fifteen-minute time lapse, the available measurements can be summarized as follows:

* Voltage magnitude, active & reactive powers at the LV side of the transformer.
* Current magnitudes at the head of each LV feeder.
* Voltage magnitude, active & reactive powers provided by the smart meter of every customer connected to the LV feeders.

<div class="text-center">
<figure class="figure">
  <img src="/assets/img/research/monica/unifilar_MT.png" class="figure-img img-fluid rounded" width="80%">
  <figcaption class="figure-caption text-center">Figure 2. Generic scheme of the location of the sensors in a MV feeder with several secondary substations and clients </figcaption>
</figure>
</div>

## Results and Applications

The SE has been satisfactorily tested with both simulated and actual data. It provides the maximum likelihood voltage magnitudes at all buses, the currents and power flows across all feeder sections and the resulting losses. In addition, for LV feeders it allows abnormal or unacceptable system imbalances to be detected. Just as a sample, Figure 3 shows, for each hour on the 20th of August, 2016, the resulting ohmic losses for the set of three phases and the neutral cables fed from the secondary substation No. 307 in Smartcity Malaga. As can be seen, the resulting imbalance is not negligible, which has prompted the utility to undertake corrective actions aimed at more optimally relocating individual customers to achieve a better balance.

<div class="text-center">
<figure class="figure">
  <img src="/assets/img/research/monica/resultados.png" class="figure-img img-fluid rounded">
  <figcaption class="figure-caption text-center">Figure 3. Active power losses per phase and neutral cable for twenty-four scenarios </figcaption>
</figure>
</div>

Based on the results provided by the SE, other diagnostic and corrective tools can be developed, such as:

* var & voltage control, 
* congestion alleviation, 
* automatic feeder reconfiguration, 
* detection of non-technical losses, 
* etc.

One of the most interesting applications of the SE is the possibility of detecting wrong measurements. The following test was carried out with real data from the LV secondary substation 307, Smartcity Malaga:

1.  The SE was executed with measurements received from the consumers and the secondary substation for the same time stamp.
2.  Measurements of two consumers located in the 2865XX PCR (Spanish acronym of point of connection to grid) were modified on purpose to simulate a wrong measurement or a fraudulent connection. 
3.  Figure 4 shows the result of SE (before eliminating wrong measurements). It is observed that the estimate of consumption in the 2865XXX PCR, obtained by the estimator, of 12644 W differs considerably from the introduced measurement of 8100 W.

<div class="text-center">
<figure class="figure">
  <img src="/assets/img/research/monica/esquema_cd_307_1.png" class="figure-img img-fluid rounded" width="80%">
  <figcaption class="figure-caption text-center">Figure 4. Result of the state estimator with simulated error </figcaption>
</figure>
</div>

4.  The SE, under certain conditions, allows to identify this measurement as erroneous and remove it.
5.  Once the bad measurement is eliminated the estimator is re-executed. As can be seen in Figure 5, the SE calculates a consumption in the PCR very close to the real consumption.
{:start="4"}

<div class="text-center">
<figure class="figure">
  <img src="/assets/img/research/monica/esquema_cd_307_2.png" class="figure-img img-fluid rounded" width="80%">
  <figcaption class="figure-caption text-center">Figure 5. Result of the state estimator after eliminating the wrong measurement </figcaption>
</figure>
</div>

# Pastora Project
## Summary

Big data has reached the electrical grid and it is going to change everything. The millions of data offered by smart grids will allow system operators to predict and anticipate potential incidents in order to improve the functioning of the network and the quality of service to clients.

This is the challenge of the PASTORA project, an initiative which we are leading in Malaga, together with a consortium of companies and research organisms. During the 31 months of the project, we are going to apply artificial intelligence techniques to analyse the data obtained from electric meters and sensors installed at different points of the grid. Using an algorithm, we will conduct advanced statistical data processing, allowing us to improve control in real time, as well as preventive maintenance of the distribution grid.

As stated by Susana Carillo Aparicio, Director of the PASTORA project, and Head of Smartcity Málaga Living Lab at Endesa, "the aim of PASTORA is to anticipate any problem which may occur on the grid, based on the knowledge of what is happening on the electric grid".

![malaga smartcity](/assets/img/research/monica/mapa-pastora-malaga-smartcity.jpg){:class="img-fluid rounded"}

### Smartcity Málaga Living Lab, home to innovation

PASTORA, which stands for Preventive Analysis of Smart Grids with Real Time Operation and Renewable Assets Integration, is run at the Smartcity Málaga Living Lab, an ecosystem for innovation which brings together all of the technologies of smart grids in a real environment. It was also the home of the MONICA project, which also focused on automating the electric grid, yielding conclusions which have served as a starting point to progress in the predictive maintenance of the distribution grid.

Thanks to the millions of data the new smart grid offers us, we are going to develop predictive models to anticipate how the network will behave and, in that way, improve their functioning. This will facilitate the integration of renewable energies and electric vehicles, and it will also allow to anticipate where incidents may occur, to optimise grid maintenance and investments.

This project — a new step in the digitalisation of the distribution grid — is being run with a consortium which includes Ayesa Advanced Technologies, Ormazabal Media Tensión, Ingelectus Innovative Electrical Solutions, AICIA (a research association linked to the University of Seville) and the University of Granada. It manages a budget of 2.8 million euros, partially funded by CDTI, the Centre for the Development of Industrial Technology, supported by the Ministry of Science, Innovation and Universities and co-financed by the European Union through ERDF, via the Multi-regional Operational Programme for Spain 2014-2020.

With innovation projects like PASTORA, we work to progress in the digitalisation of the distribution grid by integrating artificial intelligence and big data techniques into the energy sector to improve our services.

# CONCLUSIONS
The SE is a powerful tool that can be used with the following functionalities:
* Identification / detection of erroneous measurements. 
* Improve energy balances, allowing better detection of non-technical losses.
* Disaggregation of total technical and non-technical losses.
* Evaluate the congestions 
* Identify under or over voltages of the network.
* Analyze the unbalances. 
* Optimize network planning.




![funding](https://www.endesa.com/content/dam/enel-es/home/proyectos/imagenes/logos1_MONICA.png)
{:class="text-center"}
