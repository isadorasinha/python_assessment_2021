# python_assessment_2021
# MRI Neuroimaging Data Exploration and Masking with NiBabel and Nilearn - Isadora Sinha

This code is written in Python and is meant for the purpose of preliminary exploration of MRI data. It utilises the Nibabel and Nilearn packages to access and process NIfTI data and masking files of MRI neuroimaging data.

The code is in a Jupyter Notebook so simply open it using Anaconda and run each block in order (you will need Python3 and Anaconda pre-installed on your local drive). 

Example data 1 is from: https://www.fmrib.ox.ac.uk/primers/intro_primer/ExBox14/ExBox14.zip
This example data contains 3 NIfTI files: the original MRI data, the MRI data of just the brain and a file of the mask. The file names are listed as T1.nii , T1_brain.nii and T1_brain_mask.nii.

TO USE THE ExBox14 FILES EITHER DOWNLOAD FROM ABOVE LINK AND UNZIP THE FILE OR DOWNLOAD AND UNZIP FILES FROM THIS GITHUB REPOSITORY. THEN MOVE THE RESULTING FILES TO THE DESIRED LOCATION ON YOUR LOCAL DRIVE, THEN SPECIFY THE LOCATION IN THE FOUR POINTS IN THE SCRIPT THAT HAVE THE HARD CODED FILE PATH FOR THE EPI BRAIN IMAGE, HEAD IMAGE AND THE MASK. 

First, the example data file's image is explored (voxel dimensions and data type) then the image data itself was loaded using NiBabel. Following this, the image data dimensions are checked to ensure it matches the image dimensions. Nilearn is used to plot the epi images (epi=echo-planar imaging). As 3D data can be difficult to manipulate, the code also turns the 3D epi data into a 2D array which can be taken on further for easier data analysis. The mask data file is then loaded, checked and set to boolean. The mask is then applied to the example data by indexing and the result is plotted. Next, the example dataset is used to visualise volumes and generate a mask.

Example dataset used in the code is from: 
http://data.pymvpa.org/datasets/haxby2001

The Haxby dataset (Haxby et al. 2001) is downloaded and the locations of the dataset on your local drive are printed. A mean image is generated from the dataset's epi images and plotted using Nilearn - mean is taken of axis 3 of all the epi's (axis 3 = time).

Nilearn then generated a mask for the Haxby dataset. This is also plotted to show the region of interest (ROI). The code then applies the mask to the dataset using Nilearn (rather than applying by index as previously done). The dimensions of the resulting 2D object is displayed then a plot the first 500 timepoints from 5 voxels is generated. The parameters of the plot can be altered to display n number of timepoints for n voxels as desired by editing this line in the code: plt.plot(masked_data[:500, :5]).


References:
Haxby, J., Gobbini, M., Furey, M., Ishai, A., Schouten, J., and Pietrini, P. (2001). Distributed and overlapping representations of faces and objects in ventral temporal cortex. Science 293, 2425-2430.
https://nilearn.github.io/modules/generated/nilearn.datasets.fetch_haxby.html
https://www.fmrib.ox.ac.uk/primers/intro_primer/ExBox14/IntroBox14.html
https://nipy.org/nibabel/nibabel_images.html
https://github.com/Brainhack-AMX/Brainhacking-101
