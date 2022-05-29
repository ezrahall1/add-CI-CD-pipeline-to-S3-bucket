<h1>Add CI/CD pipeline to an Amazon S3 bucket</h1>

<h2>Description</h2>
This project will demonstrate how to host a dedicated Jenkins Server on Amazon EC2.
Jenkins is an open-source automation server that integrates with a number of AWS services, such as AWS CodeCommit, AWS CodeDeploy, Amazon EC2 Spot, and Amazon EC2 Fleet. 
<br />


<h2>Services Used</h2>

- <b>S3</b>
- <b>AWS CodePipeline</b> 
- <b>AWS CodeStar</b> 

<h2>Environments Used </h2>

- <b>AWS</b>
- <b>GitHub</b>

<h2>Program walk-through:</h2>
<H3>Step 1 - Create S3 bucket and upload content</H3>

Once you have log into the AWS account you would need to click on services>S3>click on create bucket. Make sure the bucket name is unique or you would not be able to create the bucket successfully. 
<img src="https://i.imgur.com/RhbERL9.png" height="80%" width="80%" alt="Image 1"/>

Scroll down and untick block all public access. This is a safety feature of S3, but because you are intentionally creating a S3 bucket to be used as a static website, you need to untick this box. Unticking this box means that you will be able to grant public access. It does not mean that public access is granted automatically.
<br />
<br />
<img src="https://i.imgur.com/YLFvbiO.png" height="80%" width="80%" alt="Image 2"/>
<br />
<br />
Tick the acknowledge box to show that you understand the changes you are making. <br/>
<img src="https://i.imgur.com/vn34t2z.png" height="80%" width="80%" alt="Image 3"/>
<br />
<br />
Leave everything else as default scroll to the bottom and click create bucket. <br/>
<img src="https://i.imgur.com/OlsCav4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<H3>Step 2 – Enable static website hosting </H3>
Click on the name of your bucket, then click on properties scroll down to the bottom where it says static website hosting and click on edit. Click on enable and make sure host a static website is selected.
<img src="https://i.imgur.com/D92cAzu.png" height="80%" width="80%" alt="Image 4"/>
<br />
<br />
In the index document section make sure you have added index.html, click save changes.
<img src="https://i.imgur.com/rxIz3fn.png" height="80%" width="80%" alt="Image 6"/>
<br />
<br />
Scroll down to static website hosting section and make a note of your bucket URL.
<img src="https://i.imgur.com/evbIuxh.png" height="80%" width="80%" alt="Image 7"/>

The next step is to upload some objects to the bucket you have created. In order to do that you would need to scroll to the top of the page and click on objects, then click on upload.

<H3>Step 3 – Grant permissions</H3>
The next step is you need to grant permissions to be able to read these objects. You would need to create a bucket policy. Click on the permission tab scroll down to where is says bucket policy click on edit. When entering the policy details remember to update the arn so it is not the same as mine or else it would not work, click on save changes.
<img src="https://i.imgur.com/ZGf2dE6.png" height="80%" width="80%" alt="Image 9"/>
Based on the policy you have created you will now see a red banner stating, “publicly accessible”, which means the bucket can be access by anyone.

<img src="https://i.imgur.com/h4Twv3G.png" height="80%" width="80%" alt="Image 10"/>

<H3>Step 3 – Create a pipeline</H3>
From there you would need to go to  AWS CodePipeline. Choose Create pipeline and enter a name for the project, select new service role and click next

<img src="https://i.imgur.com/bBBnpE1.png" height="80%" width="80%" alt="Image 10"/>

For the source provider choose GitHub (Version 2) from the list of source providers and connect to that GitHub. (Authorize GitHub to grant CodePipeline access to your GitHub repository)

<img src="https://i.imgur.com/Md4RE1T.png" height="80%" width="80%" alt="Image 11"/>

Create a connection to GitHub in GitHub connections
<img src="https://i.imgur.com/k0EIEYL.png" height="80%" width="80%" alt="Image 12"/>


Click on Install a new app.

<img src="https://i.imgur.com/AGKDv4q.png" height="80%" width="80%" alt="Image 12"/>


Select which repository you would like to use and click save

<img src="https://i.imgur.com/oDz8HR1.png" height="80%" width="80%" alt="Image 13/>


</p>


