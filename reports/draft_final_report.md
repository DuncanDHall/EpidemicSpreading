# Simulation of Epidemic Spreading in Various Network Topologies
## by Duncan Hall and Seungin Lyu


### Abstract


### Replication of Pastor-Satorras and Vespignani's experiment



<center>

![Figure 11](../resources/figure11.png)

<br>
*Figure 1.1. "Persistence ρ as a function of 1/λ for different network sizes: N = 10<sup>5</sup> (+), N = 5 × 10<sup>5</sup>
(◻), N = 10<sup>6</sup> (×), N = 5 × 10<sup>6</sup> (○), and N = 8.5 × 10<sup>6</sup> (◇). The linear behavior on the
semi-logarithmic scale proves the stretched exponential behavior predicted for ρ. The full line is a
fit to the form ρ ∼ exp(−C/λ)." [1]*
<br>


![Figure 1](../resources/figure1.png)
<br>
*Figure 1.2. We quantitatively replicate the original plot shown in Figure 1.1 with each color corresponding to a network size in the original experiment. We confirm that the persistence ρ is indeed semi-logarithmically linear.*
<br>


![Figure 21](../resources/figure21.png)
*Figure 2.1. a) "Surviving probability P<sub>s</sub>(t) for a spreading rate λ = 0.065 in scale-free networks of
size N = 5 × 10<sup>5</sup> (◻), N = 2.5 × 10<sup>4</sup> (◇), N = 1.25 × 10<sup>4</sup> (△), and N = 6.25 × 10<sup>3</sup> (○). The
exponential behavior, following a sharp initial drop, is compatible with the data analysis of Figure 1.1" [1]*
<br>
![Figure 2](../resources/figure22.png)
<br>
*Figure 2.2. We qualitatively replicate the original plot shown in Figure 2.1. Note that we run the simulation for 50 time steps due to time complexity.*
<br>

</center>

### Going Beyond : SIS model simluation on ER, WS, Facebook network


![Figure 3](https://github.com/SeunginLyu/EpidemicSpreading/blob/master/resources/figure3.png)
<br>
*Figure 3. We run the SIS model simulation on the Facebook data provided by SNAP. We observe qualitatively semi-logarithmically linear graph as in Figure 1.1 and Figure 1.2 but quantitatively the prevalence is higher in this plot.*

### Conclusion

[[[ this conclusion will need re-writing after a bit more experimentation ]]]

We still have some experiments we need to do before writing this conclusion. Namely, we plan to further investigate virus behavior in ER and WS graphs, as we are not sure we understand the definition of a network flood properly. We see that in ER and WS graphs, the viral prevalence actually does reach a steady state for some lambda, though we believe this to actually be due to flooding. We need to do a little bit of math to confirm this. We hypothesize that in non-SF graphs there is a critical lambda as mentioned in Pastor-Satorras and Vespignani, and that the behavior of the virus prevalence over time is only similar to in SF graphs for small network sizes. In other words, lambda values which lead to viral extinction in small and medium-sized SF networks will not do so in networks with increased size (due to the amplitude of the noise relative to the steady state average decreasing), but in non-SF networks we expect the same extinction regardless of size.





### Bibliography

#### [1]. [Epidemic spreading in scale-free networks](https://github.com/SeunginLyu/EpidemicSpreading/blob/master/papers/epidemic_spreading_in_SF_networks.pdf)

Pastor-Satorras, R., & Vespignani, A. (2001). Epidemic spreading in scale-free networks. Physical review letters, 86(14), 3200.

Pastor-Satorras and Vespignani  designed a model for the spreading of infections on scale-free networks. They applied the susceptible-infected-susceptible (SIS) epidemiological model on scale-free graphs (Barabasi and Albert). They believe that models with SIS applied to Euclidean lattices, ER graphs, and WS graphs aren’t completely adequate to represent the real phenomenon because the end behavior after time *t* eventually yields either complete extinction or complete prevalence of a computer virus depending on whether the effective spreading rate is greater or less than the epidemic threshold. They discover the absence of the epidemic threshold in scale-free networks and conclude that “infections can proliferate on these scale-free networks whatever spreading rates they may have. These very bad new are, however, balanced by the exponentially small prevalence for a wide range of spreading rate”.

#### [2]. [Epidemic spreading in Real Networks : An Eigenvalue Viewpoint](https://github.com/SeunginLyu/EpidemicSpreading/blob/master/papers/epidemic_threshols_real_networks_eignevalue.pdf)

Wang, Y., Chakrabarti, D., Wang, C., & Faloutsos, C. (2003, October). Epidemic spreading in real networks: An eigenvalue viewpoint. In Reliable Distributed Systems, 2003. Proceedings. 22nd International Symposium on (pp. 25-34). IEEE.

Wang, Yang and Chenxi Wang proposed a ‘general’ epidemic threshold condition that applies to arbitrary graphs and prove that the epidemic threshold is closely related to the largest eigenvalue of its adjacency matrix under reasonable approximations. They point out that the model proposed by Pastor-Satorras and Vespignani is only limited to the BA graph and only works heavily under the assumption that gamma = 3 when *P(k) = k^(-gamma)* (*P(k)* is the probability that a node has *k* links). They validate their epidemic spreading model on both homogeneous graphs like ER graph and power-law scale free graphs like the BA graph. They conclude that their threshold condition holds for arbitrary graphs by validating their model through extensive experiments on real and synthesized graphs.


#### [3]. [Epidemic Thresholds in Real Networks](https://github.com/SeunginLyu/EpidemicSpreading/blob/master/papers/epidemic_thresholds_real_netowkrs.pdf)

Chakrabarti, D., Wang, Y., Wang, C., Leskovec, J., & Faloutsos, C. (2008). Epidemic thresholds in real networks. ACM Transactions on Information and System Security (TISSEC), 10(4), 1.
Chicago

They present a new analytic model called NLDS(nonlinear dynamic system) that makes no assumptions about the network topology and show that their model performs as well or better than the previous models that are targeted specifically to fit certain special case graphs like ER, WS, and BA graphs. This model is an improved version of <i>Epidemic Spreading in Real Networks : An Eigenvalue Viewpoint</i> (written five years later by almost the same group of author). They conclude that their threshold condition can be used to design new network topologies that are more resistant to viruses.
