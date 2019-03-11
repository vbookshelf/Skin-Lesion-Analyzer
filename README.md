
Live Web App: http://skin.test.woza.work/

This is a prototype for a freely available online tool that can tell doctors and lab technologists the three highest probability diagnoses for a given skin lesion. It could help them quickly identify high risk patients and speed up their workflow. The app will produce a result in less than 3 seconds. To ensure privacy, user submitted images are pre-processed and analysed locally and are never uploaded to an external server. 

This app is powered by Artifical Intelligence. My goal for this project was to build an end to end solution - starting with model creation and ending with a live web app. Users are able to submit a picture of a skin lesion and get an instant prediction. 

The app is able to classify 7 types of skin lesions as described in this paper:

The HAM10000 Dataset: A Large Collection of Multi-Source Dermatoscopic Images of Common Pigmented Skin Lesions<br>
https://arxiv.org/abs/1803.10417


The entire model building and training process is described in this Kaggle kernel:<br>
https://www.kaggle.com/vbookshelf/skin-lesion-analyzer-tensorflow-js-web-app

The python code to build and train the model is included in the Jupyter notebook. All the javascript, css and html files are also freely available here. The trained model is also available.


<hr>


<b>How to Run This Project</b>

In order the run this project you will need to set up a web address and then upload files to it as you would do when building a website. 

These are the steps:

1. Set up an account with an internet service provider (ISP). I use <a href="https://www.dreamhost.com/r.cgi?2163352">Dreamhost</a> but there are many others you can use depending on your needs and budget.
2. Register a domain name like mywebsite.com. There is an annual cost for this but some ISP’s will give you your first domain for free.
3. You can upload the files to this domain or you could create a sub-domain like: skinproject.mywebsite.com. The good thing about sub-domains is that they can be set up for free, depending on your ISP. This helps if you have many personal web project ideas that you want to implement. On this project, skin.test.woza.work is actually a subdomain of woza.work.
5. Upload the files to the web address you have created. Your ISP will have specific instructions on how to do this. For example, on Dreamhost the HTML file of the main page has to always be named index.html. These are the files and folders from this repo that you should upload to your site:<br>

- index.html<br>
- assets (folder)<br>
- jscript (folder)<br>
- final_model_kaggle_version1 (folder)<br>
- robotfavicon.png (Stored in assets folder. Not essential.)<br>

5. After you have finished uploading the files and folders type your website address in your browser and go to your site. It should look and work just like mine does. I must be honest, the first time you set up a website can sometimes be a frustrating process. But persevere because it always works in the end - after some hair pulling and a few tears.


Please take note that if you add a security certificate to your website to make it an https site,  this security feature may block the model from automatically downloading when a user visits your website. 


<hr>

<b>Bugs & Lessons Learned</b>

1. If the model is not loading into your website:<br>
If you uploaded the model using FileZilla then the default transfer setting may need to be changed.<br>
Go to Settings->Transfers->File_Types and set the default transfer type to Binary.<br> 
Then upload the model to the server again.

2. When trouble shooting your website ensure that your browser is in "Incognito" mode. Otherwise it will load the model (and site) that is stored in the cache and you will not be looking at the latest version of the model.

3. Create the model in Keras and convert it to Tensorflow.js without first saving it. If you save it, load a saved model then convert - the model may not work when loaded into your site.

4. A converted tf.keras model does not work when loaded into at the app. A native Keras model must be used. When I say, 'does not work' I mean that either the model will not load into the app or if it loads, it will not output a prediction.

5. Another complication - If you don't use tf.keras then the accuracy as calculated from the confusion matrix will not match the accuracy obtained during training and evaluation. I think there is a problem with predict_generator() in native Keras - or maybe I'm using it wrong.

6. The app does not work in OSX Safari. It's best to use the latest version of Chrome. When developing Tensorflowjs based apps browser support needs to be kept in mind.







