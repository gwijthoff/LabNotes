---
type: overview
layout: single
---

<div class="mw6 center pa3 tc">

### Research [data](#data),<br> [code](#code), and [sketches](#viz)<br>on the history and future<br> of space opera.

</div>

<div class='tc'>✦</div>

<br>

At a time when prominent speculative fiction authors have turned to near-future climate fiction, a younger generation of writers has instead begun publishing stories of interplanetary exploration set centuries from now. These Afrofuturist (Tade Thompson, Nnedi Okorafor), transgender (Yoon Ha Lee, Charlie Jane Anders), and Chinese (Hao Jingfang, Liu Cixin) authors are redefining space opera despite its roots in the toxic idea that we can simply move on and settle another planet if this one is ruined.[^1]

[^1]: While [Tade Thompson sees](https://lithub.com/please-stop-talking-about-the-rise-of-african-science-fiction/) "Afrofuturism" as an umbrella term that is beginning to encompass work by authors both from the African continent and the African diaspora, [Nnedi Okorafor distinguishes](https://nnedi.blogspot.com/2019/10/africanfuturism-defined.html) her work as Africanfuturist: "specifically and more directly rooted in African culture, history, mythology and point-of-view." [Yoon Ha Lee](https://www.sfsignal.com/archives/2015/03/exclusive-interview-yoon-ha-lee-operation-arcana-story-graphology-hemorrhage/) and [Charlie Jane Anders](https://www.them.us/story/gavilan-rayna-russom-charlie-jane-anders-envoy-new-album-interview) have both discussed the ways that SF has represented for them "permission and empowerment to not fit into conventional social norms." For context on the meteoric rise of Chinese SF over the past decade, see the special issue of *SFRA Review* on "[Chinese Science Fiction and the World](https://sfrareview.org/vol-51-no-2-spring-2021/)."

This project in progress situates the new wave of space opera amid a computationally-inflected history of the subgenre by comparing literary data at different resolutions with astronomical data like NASA’s Exoplanet Archive.

*All datasets, visualizations, and code below are custom unless otherwise noted.*

<div class="mw6 tr">

Grant Wythoff<br>Center for Digital Humanities<br>Princeton University

<br>

</div>

# Exploratory Text Analysis {#code}

Modeling literary data is like counting fish in the sea: no method will fully capture the wide diversity and deep nuance of what's there. A trawler drags a harmful net across the ocean floor, paying no regard to local ecologies and scooping up everything in its path, like this [single Internet Archive text file](https://www.kaggle.com/jannesklaas/scifi-stories-text-corpus), containing 150 MB of bulk OCR'd pulp magazine text from 1845 to the present in multiple languages. A taxonomist carefully catches (and hopefully releases) unique specimens that are representative of a species, like the 189 novels published by Orion's [SF Masterworks series](https://en.wikipedia.org/wiki/SF_Masterworks) that represent a particular critical account of speculative fiction.

Somewhere between the two scales of collection above, pole-and-line fishers have a good idea of what they're trying to catch, a method for catching a lot of it, and are often surprised by what they find. This is the path I've been taking: starting with standard bibliographies of English-language SF and using them to explore patterns in the full text of those works hosted by HathiTrust Research Center. While all of these models are "wrong," some are useful.

**_<div class='tc'>Number of speculative fiction novels<br>collected from HathiTrust, by decade[^2]</div>_**

[^2]: The initial list of 3,248 novels was scraped from [Worlds Without End](https://www.worldswithoutend.com/), an exhaustive, fan-managed bibliography of speculative fiction. The list thus reflects the preferences and biases of a particularly engaged, technically-savvy community of readers. Another approach would be to start with the [Classics of Science Fiction](https://csfquery.com/) database, which ranks SF novels by the number of award nominations they receive and "best-of" lists they appear on. We could also cross-reference that list with the [Open Syllabus Explorer](https://opensyllabus.org/) — a database of 7 million syllabi — to find the SF novels most often taught in U.S. college courses. Finally, we could combine these three bibliographies, removing duplicates, in order to see how the textual patterns we're interested in respond to different forms of selection and curation by fans, critics, and professors. For more detail, see [my Python notebook](https://github.com/gwijthoff/HTRC_SF_experiments/blob/main/htrc_sf_experiments.ipynb) documenting the data collection process.

```
1900s ░ 35
1910s ░ 40
1920s ░ 39
1930s  19
1940s ░ 49
1950s ░░░░░ 192
1960s ░░░░░░░░░ 323
1970s ░░░░░░░░░░░░░░░░░░░░ 710
1980s ░░░░░░░░░░░░░░░░░░ 654
1990s ░░░░░░░░░░░░░░░░ 576
2000s ░░░░░░░░░░░░░░░░░ 594
```

#### Replicate my data collection in this [✦ Python notebook ✦](https://github.com/gwijthoff/HTRC_SF_experiments/) for accessing and analyzing 3,248 twentieth-century speculative fiction novels via HathiTrust.

During my research, I periodically like to take snapshots of just one of the novels in this large collection. For a project I called "Data, Summarize," I used DrawBot to write Python code allowing me to analyze my data and typeset the results in the same script. In the text analysis "broadside" below, I pull the bibliographic metadata for each book from HathiTrust Research Center (HTRC), including publisher, place, and identifier from OCLC, the global library cooperative behind WorldCat. I then take a sample of random words (or "tokens" in the parlance of natural language processing) from the novel, and perform term frequency / inverse document drequency (TF-IDF) analysis to produce a list of the tokens that are most distinctive to *this* novel as opposed to others in the collection. Finally, I typeset the results by calculating the appropriate font sizes for the page dimensions. Each time the script loads, it pulls in a new novel and prints a broadside like the one below.

[![](https://raw.githubusercontent.com/gwijthoff/data-summarize/main/output/Delany_1967_THE%20EINSTEIN%20INTERSECTION%20.png)](https://github.com/gwijthoff/data-summarize/)

#### Use my [✦ DrawBot script ✦](https://github.com/gwijthoff/data-summarize/) for simultaneously analyzing the text of a novel and typesetting the results.

# Visualizations {#viz}

- [How far in the future are works of speculative fiction set?]({{< ref "/future" >}}) (in process)
- [Prevalence of first-person, third-person, and epistolary novels, 1660-1850]({{< ref "/narrative" >}})
- [Chart of exoplanet discoveries to date, by orbital period and mass]({{< ref "/exoplanets" >}})

# Data Curation {#data}

- [Time Horizons of Speculative Fiction](https://github.com/gwijthoff/TimeHorizons) (in process)
- [Live-updated data from the NASA Exoplanet Archive](https://github.com/gwijthoff/exoplanets)
- [SF works ranked by number of award nominations and anthology re-publications, 1551–2020 (Classics of SF)](https://gist.github.com/gwijthoff/d8af3b328686a0450733d7af98940395)

# Guiding Questions

<span class="small-caps b">Race, Gender, & Archives</span> 

How can standard bibliographies like the Internet Speculative Fiction Database and Worlds Without End be made more representative of Black and women authors who were excluded from mainstream pulp magazines and SF publishers? How can our data collection and analysis methods be made more responsive to emerging scholarship on the history of these diverse voices?

<span class="small-caps b">Distance & Genre</span> 

Does a narrative world's distance from the Earth correlate with genre differences? Are works set farther away (either in terms of actual stellar setting or distance measurements in the text) more closely tied to fantasy? Are works set closer to our solar system associated with "hard" SF?

<span class="small-caps b">Neology & Novums</span>

How can we use automated methods to measure a text's density of invented names (neology) for imaginary things (novums)? Can named-entity recognition (NER) detect fictional place names or speculative technologies?

<span class="small-caps b">Character Networks

How has the gender of characters changed from golden age to contemporary SF? Have defining space opera features like the heroic central character and the quest narrative changed in works of the 2010s and 2020s?

<span class="small-caps b">Temporality</span>

How far in the future is a work of space opera likely to be set? Has that future horizon shifted from golden age to contemporary SF?

<br>

<div class='tc'>✦</div>

<br>
<br>