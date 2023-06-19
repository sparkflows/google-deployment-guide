# Google Cloud Launcher

## Deploying
First off we're going to deploy a cluster.  That's really easy with Cloud Launcher.  Simply go to https://console.cloud.google.com/marketplace/product/sparkflows-public/fire-insights?project=sparkflows-public

![](images/gcp_image1.jpg)

Click "Launch"

![](images/gcp_launching_instance.jpg)

You can take the default settings or customize them.  When complete click "Deploy"

![](images/gcp_image3.jpg)

When complete you should see:

![](images/gcp_image4.jpg)

Once you have the instance up and running, you need to grab the external IP( lets say 192.xx.xx.xxx) and visit http://192.xx.xx.xxx:8080 to view the login screen.

## Generate and Configure Google service account JSON Key

In order to authenticate to the GCP services like GCS and BigQuery, you need to [generate](https://cloud.google.com/iam/docs/keys-create-delete#creating) and save the access key to the above VM created in the directory - `/home/sparkflows` with name as `sparkflows-key.json`. In order to switch to the `sparkflows` user in the VM, use the password `Sparklows`

Now edit the file `/home/sparkflows/fire.sh` and uncomment the line #5, where the variable `GOOGLE_APPLICATION_CREDENTIALS` has been exported. Save the file and restart the service using the below command: 

```
sudo systemctl restart fire.service
``` 

Now wait for 30 seconds, and visit the http://192.xx.xx.xxx:8080 url to access the login screen, with GCP support enabled.

## Create Dataproc Cluster with proper spark library dependency 

## Ensure proper roles assigned to the Dataproc Cluster to access BigQuery and GCS

## Configure Callback URL in Sparkflows

## Configure Dataproc Connection in Sparkflows

## Run a sample workflow to test the End-2-End Connctivity with GCS and Dataproc 

