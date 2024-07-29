# Probabilistic_Verification_Process_Models
Probabilistic Verification of Process Models learned via Process Mining techniques.

The repository contains codes and sample files, which allow one to perform probabilistic model checking of process models.

The subdirectory 'Code' contains the codes. It has two codes in the Jupyer Notebook: the 'Old_event_log' and 'New_event_log.' The former is the code
for generating all the models from the old event log, and the latter is for the new event logs. Both codes have at the top module the inputs expected
from the user and then step-by-step submodules that end up generating all the files, i.e., an mCRL2 compatible LTS and ADTMC, a PRISM compatible SDTMC,
and text files of saved DFS traversals and information regarding failed trace simulations (if this scenario occurred). To run the codes, one will require
the ProM toolset and an XES event log for which the end events are known. Then, the generated LTS (Petrify SG file) corresponding to the discovered process
model in ProM using the ProM plugin to construct a reachability graph, the event log, and the end event information will enable the user to generate all the files.
For the later code, one will additionally require the mCRL2 toolset from which one can simulate the LTS and save the trace as suffixed 'lts_sim.txt' file along with
the LTS in the above-mentioned format and the end events to generate all the files. Finally, the user will require the PRISM model checker for the next step. 

We provide all the files in each of the Code folders for all codes for the first case study as a sample for understanding the functioning of our codes. All the 
attributes are filled. The user can run each module and see on top of the module to find what this module serves and uncomment the print statements
to look at the interested outputs. The final outputs (all output models) will be available in the same directory where the file belongs.

The other subdirectories each refer to the Case Studies discussed in the paper. Inside them, one will find all the PRISM-compatible models
again stored in separate subdirectories, 'Data' contains models generated from the old event log, and 'Simulation' contains models generated
from the new event log. The Property files are the same for both and hence stored outside. All file names in these directories, either for 
the model or the property file ending in 'alpha' or 'inductive' signifying the Miner to which they correspond and also if they correspond to a $0$ (inductive)
noise threshold or $0.x$ (pointx_inductive) for the Inductive Miner (IMf) or other variants of the Alpha Miner. The 3rd case study discusses some reward-based properties,
which have been saved with the prefix '-Rewards' in case one wishes to verify them. Open the model in the PRISM model checker and its corresponding '.props' file containing
the properties to get the desired result. Other relevant files have also been shared should one wish to view them.

The file 'Appendix.pdf' has details about the properties discussed for each case study in the paper in (a) natural language, (b) APCTL/APCTL* semantics, and translated (c) PCTL/PCTL* semantics using the logical embeddings. 

Additional files are presented in the subdirectories of each case study for one to view. The event logs are stored in a separate zipped folder with the name 'Event_Logs.zip', where the old event logs (original),
old event logs (filtered), and the mCRL2 simulations (new event logs) are presented with names of respective case studies. The generated Petri Nets and the Reachability Graphs 
are also present in the subdirectories with names signifying to whom they belong; their DFS traversals are also saved. The zipped folder can be extracted to view all of them.

In a nutshell, to perform probabilistic model checking of process models, generate the model in ProM, construct the reachability graph of the Petri Net,
then export the event log and the LTS XES and Petrify SG files, respectively. Then, use either code to construct an ADTMC and subsequently the SDTMC, write down specifications in  APCTL/APCTL*, convert them to PCTL/PCTL*, and finally model check the SDTMC w.r.t. to the PCTL/PCTL* property in PRISM to analyze and insight.

All the third-party toolsets are available for free on the internet for personal use and can be easily installed across most OSs. 

