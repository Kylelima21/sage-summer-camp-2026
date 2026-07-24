# Exploring the Potential for Edge Computing to Collect Novel Biotic Interaction Data

Kyle Lima </br>
klima@schoodicinstitute.org </br>
*University of Maine, Schoodic Institute at Acadia National Park* </br>


## Introduction

Biodiversity is essential for ecosystem functioning and the provisioning of ecosystem services but is increasingly threatened by global change. Global change is impacting species abundances, distributions, and biotic interactions causing novel ecological communities, and doing so at rates more rapidly than ever before. Understanding and mitigating these changes has therefore become critical to biodiversity conservation.

However, predicting biodiversity responses to global change remains challenging because the ecological processes that shape species populations and communities operate across multiple spatial and temporal scales. Species distributions and community composition emerge from interactions among processes ranging from local-scale habitat conditions and species interactions to landscape-scale environmental gradients and regional climate patterns. This is a central challenge in ecology, processes governing biodiversity are inherently scale dependent, yet most predictive models assume that relationships between biodiversity and other drivers remain constant across scales. While studies have modeled how geophysical and biological drivers (i.e., forest structure, topographic characteristics, landscape composition and configuration) influence biodiversity across multiple spatial and temporal scales, most approaches only emphasize coarse climate or landscape patterns and overlook other important drivers that shape ecological communities.

Perhaps the greatest remaining challenge in predictive ecology is incorporating biotic interactions into models of biodiversity change. Although ecological theory recognizes species interactions as fundamental determinants of biodiversity, they are rarely incorporated into models because they are difficult to quantify consistently across broad spatial and temporal extents. While studies have shown the importance of biotic interactions on species distributions and community composition, we don’t understand how these effects operate at different scales, i.e. the Raunkiaeran shortfall, especially in relation to other drivers. Similarly, we don’t know how biotic interactions relate to other critical components of biodiversity distribution like geophysical characteristics (e.g., climate, roughness, topographic complexity, etc.) which inherently mediate the importance of biological drivers like biotic interactions.


## Project Overview

This projects begins to explore the ability of AI to collect biotic interaction data by working with the Sage Grande Testbed and applying a simple example model at the edge. We compare two foundation models (BioCLIP and DINOv3) with a few different classification heads trained on the same data to perform the same task: classify an image to a certain biotic interaction type. We took the top model and published an application on a Sage Node to provide a proof of concept example classifying interactions from images at the edge.


## Methods and Results


## Future Directions

The long-term goals are to integrate multiple sensors (acoustic recording units, video, image) to monitor for interactions more effectively and to develop a more powerful, well trained version of this application to classify more types of biotic interactions. We would also liek to scale data collection across the SGT network as well as integrate this with NEON sites.




