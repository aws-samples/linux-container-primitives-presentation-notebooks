## Linux Container Primitives presentation notebooks

This repository contains the Jupyter notebooks demonstrated during the "Linux Container Primitives and Runtimes" presentation at AWS Sydney Summit on Thursday May 2nd, 2019.

## Notes

These notebooks have been prepared to demonstrate interacting with cgroups, namespaces and overlay filesystems under Linux. 

The demonstrations are intended to run on a testing/development box. The notebooks include cleanup commands which may be destructive and should only be executed with care. 

***I recommend you launch a new instance to explore these notebooks with.***

## Installation

The notebooks have been developed and tested under Amazon Linux 2. The following packages are required in order to use the Notebooks:

- Docker
- Python 3
- Jupyter
- bash_kernel kernel for Jupyter
- jq

The following commands have been tested successfully to configure the host OS to be able to execute these notebooks:

~~~~
sudo yum install python3 python3-devel gcc jq docker git
pip3 install --user jupyter
pip3 install --user bash_kernel
python3 -m bash_kernel.install
sudo service docker start
sudo usermod -a -G docker ec2-use
~~~~

Clone this repository to the instance

~~~~
git clone https://github.com/aws-samples/linux-container-primitives-presentation-notebooks.git
~~~~

Log off and reconnect to the instance. 

To tunnel the notebook web server port (by default, TCP/8888) to your localhost, connect to the instance with a SSH tunnel configured on port 8888:

~~~~
ssh -L 8888:localhost:8888 ec2-user@<instance-address>
~~~~

Start Jupyter notebook server in the folder containing the notebook files:

~~~~
jupyter notebook .
~~~~

You will be presented with a URL to connect to the server via your web browser. From here you can load the notebooks and start experimenting!

## License Summary

This sample code is made available under the MIT-0 license. See the LICENSE file.
