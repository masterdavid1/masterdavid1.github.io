---
layout: article
titles: 'Projects & Presentation'
---


## Project

1. [SDR Receiver](#sdr-receiver)
2. [GaN based energy storage system and charger solution (Capstone project)](#gan-capstone)
3. [ESP Solution Localized automatic lighting solution](#esp-lighting)

### <span id="sdr-receiver">Radio Receiver end for a Flexible Radio Transceiver (FLRTRX)</span>

This project was conducted in ECE295 as a hardware design project for the purpose of implementing the front-end of the flexible radio transceiver, which is divided into 5 subsystems. As team leader, I managed to keep track of progress and build up the team spirit. I practiced exemplary oral and written communication skills as well professionalism through meetings with the project manager and teaching assistant and documenting all testing and meeting minutes.

Our group's subsystem is subsystem A: RX Filter, Limiter, and Mixer. This subsystem filters the signal received by the antenna to remove out-of-band signals. After filtering, the signal must be downconverted to the intermediate frequency and filtered. The downconversion requires use of the LO signal at frequency fLO to bring an RF signal of known frequency down to the baseband frequency range of Subsystem B. The signal is filtered to remove extraneous mixer products, and passed onto Subsystem B, which acts on the downconverted signal.

![](/assets/projects/p1.png)

### Design

Perhaps the first thing to do before putting theory into practice is to divide and conquer the subsystem into smaller blocks and identify the electrical and mechanical interface requirements. Multisim is used here to simulate the chosen topology and element parameters arrived from hand calculations. A detailed design procedure and rational can be accessed from OP1.pptx

<iframe src="/assets/pdfs/Project1-OP1.pdf" width="100%" height="800px" style="border: none;">
  <p>Your browser does not support PDFs. <a href="/assets/pdfs/Project1-OP1.pdf">Download the PDF</a> instead.</p>
</iframe>


### Prototype

This is to ensure that the physical circuit meets our requirements and aligns with the simulation results. Using the breadboard, the limiter, low-pass filter, mixer, high-pass filter and amplifier are checked to ensure the functionality of the circuit.

![](/assets/projects/p2.png)

### Assembly

Altium Designer is used here to first create the 3d component libraries and then layout the 2-layer board. Hand soldering and refill oven is used to solder the surface mount and through hole components. Flux is also applied to reduce oxidation layer.

![](/assets/projects/p3.png)

![](/assets/projects/p4.png)

### Testing

Python test scripts are provided for modification in order to sweep the parameters to configure the instruments on the test bench to verify our subsystem, and then it is compared to a reference solution. Our implementation of the subsystem produced better performance compared to the given solution!

![](/assets/projects/p5.png)

For Assembly & testing, details can be found in final Presentation document

![](/assets/projects/p6.png)

<iframe src="/assets/pdfs/Project1-SDRReceiver.pdf" width="100%" height="800px" style="border: none;">
  <p>Your browser does not support PDFs. <a href="/assets/pdfs/Project1-SDRReceiver.pdf">Download the PDF</a> instead.</p>
</iframe>

### <span id="gan-capstone">Solar-powered electronics charger using Gallium Nitride (GaN) based power converter</span>

Research and Ongoing project Status can be monitored on our website [https://ece496team2025120.com](https://ece496team2025120.com)

#### Motivation

As an inexhaustible clean energy source, solar energy has long been favoured due to its remarkable characteristics of being clean and pollution-free, economical and affordable, as well as environmentally friendly and sustainable. However, solar output fluctuates with weather conditions, seasonal changes (such as shading from clouds and temperature variations), and the time of day (due to the angle of incidence). These fluctuations can reduce overall conversion efficiency, especially with traditional silicon-based power converters, which introduce significant energy losses. To address these challenges, our project explores the use of GaN-based power electronics, which provide higher efficiency, faster switching speeds, and lower losses compared to silicon devices.

#### Goal

To design, build, and test a solar-powered charging system using a GaN-based DC-DC converter that delivers stable, efficient power for an electronic device.

#### Brief Description

The project involves designing a DC-DC power converter using GaN switches to minimize losses and for faster switching than traditional silicon switches. The input will be solar energy, with the converter scaling the voltage as required for storage, or for charging a device, depending on the mode of operation. The design will also require Maximum Power Point Tracking (MPPT) as is generally required in applications of solar energy, to maximize performance according to varying solar conditions.

#### Anticipated Outcome

A fully functional GaN-based DC-DC converter prototype capable of harnessing solar energy to charge a device, with improved efficiency, stability and in a smaller form factor than traditional silicon designs.

<iframe src="/assets/pdfs/Project2-Capstone.pdf" width="100%" height="800px" style="border: none;">
  <p>Your browser does not support PDFs. <a href="/assets/pdfs/Project2-Capstone.pdf">Download the PDF</a> instead.</p>
</iframe>

### <span id="esp-lighting">Engineering Strategies & Project: Address Bird Mortality Caused by Light Pollution</span>

In this group project, I acted as the contact person and design engineer for the team. I connected with the client throughout the length of this project and hosted and spoke on progress meetings and explained final deliverables. Many tools, such as Gantt chart, team charter, cost-benefit analysis, are utilized to facilitate team organization and efficiency. CAD tools like the V-Ray Lighting Analysis is used to simulate the proposed solution's effectiveness in order to present to the client.

![](/assets/projects/p7.png)

The project info can also be found on the client's website https://www.sayeh.ca/research/esp2021/

<iframe src="/assets/pdfs/Project3-Lighting.pdf" width="100%" height="800px" style="border: none;">
  <p>Your browser does not support PDFs. <a href="/assets/pdfs/Project3-Lighting.pdf">Download the PDF</a> instead.</p>
</iframe>
