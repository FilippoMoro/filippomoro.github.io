---
title: 'The Memory Technology Landscape'
date: 2024-11-14
permalink: /posts/2024/11/The Memory Technology Landscape/
tags:
  - Memory
  - SRAM
  - RRAM
  - PCM
  - MRAM
---

Memory technology has become the major battleground for integrated chip's innovation. Our chips' integrated memory is ever growing and now occupies a considerable portion of commercial silicon dies. While Static-Random-Access-Memory technology dominates the on-chip memory market, an article pointed out that SRAM's scaling - fueled so far by Moore's Law - is hitting a wall. TSMC's 3nm node only provides a minor improvement (about 5%) in SRAM bitcell density compared to the 5nm node. So what is the future for on-chip memory?. Here I explore the current on-chip memory to extrapolate what the future might look like. More importantly, this article links to a [spreadsheet](https://docs.google.com/spreadsheets/d/1qB0eTERsOAq3VRLizeE9IMj2wXXSUNgyxcXAxigXpuM/edit?gid=0#gid=0) where I gather data on all the memory devices featured in the plots. You can access this spreadsheet freely, and will find all the information about the given memory devices as well as a reference to the scientific paper they were featured in.

======

### Memory is all you need
Memory technology has become the major battleground for integrated chip's innovation. Our chips' integrated memory is ever growing and now occupies a considerable portion of commercial silicon dies. While Static-Random-Access-Memory technology dominates the on-chip memory market, an article pointed out that SRAM's scaling - fueled so far by Moore's Law - is hitting a wall [1]. TSMC's 3nm node only provides a minor improvement (about 5%) in SRAM bitcell density compared to the 5nm node. Then what is the future for on-chip memory? Some suggest that the shift from FinFET to Nanosheet transistor technology will propell the continuation of CMOS - and SRAM as well - scaling. Others highlight that alternative solutions exist: several emerging memory cells have been developed with the aim of going beyond standard CMOS and exploit different physical phenomena to store information in memory cells. Among such innovative devices, Resistive-RAM (RRAMs) [2], Phase-Change-Memory (PCM) [3], Magnetic-RAM (MRAM) [4], Ferroelectric-RAM (FeRAM) [5], 2T-Gain-Cells [6] or eDRAM [7]. Albeit far less mature than SRAM, these devices (except for 2T-Gain-Cells and eDRAM) are non-volatile, thus promising energy efficiency, and can easily be integrated in the Back-End-of-Line (BEOL) of common CMOS processes, thus enabling high integration memory density.

This article offers a birdseye view of the memory technology landscape, analysing the development SRAM until the most recent nodes, and assessing the performance of the alternative emerging memory devices. Importantly, this article is inspired by this excellent review [paper](https://ieeexplore.ieee.org/abstract/document/10488872) from Prof. Shimeng Yu. I build on top of this article finding the relevant sources in the literature and providing my own opinions on the future of memory technology. You can access all the information contained in this article from this [spreadsheet](https://docs.google.com/spreadsheets/d/1qB0eTERsOAq3VRLizeE9IMj2wXXSUNgyxcXAxigXpuM/edit?gid=0#gid=0): it features the scientific references and technical information to a lot of memory devices.

======

### SRAM scaling
Pushed by the advances of transistor technology, SRAM performance improved at an astounding pace over the years. Here we focus on SRAM scaling after the year 2000, showing the impressive rate at which the cell size has shrunk over the years.

<!-- <p align="center">
  <img src="/images/Blog_Memory/SRAM_scaling.png" alt="alt text" width="1200"/>
</p> -->

<style>
  /* Add this style block for custom styling */
  .carousel-container {
    position: relative;
    max-width: 800px; /* Adjust the max-width based on your design */
    margin: auto;
    height: 800px; /* Set the height as needed */
  }

  .carousel-slide {
    display: none;
    position: absolute;
    width: 100%;
  }

  .carousel-slide img {
    width: 100%;
    height: auto;
  }

    .carousel-prev, .carousel-next {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    font-size: 20px; /* Increase the font size for bigger buttons */
    color: #fff;
    /*background-color: #6b3c70; /* Dark purple color */
    border: none;
    padding: 15px; /* Increase padding for bigger buttons */
    cursor: pointer;
    border-radius: 10px; /* Add some border-radius for rounded corners */
  }

  .carousel-prev {
    left: 10px;
  }
  .carousel-next {
    right: 10px;
  }

    /* Add margin to create space after the carousel */
  .space-after-carousel {
    margin-bottom: 30px; /* Adjust the margin as needed */
  }

</style>

Scroll through the 3 figures!
<div id="imageCarousel" class="carousel-container">
  <div class="carousel-container">
    <div class="carousel-slide" style="display: block;">
      <img src="/images/Blog_Memory/SRAM_scaling_general.png" alt="Image 1" width="80%">
       <!-- <div class="caption">Caption for Image 1</div> -->
    </div>
    <div class="carousel-slide" style="display: block;">
      <img src="/images/Blog_Memory/SRAM_scaling_company.png" alt="Image 2" width="80%">
       <!-- <div class="caption">SRAM scaling by company</div> -->
    </div>
       <div class="carousel-slide" style="display: block;">
      <img src="/images/Blog_Memory/SRAM_scaling_transistor.png" alt="Image 3" width="80%">
          <!-- <div class="caption">SRAM scaling by transistor type</div> -->
    </div>
  </div>
  <button class="carousel-prev" onclick="changeSlide(-1)">Previous</button>
  <button class="carousel-next" onclick="changeSlide(+1)">Next</button>
</div>

<script>
  let currentSlide = 1;

  function showSlide(n) {
    const slides = document.getElementsByClassName("carousel-slide");
    if (n > slides.length) { currentSlide = 1; }
    if (n < 1) { currentSlide = slides.length; }

    for (let i = 0; i < slides.length; i++) {
      slides[i].style.display = "none";
    }

    slides[currentSlide - 1].style.display = "block";
  }

  function changeSlide(n) {
    showSlide(currentSlide += n);
  }

  // Show the first slide when the page loads
  document.addEventListener("DOMContentLoaded", function() {
    showSlide(currentSlide);
  });
</script>


This data, again, is reported in the shared [spreadsheet](https://docs.google.com/spreadsheets/d/1qB0eTERsOAq3VRLizeE9IMj2wXXSUNgyxcXAxigXpuM/edit?gid=0#gid=0) and from it we can learn three main messages:
- 1: SRAM bit-cell size has steadily decreased through the years, but it appears to have slowed down lately.
- 2: planar CMOS technology hit a wall in the beginning of the 2010s, where FinFET technology took over, continuing in the scaling trend.
- 3: only three companies are currently participating in the race of SRAM scaling (TSMC, Samsung, Intel).

<!-- It's important to note that in the early 2010's, performance of bulk CMOS was stagnating due to the limited electrostatic control over the channel. The semicoductor industry was quick to react and adopt a novel transistor architecture, the FinFET transitor, capable of a greater control over the channel and thus enable further scaling of feature sizes. More recently, it seems the FinFET has reached its limitations and SRAM size has slowed down. However, the industry has prepared an evolution of the FinFET transistor, the Nano-sheet-FET, which should drive the innovation of CMOS tecnology - and SRAM as well - in the coming years. -->

As technology nodes become more advanced, the investements required to participate in the silicon scaling race grow exponentially. This is why the leading edge of SRAM scaling is carried out by essentially one only company nowadays, TSMC. Samsung follows closely, and Intel seems to be lagging a little behind.

> Will SRAM scaling continue?

It seems like SRAM scaling is becoming harder and harder, and even TSMC flinched when lunching their 3nm node, with the N3B specification only offering a 5% improve over the N5 (5nm) node [1]. 
<!-- Also, notice that supposedly due to yield issues the N3B node has mainly been used by Apple as a customer. TSMC seems to have dismissed N3B due to these issues and moved to a N3X variant, and it's unclear whether this updated node offers any advance in terms of SRAM cell density. -->
<!-- What are the limitations in scaling SRAM?
- **Fin-width**?
- **BEOL limitations**? -->

However, the semiconductor industry still has some tricks up it sleaves, and it's ready to play them all to assure the continuation of SRAM scaling.
- **Nanosheet transistors**: the next generation of transistor promises higher integration density, guaranteeing the continuation of SRAM scaling
- **Backdoor power rails**: an option mainly researhced by Intel.
- **Complementary 3D stacked logics**: a potentially disruptive technology whereby p- and n-mos transistors can be stacked on top of each other, offering clear scaling advantages even compared to ultimate nanosheet transistors.


======

### Alternative emerging memory technology

> Embedded Non Volatile Memory (eNVM)
As advancing technology nodes becomes every more expensive and technically challenging, very few companies can afford to advance the development of CMOS. This leads researches to explore novel memory devices that operate exploiting different physical phenomena. Such class of emerging memories has been talked about a lot, so how does it compare with SRAM? We'll now focus on emergin Non-Volatile-Memory (eNVM), which includes RRAM, MRAM, PCM and FeRAM. (The latter is not mature enough to be compared in the following plots).

<!-- <img src="/images/Blog_Memory/eNVM_scaling.png" alt="alt text" width="800"/> -->
Scroll through the 2 figures!
<div class="carousel-container">
  <div class="carousel">
    <div class="carousel-item">
      <img src="/images/Blog_Memory/eNVM_scaling_general.png" alt="Image 1" width="80%">
       <!-- <div class="caption">Caption for Image 1</div> -->
    </div>
    <div class="carousel-item">
      <img src="/images/Blog_Memory/eNVM_density_general.png" alt="Image 2" width="80%">
       <!-- <div class="caption">SRAM scaling by company</div> -->
    </div>
  </div>
  <button class="carousel-prev" onclick="changeSlide(-1)">Previous</button>
  <button class="carousel-next" onclick="changeSlide(+1)">Next</button>
</div>

<script>
  let currentSlide = 1;

  function showSlide(n) {
    const slides = document.getElementsByClassName("carousel-slide");
    if (n > slides.length) { currentSlide = 1; }
    if (n < 1) { currentSlide = slides.length; }

    for (let i = 0; i < slides.length; i++) {
      slides[i].style.display = "none";
    }

    slides[currentSlide - 1].style.display = "block";
  }

  function changeSlide(n) {
    showSlide(currentSlide += n);
  }

  // Show the first slide when the page loads
  document.addEventListener("DOMContentLoaded", function() {
    showSlide(currentSlide);
  });
</script>

This data, once more, is reported in the shared [spreadsheet](https://docs.google.com/spreadsheets/d/1qB0eTERsOAq3VRLizeE9IMj2wXXSUNgyxcXAxigXpuM/edit?gid=0#gid=0):
- 1: in terms of bit-cell size, eNVM is competitive with SRAM, especially RRAM and PCM.
- 2: however, memory array density highlights that eNVM is for now reserved to lesser technology nodes (typically at 40nm or 28nm, topping at 14nm) and thus eNVM results less memory dense.

For now we have mainly looked at size and density, but there is more to memory. The next figures gives an idea of the Figures of Merits of different memory technology, comparing SRAM (in grey) to eNVM. Note that this figure is obtained by considering the general performance of the differen memory classes, taking inspiration from Table 1 in [8].

<img src="/images/Blog_Memory/Memory_overview.png" alt="alt text" width="550"/>

What do we learn? SRAM and eNVM are apples and oranges. They don't belong to the same class of memory devices, which if famously clustered in the pyramid of memory (refer to Figure 2 in [8]). In particular, the core differences are:
- SRAM is *fast*! eNVM is slower to read and even slower to write.
- SRAM has extremely high Endurance (number of read/write cycles before failure). MRAM also feature high endurance, but RRAM and PCM are very limited in this sense.
- Despite SRAM being the densest so far, RRAM and PCM feature multi-bit per cell. The density gap might close in the future!


<!-- #### Gain Cell (eDRAM) and embedded Flash -->
======

### The future of memory technology

<!-- SRAM is still too good, will stay there for cache L1 and L2 for sure
MRAM as alternative for L3/4
CIM is the battleground for eNVM -> memory density is key, going 3D [9] is the way to truly innovate! -->
(What follows is my personal opinion)

It is hard to predict what the future of memory technology will look like. My opinion is that until transistor scaling will be physically possible and economically viable, industry will keep developing in that direction, bringing benefits to SRAM scaling. Concerning memory applications, it's hard to see SRAM dethroned as L1 and L2 cache memory, where sheer speed is mandatory. There is no other device currently capable to deliver similar read and write speed.

However, transistor scaling will likely hit a point of deminishing returns at some point. Are the alternavie memory devices ready to take over when this happens? Again, it depends on the applications.
- eNVM is *already* in the market, as embedded memory in commercial micro-controllers [9].
- As L3 or L4 cache memory, MRAM might evolve into a serious candidate, especially when its non-volatility can be exploited in low stand-by power contexts.

> Compute-In-Memory
The most intreaguing domain of application for eNVM is certainly Compute-in-Memory (CIM). While SRAM-based CIM is definitely well performing, breaking the 1000Tops/W mark per macro, eNVM-based CIM is also competitive [10]. eNVM features two important characteristics that are still not fully exploited in CIM, especially in low-power applications. While SRAM is speed king and maximally efficient only at peak frequency, eNVM does not consume any static power (in theory!) and it's thus energy efficient even at low frequency, typical use-case in edge applications. Also, RRAM and PCM store multiple bits per cell (typically 3 bits): this aspect is rarely exploited as it makes the peripheral circuit design more complex (need to design a great ADC), but it might give an edge to eNVM in terms of memory density CIM.

But there is an important prospect to account for: 3D-memory integration [11]. Nowadays, 3D integration is reserved to Flash memory, achieving more than 100 levels in the Back-End-of-Line and thus record-breaking memory density [12]. SRAM is very likely not scalable to 3D, as crystalline silicon cannot be deposited in the BEOL to form the 6 transistor required by SRAM. In contrast, eNVM are already BEOL-compatible! So can they scale to 3D? Yes, but it will be complicated. Some early research showed BEOL integration of RRAM and carbon-nanotube selector [13], potentially scalable to multiple 3D layers. This paves the way towards ultra-high density on-chip memory density!


======
Thank for reading! Please don't hesitate to provide feedbacks, you can find my contacts in the landing page of my website (provide links!). 
Also check out the Emerging Intelligent Substrates Lab (EIS), directed by Melika Payvand. It's a cool environment where novel memristive-based architectures and neuromorphic algorithms are codesigned, leading to creative and competitive neuromorphic solutions.

Visit the [EIS Lab Github](https://github.com/EIS-Hub).


=====

### References
[1] David Schorr "IEDM 2022: Did We Just Witness The Death Of SRAM?" WikiChip Fuse (2022)

[2] Wong, H-S. Philip, et al. "Metal–oxide RRAM." Proceedings of the IEEE 100.6 (2012): 1951–1970.

[3] Ielmini, Daniele, et al. "Physical interpretation, modeling and impact on phase change memory (PCM) reliability of resistance drift due to chalcogenide structural relaxation." 2007 IEEE International Electron Devices Meeting. IEEE, 2007.

[4] Na, Taehui, Seung H. Kang, and Seong-Ook Jung. "STT-MRAM sensing: a review." IEEE Transactions on Circuits and Systems II: Express Briefs 68.1 (2020): 12–18.

[5] Mikolajick, Thomas, et al. "FeRAM technology for high density applications." Microelectronics Reliability 41.7 (2001): 947–950.

[6] Liu, Shuhan, et al. "Hybrid 2T nMOS/pMOS Gain Cell Memory with Indium-tin-oxide and Carbon Nanotube MOSFETs for Counteracting Capacitive Coupling." IEEE Electron Device Letters (2023).

[7] Fredeman, Gregory, et al. "A 14 nm 1.1 Mb embedded DRAM macro with 1 ns access." IEEE Journal of Solid-State Circuits 51.1 (2015): 230-239.

[7] Dalgaty, Thomas, et al. "In situ learning using intrinsic memristor variability via Markov chain Monte Carlo sampling." Nature Electronics 4.2 (2021): 151–161.

[8] Mannocci, P., et al. "In-memory computing with emerging memory devices: Status and outlook." APL Machine Learning 1.1 (2023).

[9] STMicroelectronics, announcing a (18nm FD-SOI platform with ePCM)[https://newsroom.st.com/media-center/press-item.html/c3244.html]

[10] Shanbhag, Naresh R., and Saion K. Roy. "Comprehending in-memory computing trends via proper benchmarking." 2022 IEEE Custom Integrated Circuits Conference (CICC). IEEE, 2022.

[11] Vianello, Elisa, and Melika Payvand. "Scaling neuromorphic systems with 3D technologies." Nature Electronics 7.6 (2024): 419-421.

[12] Kim, Bvunarvul, et al. "28.2 A High-Performance 1Tb 3b/Cell 3D-NAND Flash with a 194MB/s Write Throughput on over 300 Layers" 2023 IEEE International Solid-State Circuits Conference (ISSCC). IEEE, 2023.

[13] Srimani, Tathagata, et al. "Foundry monolithic 3D BEOL transistor+ memory stack: Iso-performance and Iso-footprint BEOL carbon nanotube FET+ RRAM vs. FEOL silicon FET+ RRAM." 2023 IEEE Symposium on VLSI Technology and Circuits (VLSI Technology and Circuits). IEEE, 2023.