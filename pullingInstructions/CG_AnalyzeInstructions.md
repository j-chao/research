# PULLING SIMULATIONS ON 2KBP WORK LOG

Convert all-atom PDB to RACER CG pdb file (2kbp.pdb -> 2kbp.pdb.pdb)
$ ./mapping_atocg.py 2kbp.pdb

Use TINKER pdb2xyz.x to convert CG pdb to CG xyz (2kbp.pdb.pdb -> 2kbp.pdb.xyz)\
$ pdbxyz.x 2kbp.pdb.pdb -k tinker_RACER.key\

Sara Note: re-ran analysis: ecg_hbond3.f and analyze.f modified to output CG H_bond Energy Interactions (wait for code to compel)\

Run minimize on CG xyz files\
[syc384@bme-venus ~/02_01_17_RNA_G4_CG_conversion]$ /home/davbell/software/tinker7.1.2/source_noncan_02_01_17/minimize.x 2kbp.pdb.xyz.xyz -k tinker_RACER.key 1 > minimize_2kbp_CG_xyz.log\



\f0\b0 \
 Energy Component Breakdown :           Kcal/mole      Interactions\
\
 Bond Stretching                          47.6975            116\
 Angle Bending                           159.7575            170\
 Torsional Angle                          37.9994            180\
 Van der Waals                           -30.8391           4387\
 Charge-Charge                            22.2400            137\
 CG H-bond Energy                        -26.2457             60
\f1\b \
\
[syc384@bme-venus ~/02_01_17_RNA_G4_CG_conversion]$ /home/davbell/software/tinker7.1.2/source_noncan/analyze.x 1my9.pdb.xyz.xyz -k tinker_RACER.key d > 1my9_CG_analyze_pm.log
\f0\b0 \
\

\f1\b [syc384@bme-venus ~/02_01_17_RNA_G4_CG_conversion]$ tail 1my9_CG_analyze_pm.log\

\f0\b0  Intermolecular Energy :                  15.8163 Kcal/mole\
\
 Energy Component Breakdown :           Kcal/mole      Interactions\
\
 Bond Stretching                          80.0180            164\
 Angle Bending                           460.0052            242\
 Torsional Angle                          64.0711            260\
 Van der Waals                           -27.5802           8927\
 Charge-Charge                            47.7234            301\
 CG H-bond Energy                        -53.7472             87
\f1\b  \

\f0\b0 \

\f1\b [syc384@bme-venus ~/02_01_17_RNA_G4_CG_conversion]$ /home/davbell/software/tinker7.1.2/source_noncan/analyze.x 2kbp.pdb.xyz.xyz_2 -k tinker_RACER.key d > min_2kbp_CG_analyze_pm.log\
\
[syc384@bme-venus ~/02_01_17_RNA_G4_CG_conversion]$ tail min_2kbp_CG_analyze_pm.log
\f0\b0 \
 Intermolecular Energy :                  -2.5676 Kcal/mole\
\
 Energy Component Breakdown :           Kcal/mole      Interactions\
\
 Bond Stretching                           1.3643            140\
 Angle Bending                            21.0636            206\
 Torsional Angle                          43.7922            220\
 Van der Waals                           -38.6397           6457\
 Charge-Charge                            38.5873            211\
 CG H-bond Energy                        -47.9188             60\
\

\f1\b [syc384@bme-venus ~/02_01_17_RNA_G4_CG_conversion]$ /home/davbell/software/tinker7.1.2/source_noncan/analyze.x 3ibk.pdb.xyz.xyz_2 -k tinker_RACER.key d > min_3ibk_CG_analyze_pm.log\
\
[syc384@bme-venus ~/02_01_17_RNA_G4_CG_conversion]$ tail min_3ibk_CG_analyze_pm.log
\f0\b0 \
 Intermolecular Energy :                  -2.8631 Kcal/mole\
\
 Energy Component Breakdown :           Kcal/mole      Interactions\
\
 Bond Stretching                           1.8675            140\
 Angle Bending                            14.4437            206\
 Torsional Angle                          22.4275            220\
 Van der Waals                           -66.0467           6457\
 Charge-Charge                            40.5640            211\
 CG H-bond Energy                        -48.5532             64\
\

\f1\b [syc384@bme-venus ~/02_01_17_RNA_G4_CG_conversion]$ /home/davbell/software/tinker7.1.2/source_noncan/analyze.x 2m18_top.pdb.xyz.xyz_2 -k tinker_RACER.key d > min_2m18_top_CG_analyze_pm.log\
\
[syc384@bme-venus ~/02_01_17_RNA_G4_CG_conversion]$ tail min_2m18_top_CG_analyze_pm.log\

\f0\b0  Intermolecular Energy :                  -6.4693 Kcal/mole\
\
 Energy Component Breakdown :           Kcal/mole      Interactions\
\
 Bond Stretching                          29.9375            116\
 Angle Bending                           150.7271            170\
 Torsional Angle                          38.0058            180\
 Van der Waals                           -30.9640           4387\
 Charge-Charge                            23.2010            137\
 CG H-bond Energy                        -23.9935             58\
\

\f1\b [syc384@bme-venus ~/02_01_17_RNA_G4_CG_conversion]$ /home/davbell/software/tinker7.1.2/source_noncan/analyze.x 2m18_bottom.pdb.xyz.xyz_2 -k tinker_RACER.key d > min_2m18_bottom_CG_analyze_pm.log\
\
[syc384@bme-venus ~/02_01_17_RNA_G4_CG_conversion]$ tail min_2m18_bottom_CG_analyze_pm.log\

\f0\b0  Intermolecular Energy :                  -1.8242 Kcal/mole\
\
 Energy Component Breakdown :           Kcal/mole      Interactions\
\
 Bond Stretching                           1.3698            116\
 Angle Bending                            26.1780            170\
 Torsional Angle                          22.6528            180\
 Van der Waals                           -43.3574           4387\
 Charge-Charge                            25.3002            137\
 CG H-bond Energy                        -48.3108             62\
\

\f1\b [syc384@bme-venus ~/02_01_17_RNA_G4_CG_conversion]$ /home/davbell/software/tinker7.1.2/source_noncan/analyze.x 1my9.pdb.xyz.xyz_2 -k tinker_RACER.key d > min_1my9_CG_analyze_pm.log\
\
[syc384@bme-venus ~/02_01_17_RNA_G4_CG_conversion]$ tail min_1my9_CG_analyze_pm.log\

\f0\b0  Intermolecular Energy :                  -0.3925 Kcal/mole\
\
 Energy Component Breakdown :           Kcal/mole      Interactions\
\
 Bond Stretching                           3.2494            164\
 Angle Bending                            32.0844            242\
 Torsional Angle                          39.6354            260\
 Van der Waals                           -58.0291           8927\
 Charge-Charge                            49.0408            301\
 CG H-bond Energy                        -75.2383             84\

\f1\b \

\f0\b0 Generating xyz files to visualize minimized coarse-grained RNA G4s
\f1\b  \
\
[syc384@bme-venus ~/02_01_17_RNA_G4_CG_conversion]$ mkdir minimized_CG_RNA_xyz_files_pymol_format\
[syc384@bme-venus ~/02_01_17_RNA_G4_CG_conversion]$ scp -rp *_2 minimized_CG_RNA_xyz_files_pymol_format/\
[syc384@bme-venus ~/02_01_17_RNA_G4_CG_conversion]$ cd minimized_CG_RNA_xyz_files_pymol_format/\
[syc384@bme-venus minimized_CG_RNA_xyz_files_pymol_format]$ mv 2kbp.pdb.xyz.xyz_2 min_CG_2kbp.xyz\
[syc384@bme-venus minimized_CG_RNA_xyz_files_pymol_format]$ mv 3ibk.pdb.xyz.xyz_2 min_CG_3ibk.xyz\
[syc384@bme-venus minimized_CG_RNA_xyz_files_pymol_format]$ mv 2m18_top.pdb.xyz.xyz_2 min_CG_2m18_top.xyz\
[syc384@bme-venus minimized_CG_RNA_xyz_files_pymol_format]$ mv 2m18_bottom.pdb.xyz.xyz_2 min_CG_2m18_bottom.xyz\
[syc384@bme-venus minimized_CG_RNA_xyz_files_pymol_format]$ mv 1my9.pdb.xyz.xyz_2 min_CG_1my9.xyz\
\

\f0\b0 Copied all-atom pdb files, coarse-grained xyz files, and minimized coarse-grained xyz files to Sara\'92s MacBookPro
\f1\b \
\
\pard\tx560\tx1120\tx1680\tx2240\tx2800\tx3360\tx3920\tx4480\tx5040\tx5600\tx6160\tx6720\pardirnatural\partightenfactor0

\fs36 \cf0 saracheng@wireless-10-146-149-46:~/Documents/Research_Spring_2017/02_01_17_RNA_G4_mapping_to_cg_and_minimization$ pwd
\f0\b0 \
/Users/saracheng/Documents/Research_Spring_2017/02_01_17_RNA_G4_mapping_to_cg_and_minimization\
\

\f1\b scp -rp syc384@bme-venus.bme.utexas.edu:/home/syc384/02_01_17_RNA_G4_CG_conversion/minimized_CG_RNA_xyz_files_pymol_format/*.xyz .
\f0\b0 \
\

\f1\b saracheng@wireless-10-146-149-46:~/Documents/Research_Spring_2017/02_01_17_RNA_G4_mapping_to_cg_and_minimization$ scp -rp syc384@bme-venus.bme.utexas.edu:/home/syc384/02_01_17_RNA_G4_CG_conversion/*.pdb.xyz.xyz .\
\
saracheng@wireless-10-146-149-46:~/Documents/Research_Spring_2017/02_01_17_RNA_G4_mapping_to_cg_and_minimization$ ls -rlht 
\f0\b0 \
-rw-r--r--  1 saracheng  staff   7.9K Feb  1 10:35 2kbp.pdb.xyz.xyz\
-rw-r--r--  1 saracheng  staff   7.9K Feb  1 10:36 3ibk.pdb.xyz.xyz\
-rw-r--r--  1 saracheng  staff    13K Feb  1 10:36 2m18.pdb.xyz.xyz\
-rw-r--r--  1 saracheng  staff   4.3K Feb  1 10:36 1s9l.pdb.xyz.xyz\
-rw-r--r--  1 saracheng  staff   9.2K Feb  1 10:36 1my9.pdb.xyz.xyz\
-rw-r--r--  1 saracheng  staff   6.5K Feb  1 11:06 2m18_bottom.pdb.xyz.xyz\
-rw-r--r--  1 saracheng  staff   6.5K Feb  1 11:06 2m18_top.pdb.xyz.xyz\
-rw-r--r--  1 saracheng  staff   7.9K Feb  1 11:41 min_CG_2kbp.xyz\
-rw-r--r--  1 saracheng  staff   7.9K Feb  1 11:45 min_CG_3ibk.xyz\
-rw-r--r--  1 saracheng  staff   6.5K Feb  1 11:47 min_CG_2m18_top.xyz\
-rw-r--r--  1 saracheng  staff   6.5K Feb  1 11:55 min_CG_2m18_bottom.xyz\
-rw-r--r--  1 saracheng  staff   9.2K Feb  1 11:55 min_CG_1my9.xyz\
\

\f1\b \

\f0\b0 Re-minimize 
\fs34 2m18_top with a stronger energy criteria (angle energy term too high)
\f1\b\fs36 \
\
\pard\tx560\tx1120\tx1680\tx2240\tx2800\tx3360\tx3920\tx4480\tx5040\tx5600\tx6160\tx6720\pardirnatural\partightenfactor0

\fs34 \cf0 [syc384@bme-venus ~/02_01_17_RNA_G4_CG_conversion]$ /home/davbell/software/tinker7.1.2/source_noncan/minimize.x 2m18_top.pdb.xyz.xyz -k tinker_RACER.key 0.5 > minimize_2m18_top_CG_xyz_rms_grad_per_atom_0pt5.log\
\
\pard\tx560\tx1120\tx1680\tx2240\tx2800\tx3360\tx3920\tx4480\tx5040\tx5600\tx6160\tx6720\pardirnatural\partightenfactor0

\fs30 \cf0 [syc384@node121 ~/02_01_17_RNA_G4_CG_conversion]$ /home/davbell/software/tinker7.1.2/source_noncan/analyze.x 2m18_top.pdb.xyz.xyz_3 -k tinker_RACER.key d > 
\fs32 min_2m18_top_CG_analyze_pm_rms_grad_per_atom_0pt5.log
\f0\b0\fs36 \
\

\f1\b\fs30 [syc384@node121 ~/02_01_17_RNA_G4_CG_conversion]$ 
\fs32 min_2m18_top_CG_analyze_pm_rms_grad_per_atom_0pt5.log
\f0\b0\fs30 \
 Intermolecular Energy :                  -5.7848 Kcal/mole\
\
 Energy Component Breakdown :           Kcal/mole      Interactions\
\
 Bond Stretching                           0.8438            116\
 Angle Bending                            17.8395            170\
 Torsional Angle                          22.4041            180\
 Van der Waals                           -48.4112           4387\
 Charge-Charge                            27.1798            137\
 CG H-bond Energy                        -50.4397             63\
\

\f1\b [syc384@node121 ~/02_01_17_RNA_G4_CG_conversion]$ scp -rp 2m18_top.pdb.xyz.xyz_3 minimized_CG_RNA_xyz_files_pymol_format\
[syc384@node121 ~/02_01_17_RNA_G4_CG_conversion]$ cd minimized_CG_RNA_xyz_files_pymol_format/\
[syc384@node121 minimized_CG_RNA_xyz_files_pymol_format]$ mv 2m18_top.pdb.xyz.xyz_3 min_CG_2m18_top_rms_grad_per_atom_0pt5.xyz\
\
[syc384@node121 ~/02_01_17_RNA_G4_CG_conversion]$ mv minimize_2m18_top_CG_xyz_rms_grad_per_atom_0pt5.log minimized_CG_RNA_G4_log_files\
[syc384@node121 ~/02_01_17_RNA_G4_CG_conversion]$ mv 
\fs32 min_2m18_top_CG_analyze_pm_rms_grad_per_atom_0pt5.log
\fs30  
\fs32 analyze_results_min_CG_RNA_G4_log_files_pm_version\
\
\pard\tx560\tx1120\tx1680\tx2240\tx2800\tx3360\tx3920\tx4480\tx5040\tx5600\tx6160\tx6720\pardirnatural\partightenfactor0

\fs34 \cf0 saracheng@wireless-10-146-149-46:~/Documents/Research_Spring_2017/02_01_17_RNA_G4_mapping_to_cg_and_minimization/analyze_results_pre_post_RNA_G4_minimization$ scp -rp syc384@bme-venus.bme.utexas.edu:/home/syc384/02_01_17_RNA_G4_CG_conversion/analyze_results_CG_RNA_G4_log_files_pm_version/*.log .\
\
saracheng@wireless-10-146-149-46:~/Documents/Research_Spring_2017/02_01_17_RNA_G4_mapping_to_cg_and_minimization/analyze_results_pre_post_RNA_G4_minimization$ scp -rp syc384@bme-venus.bme.utexas.edu:/home/syc384/02_01_17_RNA_G4_CG_conversion/analyze_results_min_CG_RNA_G4_log_files_pm_version/*.log \
\

\f0\b0 Extracted CGHBOND terms from minimized RNA G4\'92s
\f1\b \
\
\pard\tx560\tx1120\tx1680\tx2240\tx2800\tx3360\tx3920\tx4480\tx5040\tx5600\tx6160\tx6720\pardirnatural\partightenfactor0

\fs30 \cf0 grep ' Energy CGHBOND' min_2kbp_CG_analyze_pm.log\
grep ' Energy CGHBOND' min_2kbp_CG_analyze_pm.log > hbonds_min_2kbp_CG_analyze_pm.txt\
grep ' Energy CGHBOND' min_3ibk_CG_analyze_pm.log > hbonds_min_3ibk_CG_analyze_pm.txt\
grep ' Energy CGHBOND' min_2m18_bottom_CG_analyze_pm.log  > hbonds_min_2m18_bottom_CG_analyze_pm.txt\
grep 'CGHBOND' min_2m18_top_CG_analyze_pm_rms_grad_per_atom_0pt5.log > hbond_min_2m18_top_CG_analyze_pm_rms_grad_per_atom_0pt5.txt\
grep \'92CGHBOND' min_1my9_CG_analyze_pm.log > hbond_min_1my9_CG_analyze_pm.txt 
\fs34 \
\
\
\

\fs30 \
\pard\tx560\tx1120\tx1680\tx2240\tx2800\tx3360\tx3920\tx4480\tx5040\tx5600\tx6160\tx6720\pardirnatural\partightenfactor0

\fs34 \cf0 \
}
