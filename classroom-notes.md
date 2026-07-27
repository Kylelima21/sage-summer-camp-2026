# Day 1

## Intro by Pete Beckman

### Deliverables

- Come up with a problem to tackle
- Create a GitHub repository called “sage-summer-camp-2026"
- With a classroom-notes.md file
- 5-min presentation
- project.md overview of your work for the Sage website
- An ECR app (if applicable)
- A poster
- Your Hermes brain
- A simple review of the course

### Sage Grande Testbed (SGT)

- Sage is a project, a testbed, to address important science questions
- Funded by NSF
- Started about 10 years ago, but transforms with new advances in tech: GPU computing, AI advances
- AI at the edge (edge computing) is transforming science
- Sage is about how do we apply edge computing (e.g., iNat) to the smallest sensors
- Goals:
  - Develop new AI algorithms and tech
  - Advance safety and privacy around AI
  - Deploy 300 new platforms across the US
  - Explore the next gen of real-time monitoring of wildlife, floods, etc.
- A lot of field testing has happened with the actual nodes to test their durability!
- E.g., volcanic eruption detection, species ID, ear tag on animal ID, cloud motion detection, pedestrian detection and directional data, pedestrian flow rates, flood detection, etc.
- Reasons to compute at the edge:
  1. Privacy - some information cannot and should not be sent to the cloud
  2. Bandwidth - limited ability to transmit large files
  3. Power - transmitting takes a lot of power
  4. Latency - lags in communication
  5. Resiliency - if there is an issue at the central computing location, then it would impact everything. With edge, each of the nodes can continue to work independently of each other and the central node
- Supercomputing and tech keeps getting better, ignore the naysayers
- This is a testbed to imagine what is possible - smaller, less energy consuming, lighter, and better computers - like Thor

### AI Agents

- A new, highest level of abstraction, in computing. From CPU, to operating systems, to cloud services and now AI.
- Sage wants to explore AI-assisted coding, AI orchestration of the edge nodes, and AI autonomous operating
- 2022 - models like Chat were trained and then put online, but the model was only able to access the data it was trained on (so no current time info)
- 2023 - models now can write code itself to get answers
- 2025 - Autonomous, terminal based agent. Autonomous loops.
- 2026 - Autonomous, always running, can learn and adapt. Model agnostic, inspectable and extensible
- Agents go down crazy rabbit holes
- You need careful thought and reasoning and deduction
- Many errors come from generalizing on spare understanding 
- Need to force it to create documentation

### AI Ethics

- Transparency - always label AI generated material
- Responsibility - you are responsible
- Recovery - what happens if everything gets deleted?
- Privacy - who can see data/tokens?
- Reproducibility - ensure it can be reproduced
- Data
- Containment
- Keys


## Sage Fundamentals by Sean Shahkarami and Neil Conrad

### Sage Continuum Website/Portal

- Office hours are available post workshop

### Data Access

- Sage Data Client
  - Python client for access to querying, fetching, and organizing data into a dataframe
  - Recommended starting point
  - Best if using Python
- HTTP Data API
  - Low level HTTP data API
  - Provides access most directly as a new line delimited JSON data file
  - Good if you were to use it outside of Python
- Both provide the same data
- Tutorials at: https://sagecontinuum.org/docs/tutorials/accessing-data

### Creating an app and publishing it to Sage

- Follow instructions here: https://sagecontinuum.org/docs/category/edge-apps



# Day 2

### MCPs - Presented by Peter Lebiedzinksi

- Model Context Protocol
- An MCP is an open source standard for connecting AI applications to external systems
- A way for a LLM to pull an external service or code to do some function
- Uses JSON-RPC 2.0 data protocol
- Sage has an MCP
  - Testbed user request something, MCP decides if it needs to reach up to the sage cloud to fulfill the request
  - Can set it up using instructions at: https://github.com/sagemcp/sagemcp
- Allows you to write programs, interact and find data, and control Sage using natural language
- MCP is basically a translator from english (aka natural language) to specific lines of code to do some function

### HERMES - Presented by Pete

- Benefit of using tmux is that the agent continues to run in the background despite you being connected or not
- Could run all night if you tell it to and it needs to
- Compaction: Sessions can only be so long, there’s a max point. 
  - If you hit 100% compaction, the agent will start a new session and try to remember things from the previous session, but it’s not very good/very messy.
  - Before you hit 100% you should write out a file from all the learnings and then in the new session you can open that file to keep going
- Economizing the ins and outs of agents is important as there are limitations to the amount you can use (tokens)


## Basics of Deep Learning by Chris Lee

### Deep Learning Mindset

- We are trying to create pattern recognition systems
- More example = better results
- It doesn’t give absolute truth, just probabilities
- Think of predictions as a distribution

### Anatomy of a Neuron

- Neuron - its a linear function - input -> function -> output
  - Other terms = bias and weights
  - A neuron is the input, bias, weights, linear function, and activation function
  - Used to create functions that can separate data, predict patterns, etc.
- To get to a neuron with N inputs, its the sum of all inputs and weights then plus bias
- Depth = how many layers (hidden and outputs, not including input layer)
- Width = how many inputs
- Another way to talk about inputs is dimensions or features
- Activation functions - hidden layer
  - Standard to use ReLU
  - Avoid non-conventional activations
- Activation functions - regression output layer
  - Regression tasks are predicting answers, the are continuous (not discrete) scores
- Activation functions - classification output layer
  - Logits are the raw predictions
- Universal Approximation Theorem
  - Neural networks can approximate any continuous function
  - Every neuron we add in the hidden layer can create a bend
- Why not make the network infinitely wide
  - Generalization
  - Scalability
- The network cannot effectively predict what it doesn’t have information about

### Dataset Curation

- Data should be:
  - Relevant to task
  - Sufficient quantity of examples
  - Diversity
  - Accurately labeled
  - Representative/Balanced
  - No contamination
- Examples are combinations of features (inputs) and targets (labels)
  - Typically multiple features used to predict targets
  - Must be correlation
- Data splits
  - Training data often 70%
  - Validation data often 15%
  - Test data often 15% - to get an idea of how well it performs
    - Do NOT make decisions based of this or it becomes another validation dataset
  - We typically want the splits to be stratified
  - Imbalanced datasets can skew test results
  - Concept drift = change in relationship between input and target
  - Data drift = change in input distribution (move sensor locations to very different climate)
  - Label drift = change in target distribution

### Preprocessing

- Cleaning
  - Remove dups
  - Handle missing values
  - Address inconsistencies and outliers 
  - Normalization
  - Convert categorical variables into numbers (embeddings)
- Data augmentation
  - When you have insufficient count of examples you might be able to augment 


### Training, Evaluation, Learning

- Training
  - Types of training
    - Reinforcement - Robot interacts with environment and is rewarded or penalized
    - Supervised learning - learning with features and labeled data (targets)
    - Unsupervised learning - learning without labeled data
  - Process for neural network
    - Weight initialization
      - Zero, random, xavier, etc
    - Step 1: Forward pass
    - Step 2: Calculate loss
    - Step 3: Backward pass
    - Step 4: Optimizer/Update weights
  - One epoch is one full pass through all the steps above
- Evaluation:
  - Classification
    - Accuracy, precision, recall, F1 score
  - Regression
    - RMSE, MAW, R^2
- Learning
  - Point of divergence from something to something = overfitting
  - Early stopping prevents overfitting 
- Mini Batching
  - For each epoch shuffle and split dataset into bathes and update models after each
- Hyperparameters
  - Tunable values to adjust
  - Automation
    - Random search, grid search, bayesian optimization, etc


# Day 3

## Foundation Models and Inference at the Edge by Matt Thompson

### Imageomics

Focused on understanding biology of organisms, particularly traits and observable phenotypes from images
Ohio State, NSF
Goal is to harness data that is diverse, massive, and multimodal
We are putting attention in areas that aren’t correlated to areas of highest biodiversity (brazil for example)

### BioCLIP

- BioCLIP is a foundation model for species classification
  - BioCLIP 2.5 trained on 233M images, 1M unique taxa, and fits within 4GB of memory
  - Working on BioCLIP 3 at the moment
  - CLIP = contrastive language image pretraining
- Training scale leads to emergent properties (unsupervised ‘knowledge’)
  - Embedding space is capturing lots of information that we don’t yet understand, and therefore might have really interesting applications and discoveries
- AI and Science exhibits a bidirectional relationship - both can benefit and progress each other
- BioCLIP is meant to be built on, not lived in
  - Domain specialization:
    - Continued pretraining
    - Fine-tuning (full/param-efficient)
    - Few-shot probing - train a classifier on embeddings from the model
  - Development optimization
    - Distillation - take an expert teaching model (BioCLIP 2.5) and use a smaller model trained on it
    - Quantization - shrinking the model
      - PTQ: Post-training quantization
      - QAT: Quantization-aware training
      - Can save memory and latency, but risks accuracy
  - Edge constraints guiding design
    - Hardware/physical limits
      - power, bandwidth, storage, memory processing
    - Science requirements 
      - Latency minimums, decisions provenance
    - Practical limitations
      - Budget, remote troubleshooting
- BioCLIP 2.5 was fine tuned for plant identification and they applied a phenology mask to improve prediction accuracy
  - The fine-tuning though was very resource-intensive
- Getting more out of a foundation model
    - Zero-shot - one forward pass
    - Probe suite - if it does well then the foundation model captures what you are looking for in embedding space. If not, additional fine tuning would likely be beneficial.
    - LoRA
    - Text tower only (LiT)
    - Last k vision blocks
    - Full model
- How can we improve performance on a taxa of interest?
  - https://github.com/Imageomics/sage-summer-2026-bioclip 
  - Peromyscus example
    - P. maniculatus and P. leucopus are hard to distinguish between
      - Have range overlap and one is disease vector
    - Raw embeddings may be better for training classification heads than normalized embeddings
    - Using methods like few-shot approaches you can improve simpler, smaller models’ performance!


## Sage Image Search by Francisco Lozano

### Buzzwords

- BM25 - keyword search
- VLM - vision language model
- Vector search - semantic, find results by comparing embeddings
- Vector database - embeddings are stored in a vector database
- HNSW Index

### Sage Image Search 

- A workflow that allows a researcher to use natural language to search for an image from the Sage databases
- The Sage Image Search benchmarking toolkit enables reproducible, scalable evaluation
- GitHub here: https://github.com/waggle-sensor/sage-nrp-image-search


# Day 4

## National Data Platform by Pedro Ramonetti and Ismael Perez

### Why is data so challenging to use
- Fragmented access, disconnect between production/collection and sharing, need for scalable or specialized compute readiness, complexity of formats, etc.
- NDP is a data ecosystem to promote collaboration, innovation and customizable use of data
  - Facilitates data cataloging to make date FAIR and used at scale
  - Provides collaborative workspaces
  - Connects users to national cyberinfrastructure and cloud resources
  - Enables development and deployment of AI-integrated workflows
  - Offers tools for learning

### NDP Overview
- NDP is not a data repository, but does catalogue data sources to help connect users to existing data
- Can search for data using the catalog tab
- Can add data set using the “add to catalog” tab, all data request are approved by a human
  - Providers of the data are expected to figure out hosting the data and upkeep with the metadata
- A Workspace can be used as a sharing resource or a learning environment
  - E.g., the jupyter notebooks that we worked with on Day 3
  - Can create one to organize a project, notebook, and can share amount partners
  - When you start a server, ensure you stop the server when you are done
  - To stop go file > Hub Control Panel > stop server
- CollabStudio
  - Allows for collaborative work on a workspace across NDP
  - Users must already be registered with NDP
  - Can add a curated catalog to the workspace


# Day 5

## Hardware by Raj Sankaran and Yongho Kim with Argonne

### Sage Nodes for Edge Computing

- Two forms of nodes
  - Wild Node
    - Ready for mounting outside 
    - Easy to add sensors, PoE, USB, LoRaWAN
    - PoE = Power over Ethernet
  - Blade Server
    - Rugged server for instrument huts, indoors
    - Easy to add PoE sensors
  - Waggle is the core platform
- Why do we need an edge device?
  - Computing - CPU/GPU SOC that is low-power
  - Instruments - can add sensors and actuators
  - Communications - external (WAN) and internal (LAN)
  - Power - AC/DC power
- What do we need in an edge device?
  - Power and system management - operate under variety of conditions, remotely debug errors
  - Fault tolerance and recovery - hardware fails and bugs in software
  - System status
  - Systems exist that handle these things - RCB 600 (modular power supply with safety features
- Basics requirements for a node
  - Always recover from faults and continue to run
  - Call home and ask for help, restore communication 
  - Gracefully degrade in performance, continue to operate, reduce/optimize operation to prolong lifespan, achieve minimum operation state
  - Operate autonomously, prepare for comm latencies and blackouts
- Wild Sage Node (first gen)
  - 3ft tall, 2ft wide, 1ft deep, ~30lbs
  - Extensive electrical and environmental testing conducted
  - 2-layer system with computing, power, env conditioning, communication, and management components.
  - Sage node interfaces
    - Four SEN ports for PoE sensors
    - One SEN port for USB

### Sage Grande Testbed: The Next Generation Computing Node for Foundation AI

- Thor - 128 GB unified memory
- Thors perform as good as DGX Spark with larger models, though DGX performance is superior with smaller models
- Thor-Blades are the indoor, software rack style node
- Once nodes reach a certain temperature, output (in Watts) starts dropping
- Thor-Blade Devkit and Thor-Blade Carrier Board
  - Leveraging off the shelf products
  - Carrier Board option uses more power than devkit, but maintains consistent cooler temperatures. AI throughput is also higher, but ends up being slightly less efficient than the devkit
- To implement thor in the wild sage nodes, temperature control is the biggest issue, they are working on trying to find solutions for this
  - Copper tube coil with fan which can cool like a radiator
  - Aluminum box instead of plastic
- Sage Supported Sensors
  - LoRaWAN
  - Air quality
  - Meteorological 
  - Pan-tilt-zoom
  - Microphones
  - Infrared camera
- PyWaggle offers a message layer connection apps to sensors and between apps for sharing immediate results
- Sensor types:
  - Networked - PoE, sensors support HTTP interface and file-transfer protocol
  - USB - connected and powered by USB, longer USB cable = unstable data transfer
  - Sensor-in-the-box - wrapped with a computing device (raspberry pi) to run sensor and support data transfer
  - Wireless - LoRaWAN, low power sensors send small amounts of data to Sage node using radio communications

### Deep Dive: Sensors and Instruments Communication and Interfaces

- The Communication Framework
  - Layered model: transducer -> electrical interface -> bus/signaling -> transport/network protocol -> application protocol -> data format -> os/device interface -> application -> data product
    - Transducer is something that converts something into something else
  - Example for temp data product connected via USB
    - USB connector -> USB bus -> CDS-ACM serial -> byte stream -> vendor ASCII protocol -> CSV lines -> /dev/ttyACM0 -> Python app -> temp data product
- Ways to attach a sensor to a node
  - Direct - sensor speaks on a bus the node exposes
  - Networked (wired) - sensor is an IP endpoint on Ethernet
  - Wireless (IP) - WiFi device joins a network
  - Microcontroller-mediated - an MCU works between a raw sensor and a node
  - Gateway-mediated - e.g., LoRaWAN
- The farther, lower-power, or more numerous the sensors, you move further right along the progression: direct -> networked -> gateway
- Sensor v Instrument v Others
  - Sensor - transduces a physical phenomenon into a signal or measurement
  - Instrument - self-contained measurement system with its own processor
  - Actuator - takes command and changes the physical world (pan-tilt-zoom motor)
  - Software-defined sensor - a program/app that derives measurements from other data (e.g., an ML plugin that publishes the number of cars detected from a video stream)
- USB
  - USB is host-centric; exactly one host initiates and devices respond
  - Power  is limited
  - Bandwidth and distance is very limited (10-15ft max)
- Ethernet and IP
  - Strong cabling advantage over USB
  - PoE is a huge advantage for field devices (no separate power to run camera)
  - High bandwidth, long runs (100ft)
- WiFi
  - Convenient but not very reliable
  - Ideal for hard to cable spots, low-rate data sensors, and sensors with local buffering
- Bluetooth and Bluetooth Low Energy
  - Higher throughput
  - Good for nearby, low-rate, battery devices
  - Limitations: paring difficulties, short range
- LoRaWAN
  - Long range, tiny bandwidth
  - LoRa = physical radio modulation, LoRaWAN = network protocol on top of LoRa
  - LoRaWAN protocol/architecture: sensor -> gateway -> network server -> application server (your data)
  - LoRa is the signaling, LoRaWAN is the stack
  - Tradeoff for extended range and great battery life means slower and less data transfer
  - Great for dispersed environmental sensing
  - Same idea as Meshtastic
- UART
  - Universal Asynchronous Receiver/Transmitter
  - The bedrock serial interface
  - Baud rates must match, a mismatch = garbage
- RS-232
  - Legacy instrument signaling
  - Point to point, one device per port
  - Spans moderate distance (15m)
- RS-485
  - The industrial/environmental workhorse
  - Long cables, multiple sensors, industrial robustness
  - Integrate with a USB adapter
- I2C 
  - Board-level, short distance, addressed
  - Board/enclosure bus
  - Only can span inches
- SPI
  - Fast, short, chip-selected
  - Much faster than I2C
  - More devices = more wires
- GPIO
  - Raw digital lines
  - Can allow apps to run in response to some signal
- Analog Signals and the ADC
  - All things are rooted in analog
  - Many sensors output a continuous analog quantity not a protocol
  - ADC = Analog to digital converter
  - Analog is fragile
- Review slides for breakdowns of needs/tradeoffs and best fits for specific sensor needs!


### Some Points to Note

- The goal of edge computing should be to access highest quality data from the environment and make it possible thanks for edge capabilities
- The SGT platform is about making these tools accessible to the scientific community, the onus then is on the scientific community to determine how to collect the best quality data that is ready for scientific use



# Day 6

## Agentic PTZ Cameras by Peter
- Need a specific agent for the PTZ cameras
- PTZ agent is a minimalist, striped-down agent with only the tooling specific for Sage nodes
- Need to be smaller so it can run on the edge
- 3 pieces
  - The brain - Reasoning LLM
    - Local Ollama
  - The eyes - Multi-model vision
    - YOLO - objects/motion
    - BioCLIP - species/taxa
    - Gemma - semantic scene captions
  - The hands - Sensor gateway
    - Only thing touching the hardware
    - Drives the PTZ
- Interface using plain english
- Documentation:
  - https://sagecontinuum.org/labs/ptz-app

