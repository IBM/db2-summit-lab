# Refresh Db2 Development Lab

To refresh the Db2 Development lab, make sure that you are using the VM Console and have opened a terminal window.

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

!!! abstract "Open the new Table of Contents"
    <a href="http://localhost:8888/notebooks/Table_of_Contents.ipynb"_blank">Table of Contents</a>

The password is `kubernetes`.

Your screen should like this.

![Browser](wxd-images/table_of_contents.png)

Click on the Db2 Development with Db2 Magic Commands arrow to display the lab exercises for the workshop.
