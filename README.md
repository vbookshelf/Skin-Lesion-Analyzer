
Live Web App: http://skin.test.woza.work/

This is a prototype for a freely available online tool that can tell doctors and lab technologists the three highest probability diagnoses for a given skin lesion. It could help them quickly identify high risk patients and speed up their workflow. The app will produce a result in less than 3 seconds. To ensure privacy, user submitted images are pre-processed and analysed locally and are never uploaded to an external server. 

This app is powered by Artifical Intelligence. My goal for this project was to build an end to end solution - starting with model creation and ending with a live web app. Users are able to submit a picture of a skin lesion and get an instant prediction. 

The app is able to classify 7 types of skin lesions as described in this paper:

The HAM10000 Dataset: A Large Collection of Multi-Source Dermatoscopic Images of Common Pigmented Skin Lesions<br>
https://arxiv.org/abs/1803.10417


The entire model building and training process is described in this Kaggle kernel:<br>
https://www.kaggle.com/vbookshelf/skin-lesion-analyzer-tensorflow-js-web-app

The python code to build and train the model is included in the Jupyter notebook. All the javascript, css and html files are also freely available here. The trained model is also available.



Bugs & Lessons Learned:

1. If the model is not loading into your website:<br>
If you uploaded the model using FileZilla then the default transfer setting may need to be changed.<br>
Go to Settings->Transfers->File_Types and set the default transfer type to Binary.<br> 
Then upload the model to the server again.

2. When trouble shooting your website ensure that your browser is in "Incognito" mode. Otherwise it will load the model (and site) that is stored in the cache and you will not be looking at the latest version of the model.

3. Create the model in Keras and convert it to Tensorflow.js without first saving it. If you save it, load a saved model then convert - the model may not work when loaded into your site.

4. A converted tf.keras model does not work when loaded into at the app. A native Keras model must be used. When I say, 'does not work' I mean that either the model will not load into the app or if it loads, it will not output a prediction.

5. Another complication - If you don't use tf.keras then the accuracy as calculated from the confusion matrix will not match the accuracy obtained during training and evaluation. I think there is a problem with predict_generator() in native Keras - or maybe I'm using it wrong.








