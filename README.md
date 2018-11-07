
Live Web App: http://skin.test.woza.work/

This is a prototype for a freely available online tool that can tell doctors and lab technologists the three highest probability diagnoses for a given skin lesion. It could help them quickly identify high risk patients and speed up their workflow. The app will produce a result in less than 3 seconds. To ensure privacy, user submitted images are pre-processed and analysed locally and are never uploaded to an external server. 

This app is powered by Artifical Intelligence. My goal for this project was to build an end to end solution - starting with model creation and ending with a live web app. Users are able to submit a picture of a skin lesion and get an instant prediction. 

The app is able to classify 7 types of skin lesions as described in this paper:

The HAM10000 Dataset: A Large Collection of Multi-Source Dermatoscopic Images of Common Pigmented Skin Lesions<br>
https://arxiv.org/abs/1803.10417


The entire model building and training process is described in this Kaggle kernel:<br>
https://www.kaggle.com/vbookshelf/skin-lesion-analyzer-tensorflow-js-web-app

The python code to build and train the model is included in the Jupyter notebook. All the javascript, css and html files are also freely available here. The trained model is also available.

I don't know how accurate the app is in practice. There's no way to field test it. I'll just leave it to roam around in the wild. Maybe someone will find it helpful.

