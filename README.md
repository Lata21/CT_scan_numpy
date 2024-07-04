# CT_scan_numpy
Import Dependencies
•	Numpy
•	Matplotlib
•	Seaborn
•	Requests
•	Imageio
•	Skimage
Retrieve Data and Unpack to NumPy Array
1.	Use requests to fetch the zip archive from the website where it is store.
2.	Unpack the content of the request to a BytesIO file-like object and initialize a ZipFile instance so that it can be read and its contents accessed.
3.	Once the data has been unpacked from the ZipFile, we use imageio to load raw pixel data to a NumPy array as part of a comprehension.
1.	Within the comprehension we iterate over the names of the files, which we retrieve using namelist
2.	We then retrieve a file-like object using the open method of the zip file archive ct_fdata that can be read by imageio.imread.
Visualize CT Scan
Once the image data has been loaded, a good next step is to inspect the data and make decisions about what processing is done.

Image Series

To visualize a series of CT images and ensure uniformity across the stack, you can create a panel plot. This plot will help you quickly inspect the images side-by-side. Here’s how you can do it using a helper method in Python:
1.	Prepare the Data: Load your CT scan series into a NumPy array.
2.	Create the Helper Method: Define a function that creates a panel plot.
3.	Parameters:
o	sstep: Step size to sample images from the series.
o	fcols: Number of columns in the panel plot.
o	frows: Calculated as the number of rows based on the series size and number of columns.
4.	Plot the Images: Use matplotlib to create subplots and display each image in grayscale.






