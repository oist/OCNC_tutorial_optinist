# OCNC_tutorial_optinist
This repository provides instructions for the preparation for the Optinist tutorial at OCNC2024. Please download the Docker image for the Optinist tutorial and make sure it opens correctly.

In addition, please download sample files from this [link](https://drive.google.com/drive/folders/1SUy3GBltprKUOa_KNPqqevGGZURq6oEY?usp=sharing)


## preparation
1. start the Docker Desktop application.
    
2. Open a Terminal/Command prompt/PowerShell and execute the following to fetch the Docker image.

```
docker pull oistncu/optinist-allinone
```
  
3. Create and run the container by the following command.
```
docker run -it --shm-size=2G -v YOURSAVINGDIRECTORY:/app/studio_data --env OPTINIST_DIR="/app/studio_data" --name optinist_container -d -p 8000:8000 --restart=unless-stopped oistncu/optinist-allinone:latest poetry run python main.py --host 0.0.0.0 --port 8000
```

- The `-v` option in docker run mounts a path from the host to a path in the container. 
Substitute `YOURSAVINGDIRECTORY` to your own path. 
For example, `C:/tmp`(in Windows) or `/tmp` (in Mac) will assign the temporary directory of the host.  


- The container automatically starts optinist. When the initialization is finished, they show the logs like this.

![Alt text](/Figures/InitializationLog.png)

4. After you see the logs, open a web browser (Google Chrome is recommended) and go to http://localhost:8000.

- If you see this, you have successfully launched the application.

![Alt text](/Figures/FrontPage.png)


