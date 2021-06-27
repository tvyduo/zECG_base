# zECG_base

# Description
This repository contains a collection of adult zebrafish electrocardiogra (ECG) traces in support of Duong et. al. (2021). All 245 traces collected are provided for download.

Traces are contained within the `Traces` directory seperated by experiments as described in the manuscript (either phenotyping *kcnh6*-s290 (*s290.zip*), flecainide acetate dosing (*FA.zip*), consecutive traces recorded to examine variance (*timepoint.zip*), or other AB/wild-type fish used for model development (*Other WT.zip*). They are provided as .txt files within each zipped folder. Note that the set of *kcnh*-s290 traces are seperated into two sets for space-saving purposes.

The accompanying file, *zECG_Covariates_Dictionary.xlsx*, contains phenotype and a dictionary explaining the values and columns provided.

# Trace Recording Protocol
Briefly, we created a customized ECG recording apparatus specifically for use in recording zebrafish ECGs. This apparatus is composed of an electrode block containing two 29-gauge needle electrodes and a base, containing a well with a clay mold to hold the zebrafish and anesthesia in during recordings. The electrodes can be independently adjusted using dials on the electode block while the entire electrode block can also be adjusted on the Y- and X- axes to assist with electrode placement. Within the day prior to the ECG recording, we document the size parameters of the fish and gently use a scalpel to descale the area around its' heart; the fish are then individually housed until the recording is performed. On recording day, the fish is anethetized in tricaine and within the fish facility for optimum temperature control. After sufficient anesthetization, the fish is brought into the recording room and placed ventral side up on the mold in the well (which also contains warm tricaine). The electrodes are adjusted and inserted into the fish, with the positive immediately anterior/cranial to the heart and the neative caudal to the heart (the ground is placed in a sponge near the fish). There is an adjustment period (60-120s) where the electrodes are adjusted to ensure an optimum trace is recorded. Once the adjustment period is done, the trace is captured up to three minutes after. Once the recording is donw, the electrodes are removed and the fish is returned to the facility for recovery.

For a more detailed protocol description, please refer to the manuscript.

# Trace Recording Settings and Processing
ECGs were recorded in the 2 mV range at the rate of 2000 samples per seconds, employing the following hardware filters: a low-pass filter at 200 Hz, a 
high-pass filter at 1 Hz, and a mains filter; we refer to this as the ‘raw trace’. Additional digital low-pass (100 Hz) and high-pass (3 Hz) filters are applied to reduce noise within the trace; this is the final trace used for all downstream analyses in the manuscript.

# Trace Format
Traces are provided as Labchart formatted .txt files. This format is provided to ensure users who do not have access to a paid version of Labchart can access the data values. The first few lines are the trace header and contain the following metadata about the trace. The data portion of the trace is after the *Range* entry and contains three columns. Column 1 is the time (in s, as designated in the *Interval* header entry). The voltage values for the _**Raw**_ trace is contained in column 2 while the voltage values for the trace used for all downstream data analysis after being digitally filtered and processed is in column 3.

The total duration of the traces are approximately around three minutes. For traces that had an extensive adjustment period, the adjustment period(i.e. when the fish is initially placed on the block, when electrodes are adjusted, etc.) is not included in the .txt file. Additionally, traces where there is extensive recording time past three minutes and 15-30 seconds (i.e. traces were recorded longer than intended) were trimmed to only provide the portion of data considered as part of our protocol. Variables within the covariate file detail which traces had an adjustment period as well as information of total trace and collection procedure duration.

# How to Visualize the Traces
A quick and easy way to visualize the traces is to download Labchart Reader: https://www.adinstruments.com/products/labchart-reader. The .txt file can be directly opened into Labchart Reader (make sure *Labchart text file* is selected in the dropdown box next to *File name* when trying to open the file and *Times in first column* is checked in the pop-up). After importing the file, the data will be displayed as two seperate channels. Note that traces cannot be saved or converted into other formats using Labchart Reader.

# Conversion into Other Formats
Advanced users can edit the .txt files to remove the header and read the data into R, Matlab, etc.

Users who have access to a paid version of Labchart can use the above instructions in the prior section to read the trace into Labchart and convert the data into the Labchart specific file format (.adicht), .mat, or other available formats. For instructions on how perform this conversion, please refer to the Labchart user guide.

# Custom Zebrafish ECG Analysis Software
We created a MATLAB-based GUI for use specifically to analyze zebrafish ECG traces called zERG (**Z**ebrafish **E**CG **R**eading **G**UI). zERG can be found at: https://github.com/tvyduo/zERG. Labchart users can convert the .txt files into .mat files using a paid version of Labchart and then directly read the .mat files into zERG. To read the .txt files directly into zERG, remove the header(s) and ensure that only two columns are present: the times of the voltages (first column) and the voltages themeselves. zERG currently only supports the display of one channel of the trace (i.e. the raw data from channel 1 and the processed data from channel 4 cannot be analyzed using zERG at the same time).

# Citation
The manuscript associated with this work is currently in review. A proper citation will be provided at a later time. Please cite if you use any of these traces!

Duong T et al. Development and Optimization of an In Vivo Electrocardiogram Recording Method and Analysis Program for Adult Zebrafish. Manuscript submitted for publication.

# Contact
Please contact ThuyVy Duong at tvyduo@gmail.com for questions and/or assistance.
