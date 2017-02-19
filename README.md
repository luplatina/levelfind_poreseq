# levelfindengine_poreSEQ
Use Bayesian model to extract signs levels and noise information of DNA bases from raw nanopore sequencing data.

Overview:
Nonopore DNA sequencing data is time series current signal. Current level findengine is the first critical step for
analysising raw nanopore DNA sequencing data. Current level has been found the most straight-forwards feature to 
identify DNA bases sequence. My most recent research discovery in Harvard nanopore group has prove that not only 
the current level, but the currennt fluctuation within the current level also strongly correlated to DNA bases 
identification. Therefore, the goal of this level findengine must be able to extract the current signal segments 
distinguishable on current levels and the distingishable on current flucation magnitude. Obtaining accurate current 
levels and fluctuation features is extremely meaningful for next step alignment work.

The procedure
Using Bayesian statistics model to find DNA bases events levels has only one general assumption:All noisy current segments for the nanopore sequencing data can be identified as groups of data obeying certain Gaussian distribution probablities.Each Gaussian distribution has its own mean value (mean current level) and varaince (current fluctuation range). The Bayesian statistics model here is to predict whether the segment of noisy current data belong to a single Gaussian distribution or not,  written as Posterior P(M|D). D is the series of current data for the whole segment. M is the model that considers the whole segment data belong to one Gaussian. P(M|D)=prior(M)*P(D|M). The liklihood on the time series data is P(D|M), with one simple  
