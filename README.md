# OCNC_tutorial_optinist
This repository provides instructions for the preparation for the Optinist tutorial at OCNC2025. Please download the Docker image for the Optinist tutorial and make sure it opens correctly.

In addition, please download sample files from this [link](https://drive.google.com/drive/folders/1l5wFz3G5jn96h2uHZ0c6-LPEE04Ag-c2?usp=sharing)


## preparation
<br>

1. start the Docker Desktop application.<br>
   (For M1/2 Mac users, make sure 'Rosetta for x86_64/amd64 emulation on Apple Silicon' is checked in the settings for Docker Desktop. )
<br> 

3. Open a Terminal/Command prompt/PowerShell and execute the following to fetch the Docker image.

```
docker pull oistncu/optinist-allinone
```
<br>

3. Create and run the container by the following command.
```
docker run -it --shm-size=2G -v YOURSAVINGDIRECTORY:/app/studio_data --env OPTINIST_DIR="/app/studio_data" --name optinist_container -d -p 8000:8000 --restart=unless-stopped oistncu/optinist-allinone:latest poetry run python main.py --host 0.0.0.0 --port 8000
```

- The `-v` option in docker run mounts a path from the host to a path in the container. 
Substitute `YOURSAVINGDIRECTORY` to your own path. 
For example, `C:/tmp`(in Windows) or `/tmp` (in Mac) will assign the temporary directory of the host.  


- The container automatically starts optinist. When the initialization is finished, they show the logs like this.

<img src="/Figures/InitializationLog.png" width="80%">
<br>

4. After you see the logs, open a web browser ([Google Chrome](https://www.google.com/chrome/) is recommended) and go to http://localhost:8000.

- If you see this, you have successfully launched the application.

<img src="/Figures/FrontPage.png" width="50%">
<br>
<br>
<br>


## trouble shooting
<br>
Issue: The Docker container seems to be working, but http://localhost:8000 does not show the front page of OptiNiSt.<br>
Solution: Try using 127.0.0.1 instead of localhost.<br>
<br>



## other information mentioned in the tutorial

### OptiNiSt
- [documentation](https://optinist.readthedocs.io/en/latest/ )
- [gitub repository](https://github.com/oist/optinist)
- [paper](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1013087#sec015)

### NWB
- [project](https://www.nwb.org)
- [NWB software](https://nwb-overview.readthedocs.io/en/latest/index.html)
- [HDF view](https://www.hdfgroup.org/downloads/hdfview/)

### cell detection algorithms
&emsp; suite2p &emsp;[website](https://suite2p.readthedocs.io/en/latest/index.html)&emsp;[github repository](https://github.com/MouseLand/suite2p) &emsp; [paper](https://www.biorxiv.org/content/10.1101/061507v2)<br>
&emsp; CaImAn &emsp;[website](https://caiman.readthedocs.io/en/latest/) &emsp;[github repository](https://github.com/flatironinstitute/CaImAn)&emsp;[paper](https://elifesciences.org/articles/38173)<br>
&emsp; lccd &emsp;[gitub repository](https://github.com/magnetizedCell/lccd-python)&emsp; [paper](https://www.sciencedirect.com/science/article/pii/S016801022200075X)<br>
  



