---
layout: page
title: PRICE
menu: state-estimation
hero: 
  image: /assets/img/research/price/bgimg-price.jpg
  description:
    "State estimation in MV distribution networks: experience in the Spanish smart grid project PRICE-GDI"
  buttons:
    - title: Learn more
      url: "#top"
      highlight: true
downloads:
  - title: Whitepaper
    url: /downloads/price-whitepaper.pdf
  - title: CIGRE 2016 Paper
    url: /downloads/price-cigre-c6-110-2016-paper.pdf
  - title: CIGRE 2016 Poster
    url: /downloads/price-cigre-c6-110-2016-poster.pdf
scrollspy:
- name: PRICE Project
  subspies:
  - id: future-smart-grid
    name: Future Smart Grid
  - id: project-scope
    name: Project Scope
  - id: motivation
    name: Motivation
- name: Solution
  subspies:
  - id: distribution-load-and-state-estimation-methodology
    name: DLSE Methodology
  - id: test-case
    name: Test Case

---

# PRICE Project
{:id="top"}

## Future Smart Grid

Traditionally, MV distribution networks are characterized to be passive systems, where the power flows from the primary substations to the final users, with a low number of available on-line measurements mainly located at the head of MV feeders. In spite of this lack of on-line information, the operation of the MV distribution system is possible mainly because of the radial topology of the feeders and their passive nature. This traditional approach, however, is steadily changing to the near future smart grid. This is because the deployment of some key technologies such as the advanced metering infrastructure (AMI), the distributed generation (DG) and the electric vehicle (EV) among others. As a result, the operation of the MV distribution system may not rely on the same traditional principles. Any new technological solution, however, has to be developed and tested in pilot projects as a previous step to their deployment in the field.

## Project Scope

Taking this in mind, PRICE-GDI is a Spanish pilot project, financed by the Ministry of Economy and Competitiveness under the INNPACTO Program with the aim of analysing different technologies enabling the massive integration of DG in MV distribution system. The objective of the project is to gather different technologies for exploring the benefits that the coordinated operation of distributed generation (DGs) may bring to the distribution system as can be seen in Figure 1. The key technologies that have been explored in this project are DGs, MV and LV STATCOMs, bidirectional Remote Units (RUs) associated to DG or STATCOMS and an energy dispatch center with advanced functionalities. 

<div class="text-center">
  <figure class="figure">
    <img src="/assets/img/research/price/price-technologies.png" class="figure-img img-fluid rounded">
    <figcaption class="figure-caption text-right">Figure 1. Main technologies deployed in the pilot project PRICE-GDI.</figcaption>
  </figure>
</div>

Undoubtedly, the proposed PRICE-GDI Dispatch with advanced functionalities, including state estimation of MV feeders and volt/var control, is a necessary technology for the operation of this future MV distribution system.

## Motivation

State estimators for distribution systems must tackle with issues specifically related to this type of networks such as:

* the large proportion of injections in the measurement set, 
* long and short lines coming to the same bus, 
* presence of current flow measurements to the detriment of power flows and
* high R/X ratios. 

But the main hindrance specifically associated to MV systems is the lack of appropriate and well-distributed measurements. As a matter of fact, MV systems are usually operated radially by feeders that extend from substations to secondary distribution transformers, on line measurements being limited in most cases to the main HV/MV substations. Although there is a growing tendency to improve the observability of the system by installing new measurement points, for many distribution companies the still only on-line information available is that acquired at the feeder heads: current and/or active/reactive powers as well as the voltage magnitude on the MV busbars. 

This lack of on-line information causes a problem of non-observability of the system, so pseudomeasurements at MV/LV transformers have to be added previously to perform the state estimation of the whole MV system. To solve this problem, the distribution system state estimator (DSSE) is usually preceded by a tool for load allocation (LA) that tries to estimate the load of the customers connected to the secondary substations. Based on this limited information, the LA problem for each single feeder has been traditionally performed by resorting to the rated power of the existing DTs. This way of modelling the load demand from DTs has proved to be inefficient.

Previous works within this area can be classified according to how the LA and DSSE algorithms interact:

1. estimation as a conjunction of two separate problems LA and DSSE which are solve sequentially.
2. estimation by solving the LA and DSSE by feeding each other. 

The algorithm implemented belongs to this second group. 

# Solution

## Distribution Load and State Estimation Methodology

The implemented solution, namely Distribution Load and State Estimation (DLSE) Methodology, is based on two submodules (LA and DSSE) that interacts each other as can be seen in Figure 2.

<div class="text-center">
  <figure class="figure">
    <img src="/assets/img/research/price/price-methodology.png" class="figure-img img-fluid rounded">
    <figcaption class="figure-caption text-right">Figure 2. Distribution Load and State Estimation (DLSE) methodology.</figcaption>
  </figure>
</div>

LA and DSSE blocks are solved by means of the reciprocal feeding of information in an optimal and efficient way until convergence is reached. The LA methodology solves the initial problem of non-observability by estimating loads demanded from DTs or consumption buses from on-line measurements at the feeder head and other additional information. These header measurements include total load demand plus power losses, so the LA methodology also allocates losses among consumers. DSSE uses these load estimations at DTs, and employs other available measurements along the analysed feeder if there were, in order to compute the best state that matches all these real and estimated measurements. After solving the DSSE problem, active and reactive power losses can be computed. These quantities are of interest for improvement of the LA, since power at the feeder head can be decreased by losses, thereby resulting in new total active and reactive powers better fitted to the total load demand. A second LA execution would result in further improved load estimations and the subsequent SE solution would estimate a new improved state. This feedback between the two applications would continue until convergence was reached (the difference in power losses between two iterations must be lower than a specified threshold).

The complete closed-loop DLSE methodology, which has been validated previously by performing numerous rigorous tests on typical distribution systems under different conditions, has been doubly optimized from a computational point of view by adopting the following new improvements:

* Since the output of each application (LA and DSSE) depends on the other, an exact solution from each application makes no sense. Instead, a single iteration for the LA and SE applications independently should be sufficient, and the convergence of the whole procedure is guaranteed by the feedback between both applications. This simplification speeds up the whole procedure without losing accuracy.
* The LA problem that is formulated as an optimization problem is simplified by an approximated linear solution in an effort to speed up the final whole solution. Once again the accuracy of the final solution is not reduced by this simplification.

## Test Case

### Distribution Network

The application considers the whole distribution network within the regional area known as Corredordel Henares comprising 9 HV/MV substations, 131 MV lines, 2.228 secondary MV/LV substations, 170.729 clients and a total installed power of 1.126 MW. Here, it is included the results of only one MV distribution feeder, shown in Figure 4, which has been intensively analysed to assess the benefits of the proposed DLSE methodology. This MV distribution feeder (20 kV of nominal voltage) is composed of a 46 secondary MV/LV substations, an installed power of 40.7 MW, contracted power of 26.09 MW and total length of 12.57 km.

<div class="text-center">
  <figure class="figure">
    <img src="/assets/img/research/price/price-case-grid.png" class="figure-img img-fluid rounded">
    <figcaption class="figure-caption text-right">Figure 4. One-line diagram of the distribution feeder used in the test cases.</figcaption>
  </figure>
</div>

Within this feeder the following measurements are available:

* Voltage, current, active and reactive powers at the MV feeder head.
* Voltage, current, active and reactive powers in 12 MV/LV secondary substations. These measurement points have been marked up with a blue square in Figure 4.

### Computation of the DLCs

The Daily Load Curve (DLCs) used in the algorithm have been computed by applying a clustering algorithm proposed. For this purpose, the hourly energy consumption of the all the clients which are connected to the analysed feeder during six months have been used as input data of the algorithm. Figure 5 represents the DLCs related to domestic and service loads that have been used in this work. Note that only two DLCs are required to represent residential clients while in the case of industrial customers four DLCs have been used. This issue is basically due to the fact that residential and service clients are more homogenous between them being possible to represent them with a lower number of DLCs.

<div class="text-center">
  <figure class="figure">
    <img src="/assets/img/research/price/price-case-dlcs.png" class="figure-img img-fluid rounded">
    <figcaption class="figure-caption text-right">Figure 5. Residential and service DLCs.</figcaption>
  </figure>
</div>

### Main results

This section presents some of the results obtained by the application during the 18th of April 2015. Figure 6 shows the measurements of active and reactive power flows at MV feeder head during this day. Note that the demand scenario is quite low during this 24 hours period. As a result, the reactive power is negative due to the capacitive behavior of the underground cables and the bus voltages are high as can be seen in Figure 7. The voltage profiles corresponding to the feeder head and the farthest node from the substation have been highlighted to stress that the remaining voltages measurements are within this range. In addition,Figure 8 shows the active power flows measurements which have been acquired in the different measurement points along the distribution system. 

<div class="text-center">
  <figure class="figure">
    <img src="/assets/img/research/price/price-case-results-1.png" class="figure-img img-fluid rounded">
    <figcaption class="figure-caption text-right">Figure 6. Active and reactive power flows at MV feeder head.</figcaption>
  </figure>
</div>

<div class="text-center">
  <figure class="figure">
    <img src="/assets/img/research/price/price-case-results-2.png" class="figure-img img-fluid rounded">
    <figcaption class="figure-caption text-right">Figure 7. Voltage measurements at MV feeder.</figcaption>
  </figure>
</div>

<div class="text-center">
  <figure class="figure">
    <img src="/assets/img/research/price/price-case-results-3.png" class="figure-img img-fluid rounded">
    <figcaption class="figure-caption text-right">Figure 8. Measurements of active power flows.</figcaption>
  </figure>
</div>

All this information constitutes the on-line measurements to the DLSE algorithm which has to be completed by the pseudomeasurements of the LA algorithm in order to obtain an observable system. With this regard, as previously stated, it is possible to apply different strategies. On the one hand, it is possible to perform the LA procedure in a classical basis using the information of contracted power of each DT (LA-CP). On the other hand, it is possible to take advantage of the information provided by the previously computed DLCs (LA-DLC). In order to highlight the benefits of the proposed LA-DLC the estimation results of three different DTs depicted in the following table are analyzed. Note that the selected DTs are of different nature. DT43 and DT4 are mainly composed of residential and industrial loads respectively while DT34 has a mix of service and residential clients.

| DT      | Clients | Contracted | Industrial | Services | Residential |
| Name    | #       | power (kW) | (%)        | (%)      | (%)         |
|:--------|:-------:|:-------:   |:-------:   |:-------: |:-------:    |
| DT 43   | 170     | 940.95     | 0.00       | 10.95    | 89.05       |
| DT 34   | 181     | 1228.61    | 5.65       | 38.40    | 55.95       |
| DT 4    | 1       | 180.00     | 100.00     | 0.00     | 0.00        |
{:class="table table-sm table-responsive"}

Figure 9 to Figure 11 show the estimated active power demand by using the classical LA-CP and the proposed LA-DLC procedure. Note that all the estimated active power demands using the LA-CP methodology follow the active power curve of the nearest upstream measurement, which is not usually the case as different consumption patterns exist depending on the type of clients connected to the DT. With this regard, note that the estimated active power by the LA-DLC methodology during some periods does not follow this curve because uses the information provided by the DLCs.

<div class="text-center">
  <figure class="figure">
    <img src="/assets/img/research/price/price-case-results-4.png" class="figure-img img-fluid rounded">
    <figcaption class="figure-caption text-right">Figure 9. Estimation of the active power demand on DT43.</figcaption>
  </figure>
</div>

<div class="text-center">
  <figure class="figure">
    <img src="/assets/img/research/price/price-case-results-5.png" class="figure-img img-fluid rounded">
    <figcaption class="figure-caption text-right">Figure 10. Estimation of the active power demand on DT34.</figcaption>
  </figure>
</div>

<div class="text-center">
  <figure class="figure">
    <img src="/assets/img/research/price/price-case-results-6.png" class="figure-img img-fluid rounded">
    <figcaption class="figure-caption text-right">Figure 11. Estimation of the active power demand on DT4.</figcaption>
  </figure>
</div>

Finally, Figure 12 shows the relative error between the estimated and the actual active power demanded by DT43. The actual active power demand has been obtained afterwards using the measurement provided by the data concentrator installed in the distribution center. Again, this result reveals the effectiveness of using the methodology based on DLCs as its associated error is quite reduced.

<div class="text-center">
  <figure class="figure">
    <img src="/assets/img/research/price/price-case-results-7.png" class="figure-img img-fluid rounded">
    <figcaption class="figure-caption text-right">Figure 12. Relative error in the estimation of active power for DT43.</figcaption>
  </figure>
</div>

# Conclusions

The objective of this pilot project has been to develop a set of key technologies enabling the massive integration of renewable generation in distribution systems. Undoubtedly, dispatch centres involving advanced algorithm such as distribution state estimators and volt/var controllers are necessary for this challenge. This project has analysed the implementation of a state estimator taken into account all the specific characteristics of the distribution systems and, mainly, their reduced number of on-line measurements. For this reason, a recent novel LA algorithm has been implemented to provide a number of pseudomeasurements to create an observable system. With this regard, it has been shown the advantages that the use of previously computed DLCs may bring compared to classical techniques based on contracted or rated power of DTs.

# Acknowledgment

This work has been financially supported by the Spanish Ministry of Economy and Competitiveness under projects PRICE-GDI (IPT-2011-1501-9) and AllToGather (ENE2014-54115-R) partially granted by FEDER fonds.
