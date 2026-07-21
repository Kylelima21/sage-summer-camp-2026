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

