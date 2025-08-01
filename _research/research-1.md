---
title: "DeepSensor Great Lakes"
excerpt: "<br/><img src='/images/deepsensor.png'>"
collection: research
---

[Code Repository](https://github.com/great-lakes-ai-lab/GreatLakes-TempSensors)


The Great Lakes, as the planet’s largest freshwater reservoir, not only provide drinking water for over 38 million people, but also serve as a vital resource for irrigation, shipping, hydroelectric power generation, and recreation. Because of their importance, observing and monitoring the Great Lakes is a critical activity. Due to the limited resources available for this much-needed observing and monitoring, it is crucial to make the most efficient use of available observing platforms (e.g. buoys, research vessels).


I am working with ressearchers at the Cooperative Institute for Great Lakes Research to develop and use an open-source package, DeepSensor to answer - "where should the next generation of temperature measurement sensors be placed in order to most efficiently improve our quantitative understanding of Great Lakes surface temperature variability?".


DeepSensor is a package for probabilistically modeling environmental data with neural processes, to characterize Great Lakes surface temperature and to make informed suggestions for future temperature sensor locations.


Contributions so far:
    * Built experimentation pipeline to train DeepSensor on 11 years of Great Lakes geospatial surface temperature data.
    *  Added functionality to include ice concentration data as additional context.
    * Optimized training process with efficient data chunking.
    * Generated predictions for surface temperatures and used meta-learning techniques to identify new sensor placements.