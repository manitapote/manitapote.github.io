## Resources for coordination detection

<details>
  <summary></summary>
  [Link]()
  
  ##### 
  
</details>


<details>
  <summary>Coordinated amplification strategies</summary>
  [Link](https://link.springer.com/article/10.1007/s13278-021-00815-2/tables/2)
  
  ##### 
  
</details>


<details>
  <summary>Temporal Dynamics of Coordinated Online Behavior: Stability, Archetypes, and Influence</summary>
  [Link](https://arxiv.org/abs/2301.06774) <br /><br />
  **Methodologies:** Use of multiplex temporal network and dynamic commmunity detection to identify groups of users that exhibit coordinated behavior in time. <br />
  **Findings** : <br /> (i) Coordinated communities feature variable degrees of temporal instability <br /> (ii) Dynamic analyses are needed to account for such instability and reuslts of static analyses can be unreliable and scarcely representative of unstable communities. <br /> (iii) some users exhibit distinct archetypal behaviors that have important practical implications <br />(iv) content and network characteristics contribute to explaining why users leave and join coordinated communities <br /><br />
  
  Steps: <br />
  1. **Preliminaries** : Co-retweet network, G, with user similarity
  2. **Dynamic network modeling** : temporal network, 
  
  ```math
  G = {G_0,....,G_{N-1}}
  ```
  where each layer $G_i$ models user behavior occured during a given time window $t_i$. Each $G$ is created with data of 7 days and an offset for $\delta = 1$ day from $t_{i-1}$. For each $G_i$, only the statistically significant edges are retained by computing its multiscale backbone **(Serrano, Boguna and Vespignani 2009)**<br />
  3. **Dynamic community detection** : Leiden based community detection method is used. Leiden is a state of the art community detection method for multiplex networks that consider edges in the graph as well as edges between layers.
  
</details>

<details>
    <summary>A Dataset of Coordinated Cryptocurrency-Related Social Media Campaigns </summary> <br />
   <p> [1](#[1])(https://arxiv.org/pdf/2301.06601.pdf)</p>
    Collection period: 13-May-2014 to 31-Dec-2022 <br />
    Source of Data: Scraping the URL Bitcointalk.org <br />
    Sample Dataset URL: https://zenodo.org/record/7539179 <br /> <br />
    Data: 15.8K Cross media bounty events, 185K participants, 10M forum comments, 
    82M social media URLs <br />
    Data files: Subforum pages, comments, user page, thread pages, images and Google spreadsheets, 
    social media handles from Twitter, Telegram (CSV of rewards,
    wallet information) 
</details>


## References
##### [1] Zilius, K., Spiliotopoulos, T., & van Moorsel, A. (2023). A Dataset of Coordinated Cryptocurrency-Related Social Media Campaigns. arXiv preprint arXiv:2301.06601.
##### [2] Tardelli, S., Nizzoli, L., Tesconi, M., Conti, M., Nakov, P., Martino, G. D. S., & Cresci, S. (2023). Temporal Dynamics of Coordinated Online Behavior: Stability, Archetypes, and Influence. arXiv preprint arXiv:2301.06774.
