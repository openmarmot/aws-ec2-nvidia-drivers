# aws-ec2-nvidia-drivers
Example templates that demonstrate how to install Nvidia drivers on AWS EC2 GPU instances


I spent a lot of time getting the NVIDIA datacenter drivers working on AWS for a different project, so I 
thought I would release a simplified version on Github and hopefully help anyone else who was having trouble 
getting this working. I found google search to be just about useless when I was troubleshooting this - these solutions 
are a result of my own troubleshooting and trial/error combination of different sets of instructions.

Note - although the AL2 template is hacked together, the AL2023 template has a official NVIDIA repo so its actually quite good

### Important notes
- Different AWS instance types have different Nvidia graphic card types. Each type has its own drivers.
- The AWS gpu instances are very expensive. Make sure to become familiar with the costs before you launch one!

### cft-al2-p3-series.yaml
- Cloudformation template for Amazon Linux 2 on a p3.x instance type.
- This graphic driver is very tempermental. It seems to require very specific package versions
- test with the nvidia-smi cli command
- This install is specific to the NVIDIA card in the AWS P3 instance
- designed to use connect->session manager from the ec2 console to connect to the cli

### cft-al2023-p3-series.yaml
- Cloudformation template for Amazon Linux 2023 on a p3.x instance type.
- Note that this is a newer os and has different prereqs to install
- AL2023 has official NVIDIA repos and this template is based on the recommended setup from Amazon
- This likely works on most AWS GPU instances but I have only tested a P3.2xlarge
- designed to use connect->session manager from the ec2 console to connect to the cli



