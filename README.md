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

## Module 3 
### Ansys Icepak Lab – Thermal Analysis of a Flipchip BGA 
#### Step 1: 
- Insert Icepak Design
- Open ANSYS Workbench
- Navigate to: `Project → Insert → Icepak Design`
#### Step 2: 
- Open the Icepak Layout
- Click the Icepak tab in the top toolbar
- This launches the Icepak layout environment
#### Step 3: 
- Create a Flip-Chip BGA Package
- Navigate to: `Icepak → Toolkit → Geometry → Packages → Flipchip_BGA`
- A configuration window will appear
- Set the following parameters:
    - xLength: 15 mm
    - yLength: 15 mm
    - Package Thickness: 3 mm
    - Model Type: Detailed
    - Symmetry: Full
- Click OK to generate the 3D model
- The Flip-Chip BGA package will appear in the working space

<p align="left">
<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/b04ea4e2-0967-4292-a2c0-4c61547a2f7c" />
</p>
<p align="left">
<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/91161ca0-e78c-4f65-80a4-ab4bd31fcdb4" />
</p>
<p align="left">
<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/de148fc2-e206-4016-b658-66b7dc75312e" />
</p>

#### Step 4:
- In the Model Tree, expand the Solids section
- Observe the generated components such as:
    - Substrate
    - Die
    - Underfill
    - Other package elements

#### Step 5: 
- Assign Thermal Power
- Navigate to: `Project Manager → Thermal`
- Enter the Power value (e.g., 1 W)
- Click OK

#### Step 6: 
- In Solids, select Flipchip-BGA1_substrate
- `Right-click → Assign Thermal → Source`
- In the dialog box:
    - Set Thermal Condition to Ambient Temperature
- Click OK
- Delete any unnecessary thermal elements (e.g., Flipchip_BGA_trace1) under the Thermal node

#### Step 7: 
- Assign Temperature Monitors
- In Solids, select Substrate
- `Right-click → Assign Monitor → Point`
- Enable Temperature → Click OK
- Repeat the same steps for:
    - Die
    - Underfill
#### Step 8: 
- Generate Mesh
- Navigate to the Mesh tab
- Click: `Simulation → Generate Mesh`
- Save the file when prompted
- Click OK

#### Step 9: 
- Inspecting Mesh Quality
- Open Mesh Visualization
- Click Quality
- Verify mesh parameters such as:
    - Face Alignment
    - Skewness
    - Volume
<p align="left">
<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/e881404d-4cd9-4bf8-a890-81b56d7a1b3e" />
</p>
<p align="left">
<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/d3672a0e-3839-4fdf-9e6d-0b3a525c94dd" />
</p>

#### Step 10: 
- Click Validate from the top menu bar
- Ensure all checks return green ticks
- This confirms the model is ready for simulation
<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/84e7e7aa-6f37-4141-854b-9c38afea6ed2" />

#### Step 11: 
- Click Analyze All from the top toolbar
- Select the Flip-Chip BGA package
- Navigate to: `Plot Field → Temperature → Temperature`
- Configure Output Options:
    - Enable Specify Name
    - Enable Specify Folder
    - Enable Plot on Surface Only
    - Under Surface Smoothing, enable Gaussian Smoothing
- Click OK, then Done


<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/dd32072e-ed58-4a50-aac6-3cf5487b69ce" />


## Module 4

- Testing at different stages
    1. Wafer Probe Test – Electrical testing of dies on the wafer
    2. Wafer Sorting – Classification of dies into good/bad bins based on test results
    3. Package Testing – Electrical and functional testing of packaged ICs
    4. System-Level Testing – Testing IC performance in real system conditions
- Movement from processing zone (ISO Class 6-7) to Testing area ( Electrical, burn-in, and reliability chamber tests)
### Package testing 
1. Assembly open and short test
2. Burn-in - Apply thermal and voltage stress to ensure early life reliability
3. Final test - Cold and hot test for validating functional and parametric specs across various temperatures

#### AOST
- Quick test for shorts or opens on package leads or balls
- To screen for massive electrical failures before leaving the assembly
- Vision inspection is also done to check for damaged or missing balls/leads and other defects
#### Burn-in test
- Testing of package components under elevated(stressful) conditions
- To identify Infant mortality failures before they reach customers
- Parts are loaded from trays onto Burn-in boards and then into burn-in ovens during testing
- Accelerates the failures by applying high voltage and high temperature stress
- Defects like **dielectric and metallization failures, electromigration** can be detected
- May result in shortening the total life span of components 
<img width="500" height="545" alt="image" src="https://github.com/user-attachments/assets/d8b0bcfc-d50f-4cf9-8dc8-7ed25ae88ae2" />

#### Final test
- A temperature corner test to verify that the packaged product meets the specifications
- Parts are loaded into temperature-controlled test fixtures during testing
- Automatic test equipment (ATE) is used
- ATPG is sent to the device under test
- Yield, testing time, and test coverage are key performance indicators
##### Parametric tests 
- Measures current or voltage from the unit to ensure the circuits are performing within specified parameters
##### Functional tests
- Evaluate functionality of the unit under operating conditions
##### Speed tests 
- Assesses the speed of units according to data sheet specifications
- Sorting is done based on speed


## Module 5
### Model the Wire Bond Package in Ansys AEDT 
<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/124409f2-b7b2-487b-a54a-425fe4772a00" />

#### Step 1: 
- Launch ANSYS Electronics Desktop
- Select Q3D Layout Design to create a new project

#### Step 2: Create the Die
- Navigate to: `Modeler → Surface → Rectangle`
- Draw a rectangular surface to represent the die
- Set the die thickness to 0.2 mm
- Rename the object to die
- Assign material: Silicon

#### Step 3: Create the Substrate
- Draw another rectangle using the same tool
- Set the substrate size to 5 mm × 5 mm
- Thicken the rectangle to –0.5 mm to form the substrate body
- Rename the object to substrate
- Position the die on top of the substrate by setting its coordinates to: (x = –1, y = –1, z = –0.1)

#### Step 4: Add Die Attach Layer
- Create a rectangle matching the die dimensions at the origin (0, 0, 0)
- Set the thickness to –0.1 mm
- Assign the material modified_epoxy to enable thermal conductivity analysis

#### Step 5: Add Die Pad
- Create a thin rectangular surface to represent the die pad
- Set the thickness to 0.005 mm

#### Step 6: Create Bond Pads
- Add bond pads on both the die and the substrate
- These pads act as electrical connection points for wire bonding
- Assign a conductive material such as gold or aluminum

#### Step 7: Connect Pads Using Bond Wires
- Use the Bondwire tool
- Connect the die bond pads to the substrate pads
- Assign gold as the bond wire material

#### Step 8: Add Mold Compound
- Create a rectangular mold compound to encapsulate the die and bond wires
- Set the mold thickness to 1.2 mm
- Assign an epoxy molding compound (EMC) material

<details>
<summary>Dimensions, Positions and Materials overview</summary>

- Die dimensions <br>
    - 3mm x 3mm 
    - Positions (0,0,0) for center
    - Thickness = 0.2mm
    - Silicon
- Substrate dimensions
    - 5mm x 5mm
    - Positions (-1,-1,-0.1)
    - Thickness = 0.5mm (Keep it -0.5 because me need it in -z direction, below the die)
    - FR4 Material
- Epoxy
    - Positions (0,0,0)
    - Thickness = -0.1
    - 3mm x 3mm
    - Modified epoxy material
- Bond pad on die
    - 0.2 x 0.2
    - First one (0.2,0.2,0.2)
    - Second one (0.5,0.2,02)
    - Thickness = 0.005mm
- Bond pad on substrate
    - 0.2 x 0.2
    - First one (0.2,-0.8,-0.1)
    - Thickness = 0.005mm
- Bond wire
    - JEDEC 4-point type
    - h1= 0.2mm
    - h2=0.305mm (h2 should be higher)
    - diameter = 0.025mm
- Molding compound
    - 5 x 5mm
    - Positions - (-1,-1,-0.1)
    - Material - Epoxy_Kevlar
    - Thickness = 1.2mm
</details>

<p align="left">
<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/c3e8b03e-5b6f-4e23-a047-d60a4470287f" />
</p>
<p align="left">
<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/49e767bf-6a25-4fbb-8f73-d27baabfdc33" />
</p>
<p align="left">
<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/4c97774c-db26-4fb2-bb45-72839ddf0468" />
</p>
