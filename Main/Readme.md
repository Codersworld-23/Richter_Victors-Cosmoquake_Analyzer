<h1> Solution Description</h1>

The traditional method of analysis of extraterrestrial seismic activity is to use the  STA/LTA(Short term- Long term algorithm).
The problem with it is that is generates a large amount of data that is quite difficult to handle, process, analyze and transfer. ​
The cosmoquake analyzer  algorithm solves this problem by taking a unique approach. 
It first of all finds out the arrival time and extent of aftershock waves of the given seismic data using the traditional STA/LTA approach and then  takes the data between these events only. ​
Then it applies Fourier transform upon the data and generates the absolute values of velocities and corresponding frequencies. 
The negative frequency values are dropped out to get only the relevant part of the data. ​
This gives us the distribution of velocities over frequency and also provides us an estimate of the strength of the quake. 
This is because the strength of quake depends on both the amplitudes and frequencies. 
Then we extract the relevant features like max velocity, frequency weighted velocity, mean velocity, frequency of max amplitude and area under curve. ​
This allows analyzation of only the worthy data.​
Now as the data can contain rare cases of seismic events like shallow quakes, we approached the problem using a random forest classifier and fine-tuned it using boosting.


<h1> files:</h1>  
1.) Moonquakes.csv - This is a sample of our custom training data(Data generated after preprocessing and feature engineering from NASA apollo data)
2.) moonquake_model.joblib - Ml model used, based on random forest classifier
3.) Training and prepration code.ipynb - Model training source code
4.) Testcaseandinputprocess.ipynb - Final code having the function to preprocess test files and predict the class of moonquake.

<h1>Working:</h1>
To run the training code we need to add the data folder provided in resources in same directory as otherfile
To run the testing code we need to add the testing data in both .csv and .mseed format by the name (testit.csv, testit.mseed).
