<h1> Solution Description</h1>

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

1. **Data reduction**: Traditional methods generate overwhelming amounts of data. We reduce this by focusing only on the data between seismic events and applying a Fourier transform to extract relevant features. The data size can be reduced from 1.38GB to mere kilobytes.
   
2. **Random Forest Classifier with boosting**: Unlike typical seismic analysis approaches that rely on complex models, we use a Random Forest Classifier, which is simpler but still powerful when combined with boosting techniques. This approach ensures the classification of seismic events, including rare shallow quakes, with high accuracy.

## Installation

To run this project locally:

1. Clone the repository:
    ```bash
    git clone https://github.com/username/cosmoquake-analyzer.git
    ```

2. Place the `Moonquakes.csv` data file and model files (`moonquake_model.joblib`) in the same directory as the source code.

3. Install the necessary dependencies:
    ```bash
    pip install -r requirements.txt
    ```

4. Ensure the data folder provided in the resources is added to the directory for proper training and testing.

## Usage

### Training the Model

1. Add the provided data folder containing `Moonquakes.csv` to the same directory as the training code.
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

## Files

- `Moonquakes.csv`: Sample custom training data generated from NASA's Apollo mission data (post feature engineering).
- `moonquake_model.joblib`: Pretrained Random Forest Classifier model.
- `Training and preparation code.ipynb`: Notebook containing the source code for training the model.
- `Testcaseandinputprocess.ipynb`: Notebook containing the final code for testing and predicting seismic events using preprocessed test files.

## Contributing

Contributions are welcome! If you'd like to contribute to this project, please follow these steps:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -m 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a pull request.

