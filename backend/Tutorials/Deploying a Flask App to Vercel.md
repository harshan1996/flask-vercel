
# Deploying a Flask App to Vercel
Below is the quick overview of deploying a Flask app on [vercel](https://vercel.com/)





##  Getting Started
You can deploy your projects to Vercel in four different ways:

* Git
* Vercel CLI
* Deploy Hooks
* Vercel API

In this section we will be discussing about the beginner-friendly one i.e deploying from the [GitHub](https://github.com/) repository.




## Deployment

After the GitHub repository is successfully setup, we are now ready to deploy.

### Step-1
* Create an account on [vercel](https://vercel.com/) 


### Step-2
* Click on ```Add New``` and from the drop-down list select ```Project```

### Step-3
* Connect your GitHub account by using ```Add GitHub Account```.
* Alternatively you can use the third party GitHub repository URL for the Deployment using ```Import a Third-Party Git Repository``` option.

### Step-4
* After the login, click ```Add GitHub account``` and scroll down to the ```Repository access``` section and select the repository and click ```save``` thereby you can view the repository on vercel.
* Make sure the name of the python run file is ```index.py```.
* Given below is the sample repository to be deployed currently.

```
GitRepository/
|
|-- backend-flask/
|   |-- index.py
|   |--__init__.py
|   |--Cors.py
|   |--views.py
|   |--vercel.json
|   |--requirements.txt
|   |--README.md
```
* ```__init__.py``` and ```vercel.json``` are required for the deployment.```__init__.py``` can be an empty file but the contents of ```vercel.json``` are as follows for this particular example:
```
{
    "version": 2,
    "builds": [
        {
            "src": "./index.py",
            "use": "@vercel/python"
        }
    ],
    "routes": [
        {
            "src": "/(.*)",
            "dest": "/"
        }
    ]
}
```

### Step-5
* Click ```import``` option and in the ```Configure Project``` section you can see that the ```main/master``` is up for the production.If you intend to know how to change it,check [Custom Production Branch](#custom-production-branch)
* You can change the ```PROJECT NAME``` if you wish or you can leave it as such.
* But in the ```ROOT DIRECTORY``` make sure the folder which consists of ```index.py``` is selected.
* In this example ```GitRepository``` by default is the root folder and that need to be changed to ```backend-flask``` because that is where the python run file ```index.py``` is located.So click the ```Edit``` button and select the ```backend-flask``` folder.

### Step-6
* Click ```Deploy``` and then the app would be successfully deployed and deployed URL can be viewed there and would also be sent to your Gmail account.

## Custom Production Branch

* In order to make any branch as ```production branch```, go to the ```Project Settings``` and click ```Git``` then in the ```Production Branch``` type the name of the branch which is present in the Git repository and click ```save```.
* Optionally a similar kind of settings can be found in the ```Domains``` section under the ```Project Settings``` which you can explore.
