# De-Mystifying ML Analyze large datasets of digitized measurements of individual DNA molecules behaviour. 

1. Magnetic tweezers MT data; methylated vs control DNA.
2. Clean csv/excel files. Magnet position(x) to Force F (y). numpy, scipy
3. Normalize DNA length by dividing to max length. Calculate normalized DNA length (mean and stdev) for every change in Force and
rotation. Calculate 1/SQRT(F) (pandas and matplotlib).
3. Built the linear regression for each experiment to retrieve the DNA persistence length (slope^2)
4. Combine experiments either by combining multiple datasets or combining regression models(partial least square regression 
https://stats.stackexchange.com/questions/235577/combining-multiple-datasets-vs-combining-regression-models).
For combined data: I did a standard linear regression and then compared other machine learning aglorithms in Python's scikit
learn libraries including support vector regression and random forest regression
5. Built linear regression graphs (combined experiments) for methylated and control DNA and statistic.
6. Does machine learning models (combine data from multiple experiments, divide to training and testing sets) correspond to my previous calculations?
