# FRED Tutorial

In order to dock with FRED, you need to prepare the receptor. If you are trying to dock into a pocket where a known ligand already docks, the best input file is one with the ligand still bound. 

## Installation
1. Go to: https://www.eyesopen.com/customer-software-download
2. Fill out the form
3. Click OpenEye Applications
4. Select the applications tar.gz file and the vida tar.gz file that works for your system (The VIDA file is for visualization)
5. Open the applications zip file - install oedocking and click install command line support
6. Install vida<br>
####  After installation (to make sure FRED is installed correctly):<br>
8. Unzip the attached oe_demo file and cd into it
9. Run the following on the command line:<br>
<br>

```fred -receptor 7n7d_site2_demo.oedu -dbase berberine.mol2 -docked_molecule_file fred_output.oeb```

If the command runs properly, you should see multiple FRED output files including a fred_score.txt file.
This site may be helpful for installation https://docs.eyesopen.com/applications/common/install_std.html


## Making A Receptor

#### Open OEDOCKING GUI <br><br>
a. File --> New --> Select PDB file of receptor with original ligand still bound --> click ok <br><br>
b. Click on Loop Building and deselect Build Missing Loops <br><br>
c. Click Make OEDesignUnit <br><br>
d. Wait for Spruce to run. A window will pop up that says Spruce ran successfully. Click ok <br><br>
e. "Select DU to Make Receptor" window pops up. This screen is asking which bound ligand should define the docking site. Select which ligand should be used and click ok. <br><br>
f. On the Shape screen, select the receptor as the target, the ligand selected above as the ligand, and any ligand that should be ignored as X. Leave the K+ counter ions. After changing one of the options, such as qul2 to X, and new OEDU must be created. If next is grayed out, click Make OEDesignUnit which will rerun Spruce. <br><br>
g. Click Make OEDesignUnit. Click ok. Click next. <br><br>
h. If the bounding box is satisfactory, click next, otherwise adjust. <br><br>
i. Click Create Shape <br><br>
j. Click save. <br><br>

##Running FRED on the command line<br>
```fred -receptor your_prepared_receptor.oedu -dbase your_dbase_of_molecules.mol2 -docked_molecule_file fred_output_name.oeb```
