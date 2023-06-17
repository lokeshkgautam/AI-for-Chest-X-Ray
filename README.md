
<img alt="" class="bg ly lz c" width="1200" height="613" loading="lazy" role="presentation" src="https://github.com/lokeshkgautam/AI-for-Chest-X-Ray/blob/master/FRT.jpeg">

# AI for Chest X-Ray

This is a Machine Learning Model for diagnosing Chest X-Ray for Pneumonia with two categories.

### Industry :
Healthcare

### Project Title :
Azure AI for Medical Imaging

### Problem Statement/Opportunity :
 AI to try to help diagnose lung diseases, such as viral pneumonia, and bacterial pneumonia.

### Project Description :
The content covers Azure Machine learning, Azure Cognitive service, and custom vision. Cognitive services provide machine learning capabilities. You don’t need special machine learning or data science knowledge to use these services. And I’ll share with you how to implement an image classifier for chest X-ray diagnosis with Azure AI. Azure Machine learning is very helpful for Data Science applications.
Now I will introduce how to build an image classifier for detecting viral pneumonia, and bacterial pneumonia with Azure AI.
#### A. Why Needs Detect Viral Pneumonia, and Bacterial Pneumonia With AI?
The world has changed due to the COVID-19 pandemic in 2020. Medical staff around the world have shown bravery and resilience in the fight against COVID-19, and some even sacrificed their lives while performing their duties. As an ordinary person, as a programmer, I also want to help. Therefore, using AI to try to help diagnose lung diseases, such as viral pneumonia, and bacterial pneumonia.
#### B. Azure Cognitive Servies
Azure is a cloud computing platform, it also provides AI services for developers. <a class="af nh" href="https://azure.microsoft.com/services/cognitive-services/" rel="noopener ugc nofollow" target="_blank">Azure Cognitive Services</a> is a comprehensive family of AI services and cognitive APIs to help you build intelligent apps.

<img alt="" class="bg ly lz c" width="700" height="313" loading="lazy" role="presentation" src="https://miro.medium.com/v2/resize:fit:700/0*bdKI4gBlw3pM3UQh.png">

<img alt="" class="bg ly lz c" width="1200" height="613" loading="lazy" role="presentation" src="https://github.com/lokeshkgautam/AI-for-Chest-X-Ray/blob/master/Cognitive%20Services.png">
Azure Cognitive Services contains many different types of AI services, such as Decision services, Language services, Speech services, Vision services, and Web search services.

What we need is an AI Vision service. By using Custom Vision services, we can identify and analyze attributes within images, videos, and digital ink. In order to train our own model, we can select the Custom Vision service of Vision services to customize image recognition to fit our needs.

### Create A Custom Vision Project and Get The Dataset :
The Custom Vision service provided by Azure provides us a user-friendly interface to develop and deploy custom computer vision models. In the following image, You can find the process of creating custom computer vision models that fit with our use case.

<img alt="" class="bg ly lz c" width="1200" height="613" loading="lazy" role="presentation" src="https://github.com/lokeshkgautam/AI-for-Chest-X-Ray/blob/master/Project%20create.png">

<img alt="" class="bg ly lz c" width="700" height="222" loading="lazy" role="presentation" src="https://miro.medium.com/v2/resize:fit:700/0*NYAjgfsFSRbqXYwq.png">

So, let’s create our Custom Vision Project and get a suitable dataset online.
<a class="af nh" href="https://www.customvision.ai/" rel="noopener ugc nofollow" target="_blank">Azure Custom Vision</a>

<img alt="" class="bg ly lz c" width="1200" height="613" loading="lazy" role="presentation" src="https://github.com/lokeshkgautam/AI-for-Chest-X-Ray/blob/master/Project%20setting%20page.png">

The first thing we need to do is to create a project on the Custom Vision site. We should identify the name of the project and create a new Azure Cognitive Services resource if there is no existing one. And there are two available options for Project Types, Classification, and Object Detection. In our case, we select the Classification type. The second thing is to look for a suitable dataset, the images to train our model later.
I will use the dataset from Paul Mooney, you can find it <a class="af nh" href="https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia" rel="noopener ugc nofollow" target="_blank">here</a>. There are 5,863 X-Ray images (JPEG) and 2 categories (Pneumonia/Normal) in the dataset.

<img alt="" class="bg ly lz c" width="592" height="195" loading="eager" role="presentation" src="https://miro.medium.com/v2/resize:fit:592/0*vq8n1mn9zKa-I0u5.png">

The normal chest X-ray (left panel) depicts clear lungs without any areas of abnormal opacification in the image. Bacterial pneumonia (middle) typically exhibits a focal lobar consolidation, in this case in the right upper lobe (white arrows), whereas viral pneumonia (right) manifests with a more diffuse ‘‘interstitial’’ pattern in both lungs.
Before training the models we need to upload a dataset of images, for that, we have to create a project & I have created a project by the name of Chest X-Ray (AI). Then inside project, we can see the option to add the images.

<img alt="" class="bg ly lz c" width="1200" height="613" loading="lazy" role="presentation" src="https://github.com/lokeshkgautam/AI-for-Chest-X-Ray/blob/master/Custom%20Vision.png">

##### Add Images :
In the images below click on the Add Image button.
<img alt="" class="bg ly lz c" width="1200" height="613" loading="lazy" role="presentation" src="https://github.com/lokeshkgautam/AI-for-Chest-X-Ray/blob/master/Add%20Imges.png">

##### Upload Images :
The upload option will come up after adding an image just like the below image. From here we can add a tag for the images & then click on the upload button. I used 3 types of images normal, viral & bacterial & add the tag accordingly for the classification purpose. It is a good idea to choose an appropriate number of images, so I chose about 35 images for each tag for training.
<img alt="" class="bg ly lz c" width="1200" height="613" loading="lazy" role="presentation" src="https://github.com/lokeshkgautam/AI-for-Chest-X-Ray/blob/master/Upload%20Images.png">

##### All Images :
We can see all uploaded images below images & select here as per the tag. From here we delete also.
<img alt="" class="bg ly lz c" width="1200" height="613" loading="lazy" role="presentation" src="https://github.com/lokeshkgautam/AI-for-Chest-X-Ray/blob/master/All%20Images.png">

##### Train the Model :
The train button will highlight once the upload is finished. The click on train button. Here are two options for the training of the model: Quick Training & Advanced training. I had used advanced training here.
<img alt="" class="bg ly lz c" width="1200" height="613" loading="lazy" role="presentation" src="https://github.com/lokeshkgautam/AI-for-Chest-X-Ray/blob/master/Train%20the%20model.png">

##### Result of Training :
After training the model finish & result windows will come as in the images below.
<img alt="" class="bg ly lz c" width="1200" height="613" loading="lazy" role="presentation" src="https://github.com/lokeshkgautam/AI-for-Chest-X-Ray/blob/master/Training%20Result.png">

##### Normal X-Ray :
After the training is over, we can see the results on the Performance page. In order to test this model, we can quickly test it via the Quick Test function on the site. This Quick test for the normal image & easy can checks the percentage of the normal condition of the X-Ray is higher. 
<img alt="" class="bg ly lz c" width="1200" height="613" loading="lazy" role="presentation" src="https://github.com/lokeshkgautam/AI-for-Chest-X-Ray/blob/master/Test%20the%20model%20for%20normal%20Pnemonia.png">

##### Viral Pneumonia X-Ray :
In the images below the percentage of the Viral X-Ray is higher as per the quick test.
<img alt="" class="bg ly lz c" width="1200" height="613" loading="lazy" role="presentation" src="https://github.com/lokeshkgautam/AI-for-Chest-X-Ray/blob/master/Test%20the%20model%20for%20viral%20Pnemonia.png">

##### Bacterial Pneumonia X-Ray :
In the images below the percentage of the Bacteria type X-Ray is higher as per the quick test.
<img alt="" class="bg ly lz c" width="1200" height="613" loading="lazy" role="presentation" src="https://github.com/lokeshkgautam/AI-for-Chest-X-Ray/blob/master/Test%20the%20model%20Bacteria%20Pnemonia.png">


### Primary Azure Technology :
Azure Cognitive Services, Custom Vision
 
