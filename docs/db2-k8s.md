# Refresh Db2 in a Kubernetes Lab

To refresh the Db2 Kubernetes lab, make sure that you are using the VM Console and have opened a terminal window.

![Browser](wxd-images/vmware-terminal-window.png)

### Download the Latest Lab Contents

This will place the file into the Download directory of the k8s user.

!!! abstract "Download latest notebooks" 
    [Latest Lab Material](https://github.com/IBM/db2-summit-lab/raw/main/notebooks.zip)

!!! abstract "Recreate the notebook directory"
    ```bash
    sudo systemctl stop jupyter-notebook
    rm -rf ~/notebooks
    unzip ~/Downloads/notebooks.zip
    sudo systemctl start jupyter-notebook
    ```

### Update the Kubernetes Cluster Certificates

!!! abstract "Switch to the Root user"
    ```bash
    sudo su -
    ```

!!! abstract "Update Certificates in the Cluster"
    This command takes approximately 1 minute to complete.
    ```bash
    microk8s refresh-certs
    ```

!!! abstract "Exit from being the Root user"
    ```bash
    exit
    ```

!!! abstract "Update local and remote connection settings"
    ```bash
    microk8s config > config
    cp config ~/.kube/.
    rsync -r config db2inst1@10.0.0.1:/home/db2inst1/.kube/
    rsync -r config db2inst2@10.0.0.1:/home/db2inst2/.kube/ 
    ```

### Open the Table of Contents
    
!!! abstract "Open the Table of Contents"
    <a href="http://localhost:8888/notebooks/Table_of_Contents.ipynb" target="_blank">Table of Contents</a>

The password is `kubernetes`.

Your screen should like this.

![Browser](wxd-images/table_of_contents.png)

Click on the Db2 in a Kubernetes Environment arrow to display the lab exercises for the workshop.