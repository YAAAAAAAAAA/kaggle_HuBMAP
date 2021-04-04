# kaggle_HuBMAP

The Dataset
The dataset is comprised of very large (>500MB - 5GB) TIFF files. The training set has 8, and the public test set has 5. The private test set is larger than the public test set.

The training set includes annotations in both RLE-encoded and unencoded (JSON) forms. The annotations denote segmentations of glomeruli.

Both the training and public test sets also include anatomical structure segmentations. They are intended to help you identify the various parts of the tissue.

File structure
The JSON files are structured as follows, with each feature having:

A type (Feature) and object type id (PathAnnotationObject). Note that these fields are the same between all files and do not offer signal.
A geometry containing a Polygon with coordinates for the feature's enclosing volume
Additional properties, including the name and color of the feature in the image.
The IsLocked field is the same across file types (locked for glomerulus, unlocked for anatomical structure) and is not signal-bearing.
Note that the objects themselves do NOT have unique IDs. The expected prediction for a given image is an RLE-encoded mask containing ALL objects in the image. The mask, as mentioned in the Evaluation page, should be binary when encoded - with 0 indicating the lack of a masked pixel, and 1 indicating a masked pixel.

train.csv contains the unique IDs for each image, as well as an RLE-encoded representation of the mask for the objects in the image. See the evaluation tab for details of the RLE encoding scheme.

HuBMAP-20-dataset_information.csv contains additional information (including anonymized patient data) about each image.
