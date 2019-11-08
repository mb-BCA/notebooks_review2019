# notebooks_review2019
These Python notebooks reproduce some figures in the following preprint using the libraries pyMOU and NetDynFlow: https://www.biorxiv.org/content/10.1101/531830v3

The following notebook should be executed first to tune the model to the fMRI data: *MOU_EC_Estimation.ipynb*. The other notebooks can be used for classification and interpretation of the model (using the flow for network analysis).

The data files are:
- BOLD time series in *ts_emp.npy*
- structural connectivity in *SC_anat.npy*
- ROI labels in *ROI_labels.npy*

**These notebooks in Python 3 have been developed by Andrea Insabato, Gorka Zamora-López and Matthieu Gilson. If you use this toolbox, please cite the first papers referenced below.**

## Notebook *MOU_EC_Estimation.ipynb*

This notebook calculates the functional connectivity and the model-based effective connectivity for each session (or run) and subject from the BOLD time series. The model is a multivariate Ornstein-Uhlenbeck (MOU) process, whose estimation procedure is implemented in the *pyMOU* library. The model estimates and other measures are stored in the form of arrays in the *model_param_movie* folder. Meanwhile, several properties of the spatiotemporal structure of the BOLD signal are 

## Notebook *ClassificationTasks.ipynb* and *ClassificationSubjects.ipynb*

These notebooks compare the performances of the several type of connectivity measures (including functional and effective connectivity) in identifying cognitive tasks and subjects. They rely on the scikit.learn library (http://scikit-learn.org).

## Notebook *Flow.ipynb*

This notebook use the *NetDynFlow* library to calculate the flow, which is network-oriented analysis of the model fitted to the BOLD data. The flow corresponds to the input response of the network to perturbation (or stimulation of given regions). The flow captures network effects that arise from the recurrent connectivity, i.e. also taking into account indirect paths between all pairs of regions.

## References

Gilson M, Zamora-López G, Pallarés V, Adhikari MH, Senden M, Tauste Campo A, Mantini D, Corbetta M, Deco G, Insabato A (bioRxiv) Model-based whole-brain effective connectivity to study distributed cognition in health and disease; http://doi.org/10.1101/531830

Original model optimization procedure: Gilson M, Moreno-Bote R, Ponce-Alvarez A, Ritter P, Deco G. Estimation of Directed Effective Connectivity from fMRI Functional Connectivity Hints at Asymmetries of Cortical Connectome. PLoS Comput Biol 2016, 12: e1004762; http://dx.doi.org/10.1371/journal.pcbi.1004762

Classification procedure: Pallarés V, Insabato A, Sanjuan A, Kühn S, Mantini D, Deco G, Gilson M. Subject- and behavior-specific signatures extracted from fMRI data using whole-brain effective connectivity. Neuroimage 2018, 178: 238-254; http://doi.org/10.1016/j.neuroimage.2018.04.070

The classification script uses the scikit.learn library (http://scikit-learn.org)

Empirical data: Gilson M, Deco G, Friston K, Hagmann P, Mantini D, Betti V, Romani GL, Corbetta M. Effective connectivity inferred from fMRI transition dynamics during movie viewing points to a balanced reconfiguration of cortical interactions. 
Neuroimage 2018, 180: 534-546; http://doi.org/10.1016/j.neuroimage.2017.09.061.
See also: Hlinka J, Palus M, Vejmelka M, Mantini D, Corbetta M. Functional connectivity in resting-state fMRI: is linear correlation sufficient? Neuroimage 2011, 54:2218-2225; http://doi.org/10.1016/j.neuroimage.2010.08.042
