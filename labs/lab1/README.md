# Lab 1 - AWS Deploy EC2
In this Lab, you will be setting up your AWS account with SSH keys to access EC2 and then will launch a Amazon Linux "Free-Tier" AMI to install a LAMP Stack.  You will then deploy some PHP code to remotely create "Load" on the Linux VM and observe the CPU utilization.

#### Key Steps:
1. Setup Key Pair for EC2 and Download PEM file.
2. Create VPC:  cmpe281 (Using Wizard).
3. Launch EC2 Instance.
4. Connect to EC2 Instance.
5. PHP Setup on EC2 Linux AMI.
6. PHP Test Stress App
7. Create PHP AMI Image.


## My Notes
- AMI - deployable instance of machine
- .0 - network , .1 - router
- 10.* - private, 127.* - host, 192.* - private
- NAT Instance - software instance  vs NAT Gateway - hardware instance
- LAMP - Linux OS, the Apache HTTP Server, the MySQL database, and the PHP programming language.

## Some useful commands to remember
```bash
# Install LAMP stack
sudo yum install -y httpd24 php56 mysql55-server php56-mysqlnd

# Apache/PHP Web Root
/var/www/html
sudo yum install stress

# Stress Test with PHP
## Stress using CPU-bound task
stress -c 4

## Stress using IO-bound task
stress -i 2

## Example Test

stress -c 2 -i 1 -m 1 --vm-bytes 128M -t 10s

Where,

    -c 2 : Spawn two workers spinning on sqrt()
    -i 1 : Spawn one worker spinning on sync()
    -m 1 : Spawn one worker spinning on malloc()/free()
    --vm-bytes 128M : Malloc 128MB per vm worker (default is 256MB)
    -t 10s : Timeout after ten seconds
    -v : Be verbose
```
