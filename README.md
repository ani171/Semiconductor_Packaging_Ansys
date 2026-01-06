# Semiconductor-Packaging

## Module 1
#### Why is semiconductor packaging needed?
- When dies/chips come out of the wafer, they are made in a protected environment, but ICs are exposed to the real world. So packaging:
  1. Enables the die to connect to other dies
  2. Protection of semiconductor devices (Corrosion, moisture, and physical damage)
<br> </br>
#### IC Manufacturing Flow:
1. Design – Circuit & layout design
2. Wafer Process – Fabrication of ICs on wafers
3. Package & Test
    - Wafer Test – Test individual dies on wafer
    - Package – Encapsulation of dies
    - Package Test – Test packaged ICs
4. Assembly – Final integration into products

#### Types of Manufacturers:

- IDM (Integrated Device Manufacturer) – Handles design, fabrication, packaging, and testing in-house
- OSAT (Outsourced Semiconductor Assembly & Test) – Specializes in packaging and testing only
- Fabless – Only designs ICs; fabrication outsourced
- Foundry – Only fabricates ICs for other companies

#### Silicon lifecycle
<img width="541" height="541" alt="image" src="https://github.com/user-attachments/assets/7fcb828b-dfbd-4ff1-b2e8-97e7ae28cfdd" />

#### Choosing the right package
1. Application – Memory/logic, etc.; bandwidth decides speed and number of interconnects
2. Thermal Dissipation – Chip power and mounting material decide package type; high-temperature chips can’t use laminate organic substrates
3. Form Factor – Package thickness and footprint constraints
4. Reliability – Performance over time and operating conditions
5. Durability – Mechanical and environmental robustness
6. Cost 

<img width="1263" height="483" alt="image" src="https://github.com/user-attachments/assets/2fed2779-734c-459b-931e-af390548b3a5" />

 #### Packaging classification
 1. Through hole mounting - TO, DIP, PGA
 2. Surface mount technology
  - QFN (Quad Flat No-Lead) – Leadless package, good thermal and electrical performance, small footprint
  - QFP (Quad Flat Package) – Leads on all sides, easy to inspect and solder
  - PBGA (Plastic Ball Grid Array) – Solder balls underneath, high I/O density, better signal integrity
  - LGA (Land Grid Array) – Flat lands instead of balls, used where socketing or fine pitch is needed
  - CSP (Chip Scale Package) – Package size ≈ die size, similar to BGA, very compact
  - PoP (Package on Package) – Multiple packages stacked vertically, saves board space, used in mobiles generally
  - MCM (Multi-Chip Module) – Multiple dies integrated in one package, improves performance and integration

- Options for carrier: Leadframe, laminate, plastic, ceramic(for high temperature), organic RDL, silicon, glass
- Options for interconnections - Wirebond(Stitch type), Bump/Solder

#### Anatomy of packages
- Leadframe: a thin metal frame that holds the silicon die and connects it to the outside world
<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/6e1b71fe-7428-4ba8-b433-f2156fd5dad2" /> <br/>
- Laminate: organic substrate with coarse metal routing and ground planes, used to interconnect die bumps to BGA balls and the PCB <br/>
- Advanced package substrates: 
    1. 2D Layer
         - Two dies placed on the same substrate (e.g., FCBGA)
         - Better than using two separate substrates
         - Die-to-die communication goes via BGA → substrate → other die
    2. 2.1D
         - #### RDL
           - Adds a Redistribution Layer (RDL) between die and substrate. RDL allows the rearrangement of the connectivity
           - Die has very small bond pand size and at different locations, which has to be connected to the bond pads of the substarte which are in a different geometrical arrangement and have to be connected. RDL enables this connectivity
           - RDL provides shorter internal connections
           - Reduces signal path length compared to 2D
    3. 2.3 D
          - Uses an organic interposer between the die and substrate
          - Helps fan-out high-density connections
          - Designed to support multiple chips, while RDL works well for 2 dies, but becomes complex beyond that
          - Organic interposer has dedicated power and ground planes
    4. 2.5 D
          - Uses a silicon interposer
          - Passive TSV interposer, while in 3D we use an active TSV interposer 
          - Silicon interposer with very fine metal layers, allowing signal lines to be routed extremely close to ground planes, enabling controlled impedance
          - Fine metal routing + close ground planes create short return paths, reducing noise and crosstalk
          - Compared to organic substrates with coarse metal and distant ground planes, 2.5D achieves much higher bandwidth and signal integrity
          - Example - CoWoS (Chip on Wafer on Substrate)
<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/949ef62d-97d3-4504-9a24-a3872fadc33f" />

## Module 2

#### Supply chain
1. Design house - IC Design (GDS II) - EDA Tools and foundry PDKs
2. Wafer fabrication - Silicon wafers, gases, chemicals, materials, equipment
3. *Package assembly and Test* - Individual ICs assembled in a package and tested
4. Board assembly and test - Many packages on a board are assembled and tested
5. Product assembly and test - Final product assembly and test

#### Packaging process
1. Wafer Preparation (ISO Class 7) – Wafers received in carriers and prepared for processing
2. Wafer Inspection – Visual and defect inspection before processing
3. Front-side Tape Lamination
4. Wafer Back Grinding – Wafer thinned to required thickness, the circuit or patter is only on the top side, while the bottom silicon is only for mechanical strength, since package will provide this mechanical strength further, this silicon is removed.
5. Tape frame mounting to wafer backside
6. Wafer Dicing – Separation into individual dies using laser grooving or blade dicing or both
##### **Wire bond packaging**
  - Using wafer map, known good dies are picked and placed onto the substrate (leadframe or laminate)
  - *Die attach* is performed using epoxy, the epoxy deposition pattern directly affects die attach quality and reliability
  - After die attach, curing is performed
  - Wire Bonding <br/>
<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/ccb5cf2b-4dd4-4cf6-b209-d0da41aa8ba3" /> <br/>
  - Molding compound transfer - Encapsulation of die and wires using molding compound - Resin flow method
  - Marking - Package labeling with part number, lot, and traceability information to identify the package
  - Package dicing <br/>
##### **Flip chip packaging**
  - Bump formation on Si
      1. Before Reflow <br/>
        - Solder is deposited on UBM (Under Bump Metallization) on silicon <br/>
        - Formed by electroplating/solder paste printing/ball placement <br/>
        - Bump shape is irregular or column-like <br/>
        - Solder is solid, and the mechanical strength is low <br/>
      2. After Reflow <br/>
        - Solder is melted and re-solidified <br/>
        - Surface tension forms a uniform spherical bump <br/>
        - Proper wetting to UBM occurs <br/>
        - Strong mechanical and electrical joint <br/>
        - Final bump height and diameter are defined <br/>
  - Flipping the chip
  - Die is placed on the substrate (Substrate already has a bond pad, and flux is applied on the pads)
  - To attach the solder balls, heat and pressure are applied - Thermocompression 
  - Solder Reflow
  - Flux cleansing - Using solvent spray
  - Underfill dispensing - Epoxy material filled between die and substrate to reduce thermo-mechanical stress and improve joint reliability
  - Underfill cure
  - Molding
  - Marking
  - Ball mounting on the substrate and reflow
<img width="500" height="226" alt="image" src="https://github.com/user-attachments/assets/d29fa7e3-a1b4-4836-a00e-6d4850816707" />

#### Wafer-level Packaging
##### Reconstitution process
- Known good dies are picked and placed on a temporary carrier from the wafer
- Modling compound is applied, and the temporary carrier is removed. We get a reconstituted wafer, which is used for further processes

##### RDL preparation
- Dielectric is coated on the carrier
- 1st RDL metal layer patterning, and is continued with dielectric and metal layers alternatively as per the requirement

