# Analysis of fMRI/BOLD signals: connectivity estimation, task/subject identification, network analysis

**These notebooks in Python 3 have been developed by Andrea Insabato, Gorka Zamora-López and Matthieu Gilson. If you use this toolbox, please cite the first papers referenced below.**

These Python notebooks reproduce some figures in the following preprint using the libraries *pyMOU* and *NetDynFlow*: https://www.biorxiv.org/content/10.1101/531830v3

The notebook *1_MOUEC_Estimation.ipynb* should be executed first to tune the model to the fMRI data. The other notebooks can be used for classification and interpretation of the model (using the flow for network analysis).

The data files are:
- BOLD time series in *ts_emp.npy*
- structural connectivity in *SC_anat.npy*
- ROI labels in *ROI_labels.npy*

## Notebook *1_MOUEC_Estimation.ipynb*

This notebook calculates the functional connectivity and the model-based effective connectivity for each session (or run) and subject from the BOLD time series. The model is a multivariate Ornstein-Uhlenbeck (MOU) process, whose estimation procedure is implemented in the *pyMOU* library. The model estimates and other measures are stored in the form of arrays in the *model_param_movie* folder. Meanwhile, several properties of the spatiotemporal structure of the BOLD signal are 

## Notebooks *2a_ClassificationTasks.ipynb* and *2b_ClassificationSubjects.ipynb*

These notebooks compare the performances of the several type of connectivity measures (including functional and effective connectivity) in identifying cognitive tasks and subjects. They rely on the scikit.learn library (http://scikit-learn.org).

## Notebook *3a_Flow.ipynb*

This notebook uses the *NetDynFlow* library to calculate the flow, which is network-oriented analysis of the MOU model fitted to the BOLD data. The flow corresponds to the input response of the network to perturbation (or stimulation of given regions). The flow captures network effects that arise from the recurrent connectivity, i.e. also taking into account indirect paths between all pairs of regions.

## Notebook *3b_Communities.ipynb*

This notebook detects communities based on the flow, namely brain regions are grouped together if they exchange strong flow in the network. It also compares the community structure between rest and movie.

## References

Gilson M, Zamora-López G, Pallarés V, Adhikari MH, Senden M, Tauste Campo A, Mantini D, Corbetta M, Deco G, Insabato A (2019) "Model-based whole-brain effective connectivity to study distributed cognition in health and disease." *bioRxiv* preprint. http://doi.org/10.1101/531830

Original model optimization procedure: Gilson M, Moreno-Bote R, Ponce-Alvarez A, Ritter P, Deco G. (2016) "Estimation of Directed Effective Connectivity from fMRI Functional Connectivity Hints at Asymmetries of Cortical Connectome." *PLoS Comput Biol* 12:e1004762. http://dx.doi.org/10.1371/journal.pcbi.1004762

Classification procedure: Pallarés V, Insabato A, Sanjuan A, Kühn S, Mantini D, Deco G, Gilson M. (2018) "Subject- and behavior-specific signatures extracted from fMRI data using whole-brain effective connectivity." *Neuroimage* 178: 238-254. http://doi.org/10.1016/j.neuroimage.2018.04.070

The classification script uses the scikit.learn library (http://scikit-learn.org)

Empirical data: Gilson M, Deco G, Friston K, Hagmann P, Mantini D, Betti V, Romani GL, Corbetta M. (2018) "Effective connectivity inferred from fMRI transition dynamics during movie viewing points to a balanced reconfiguration of cortical interactions." *Neuroimage* 180:534-546. http://doi.org/10.1016/j.neuroimage.2017.09.061.
See also: Hlinka J, Palus M, Vejmelka M, Mantini D, Corbetta M. (2011) Functional connectivity in resting-state fMRI: is linear correlation sufficient? *Neuroimage* 54:2218-2225. http://doi.org/10.1016/j.neuroimage.2010.08.042
