# FRED Tutorial (G Quadruplex example)

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

In order to dock with FRED, you need to prepare the receptor. If you are trying to dock into a pocket where a known ligand already docks, the best input file is one with the ligand still bound. 

#### Open OEDOCKING GUI <br><br>
a. File --> New --> Select 7N7D_model1_demo.pdb --> click ok <br><br>
b. An option box appears. Click on Loop Building and deselect Build Missing Loops (**NOTE** This tutorial is specifically for G quadruplexes- For proteins, you may need to select different options)<br><br>
c. Click Make OEDesignUnit <br><br>
d. Wait for Spruce to run. A window will pop up that says Spruce ran successfully. Click ok <br><br>
e. "Select DU to Make Receptor" window pops up. This screen is asking which bound ligand should define the docking site. Select BER-A102 as the ligand and click ok. <br><br>
f. On the Box screen, switch BER-A101 from target to X. Leave the BER-A102 as the ligand and the protein as receptor. Leave counter ions. After changing one of the options, a new OEDU must be created. Click Make OEDesignUnit which will rerun Spruce. <br><br>
g. Select Make OEDesginUnit and then click OK  
h. On the shape screen, adjust the box so that the ligand is fully inside the box, but there is not too much space around it the ligand. Click Next <br><br>
i. Click Create Shape <br><br>
j. Click save. <br><br>

## Running FRED on the command line<br>
```fred -receptor 7n7d_site2_demo.oedu -dbase berberine.mol2 -docked_molecule_file fred_output.oeb```

## Creating a FRED Docking report
```docking_report -docked_poses fred_output.oeb -receptor 7n7d_site2_demo.oedu -report_file fred_output_report.pdf```






