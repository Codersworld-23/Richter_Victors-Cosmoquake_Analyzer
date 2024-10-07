# Cosmoquake Analyzer Algorithm

The **Cosmoquake Analyzer Algorithm** is an innovative approach for analyzing extraterrestrial seismic activity. It addresses the limitations of traditional STA/LTA (Short Term - Long Term) algorithms by significantly reducing the data size, improving feature extraction, and enhancing the classification of rare seismic events like shallow quakes. The solution applies both signal processing and machine learning techniques to tackle this challenge, making seismic event analysis faster and more efficient.

## Description

Extraterrestrial seismic events are challenging to process due to the sheer volume of data they generate. Traditional STA/LTA algorithms, while effective in detecting seismic waves, produce data that is difficult to handle, process, and transfer. Our **Cosmoquake Analyzer Algorithm** addresses these challenges by:

1. Identifying the arrival time and extent of aftershock waves using the traditional STA/LTA method.
2. Focusing only on the relevant data between seismic events.
3. Applying a Fourier transform to calculate absolute velocities and corresponding frequencies, discarding irrelevant data such as negative frequencies.
4. Extracting key features like maximum velocity, frequency-weighted velocity, mean velocity, frequency of maximum amplitude, and area under the curve.

This drastically reduces the data size while retaining valuable information for analysis.

## Significance

The identification and classification of seismic events are crucial for understanding the internal structures and geophysical phenomena of extraterrestrial bodies, particularly rare shallow quakes that provide insights into planetary activities. The Cosmoquake Analyzer helps overcome the following challenges:

- **Data transfer issues**: Reducing data from gigabytes to kilobytes makes it manageable.
- **Class imbalance**: Seismic datasets often contain an imbalance between rare and common events, which we address with machine learning techniques.
- **Simplification of analysis**: Despite complex data, our approach uses a Random Forest Classifier fine-tuned with boosting, making it more efficient than previously complex models.

## Novelty of Our Solution

The key innovations of the Cosmoquake Analyzer include:

1. **Data reduction and Feature Engineering**: Traditional methods generate overwhelming amounts of data. We reduce this by focusing only on the data between seismic events and applying a fast Fourier transform and consecutive feature engineering to extract relevant features. The data size can be reduced from 1.38GB to mere 9.06 kilobytes which is reduction of data to about 0.000613% of the original. This facilitates easy transfer of data which was a key challenge.
   
2. **Random Forest Classifier with boosting**: Unlike typical seismic analysis approaches that rely on complex models, we use a Random Forest Classifier, which is simpler but still powerful when combined with boosting techniques. This approach ensures the classification of seismic events, including rare shallow quakes, with high accuracy.
   
- It does not assume any data distribution and can handle non-linearity effectively.
- The bootstrapping allows sufficient training over rare examples.
- It is resilient to over-fitting.
- Does fast predictions in O(logn) time.
- It is easy to store and deploy.
- It can do feature selection on its own, eliminating any irrelevant statistical fallacy on its own.
- This does not consume a lot of computational power and energy like artificial neural networks which is limited for extraterrestrial systems which have to work in harsh environment.

3. **Using the Aftershock waves**: The aftershock waves of a seismic event give a lot of information of planetary signature and impact of the event on the given celestial body. For example a meteor hit, on the Moon shall be more significant as a seismic event than on the Mars. We used them to calculate the strength of the quake.


# Repository Flow
## Resources folder
It is added for reference of the resources provided in the problem, though lunar data could not be uploaded due to file size constraints.
## Main folder
This holds our actual solution, and its usage is as follows:
### Files

- `Moonquakes.csv`: Sample custom training data generated from NASA's Apollo mission data (post feature engineering).
- `moonquake_model.joblib`: Pretrained Random Forest Classifier model.
- `Training and preparation code.ipynb`: Notebook containing the source code for training the model.
- `Testcaseandinputprocess.ipynb`: Notebook containing the final code for testing and predicting seismic events using preprocessed test files.


## Usage

### Training the Model

1. Add the data folder provided in the resources is added to the directory as the training code.
2. Run the `Training and preparation code.ipynb` notebook to preprocess the data and train the model.
3. The trained model will be saved as `moonquake_model.joblib`.

### Testing the Model

1. Place your test data in both `.csv` and `.mseed` formats by naming them `testit.csv` and `testit.mseed`.
2. Run the `Testcaseandinputprocess.ipynb` notebook to preprocess the test files and predict the class of moonquakes.

## Working

The algorithm uses the following steps:

1. **STA/LTA Detection**: Traditional seismic analysis algorithms are used to detect the arrival and extent of aftershocks.
2. **Fourier Transform**: Converts seismic data into the frequency domain, discarding irrelevant negative frequencies and keeping only the useful data.
3. **Feature Extraction**: Key features such as max velocity, frequency-weighted velocity, mean velocity, and area under the curve are extracted to reduce data size.
4. **Classification**: A Random Forest Classifier with boosting is used to classify the seismic events, with a focus on rare cases like shallow quakes.

## Possible future additions:
1. Integration of a seismic wave measuremnt based activation function into the nodes of decision tree, and customisation of it.
2. Solving the epicenter location problem. As we can't know the epicenters of the seismic events easily on the celestial body, the true magnitude cannot be assesed. It can be done in future using a satellite monitoring system integrated to provide data of distance from epicenter to detector. Then the logarithm of this distance can be used to get the true assesment of strength on standard scale.

