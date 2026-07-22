# Day 1

## Intro by Pete Beckman

### Deliverables

- Come up with a problem to tackle
- Create a GitHub repository called “sage-summer-camp-2026
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
