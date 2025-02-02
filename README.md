# Reproducibility README file

This file contains instructions on how to run the current code and to reproduce the models by retraining them. There are 2 portions of code, the one for training the models and the one to run and use them with the UI. The code for both parts is available on the Github repo links below and are public to view, download and clone. The models as well as the data is available on Zenodo to view and download for public use.

# Links:

-   [Training Code (Full Training Workspace Including Jupyter Files)](https://github.com/ameibrahim/ITICK)
-   [Frontend Code (Web UI)](https://github.com/ameibrahim/TicksApp)
-   [Jupyter Files for A](https://zenodo.org/records/14770030)
-   [Jupyter Files for B](https://zenodo.org/records/14770227)
-   [Dataset for A](https://zenodo.org/records/14353933)
-   [Dataset for B](https://zenodo.org/records/14770000)

The project entails tick detection, and how to spot dangerous ticks from harmless ones. The 2 types that were chosen for this project were Hyalomma and Rhipicephalus because they were native and common in Dogs in North Cyprus which was where this study was conducted.

The process to create a detector that could figure out which tick was dangerous was to:

1. Gather images of dangerous ticks
2. Use the images to create accurate models that could predict if those ticks were the ones or not
3. Create a UI that could easily reach the models and perform the prediction

To reproduce said result and accuracies from this study you do need a powerful computer with high GPU and RAM. These models were all trained on paperspace on a linux machine that boasted around 96GB RAM. The editor used to run the jupyter notebooks `.ipynb` files was Visual Studio Code. Apart from this, the only other software required are the libraries needed to train the models which are python libraries fro machine and deep learning contained in the `requirements.txt` file.

# Training the models

To train the models you need to ensure that:

1. You have the images downloaded and placed directly where you will run your jupyter files into a folder called dataset
2. Ensure the images are split in the dataset into 3 folders called train, dev and test. This can be done by running the `imageSplitter.py` file if required. Inside this file you can customise the split ratio. Splitting the dataset manually was a personal choice as I didn't want to accidentally change the ratio while running different iterations or training different architectures. To consolidate the images back into the main dataset folder, undoing the split, you can run `moveImagesToMainFolder.py`. This will let you resplit the dataset to your own desired ratios.
3. Play the jupyter files files one block at a time
4. Collect the models at the end. Ensure the filenames are valid Keras files `.keras`

# The UI

The webUI is there to complement the study and make it easy for the user to interact with models, without having to directly pass the image using console based methods. The models are housed under API calls in python that are consumed in a frontend built by HTML + PHP + JavaScript + CSS. An SQL file is included as a file called `aiiovdft_tickprediction.sql`, as a simple login feature was made to not allow random people to use the system. The database also saves recent predictions. The database used was MySQL.

The code for the webUI is avaialble and can be editted as desired, but there are no parameters to tweak, No changes from the frontend enhance the models in any way. The models results are independent from the frontend. _The only thing that can change the models result is the quality of the image uploaded._
